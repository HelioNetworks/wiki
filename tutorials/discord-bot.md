## Preface

This guide will work on any of the HelioHost servers.

Python is an interpreted, object-oriented, high-level programming language with dynamic semantics. Its high-level built in data structures, combined with dynamic typing and dynamic binding, make it very attractive for Rapid Application Development, as well as for use as a scripting or glue language to connect existing components together. Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance. Python supports modules and packages, which encourages program modularity and code reuse.

The Discord app works with desktop and mobile platforms, combining the features of a chat lobby, a message board and a VoIP chatting system into one app that's not going to hog resources on your phone or PC. Discord's popularity has only multiplied in recent years, with the app now reaching over 90 million registered users.

Bots and apps are the lifeblood of the Discord development community. They come in all shapes and sizes, from small hobby projects for your server with friends, to huge projects that live in hundreds of thousands of servers. We love seeing the unique, fun, and sometimes downright strange \(in a good way\) creations that come from our community.

## How to get Started with a Discord Bot

First you'll need to have a Discord account, and a Discord channel that you'll add the bot to later. Here's a good guide to get started:

{% embed url="https://www.howtogeek.com/364075/how-to-create-set-up-and-manage-your-discord-server/" caption="" %}

### Create the Bot

Once you have your discord server all set up it's time to create the bot through discord's site. Go to [https://discordapp.com/developers/applications](https://discordapp.com/developers/applications) and make sure you're logged in. Then click `New Applcation` in the top right.

![](../.gitbook/assets/new_application.png)

Type a name and hit create. I decided to name my bot `HelioBot`.

### Add the Bot to your Discord Server

Click `OAuth2` on the left navigation.

![](../.gitbook/assets/oauth2.png)

Then check the bot box under `SCOPES`, and scroll down and select `Administrator` under `BOT PERMISSIONS`. You could select the exact permissions that your bot needs one by one, but for this simple example it's easier to just allow the bot permission to do everything.

![](../.gitbook/assets/bot_admin.png)

Click copy next to the URL that is generated and open that URL in a new tab. Then, select your discord server from the dropdown menu.

![](../.gitbook/assets/add_to_server.png)

Click `Authorize` and complete the reCAPTCHA to add the bot to the Discord server. If you go to your Discord now you can see the bot on the offline user list.

![Bot on the offline user list](../.gitbook/assets/offline_bot.png)

### Write the Bot Script in Python

Log in at [https://www.heliohost.org/login/](https://www.heliohost.org/login/) and continue to Plesk. Then load up the file manager.

![](../.gitbook/assets/file_manager.png)

In the top left corner click the `+` plus sign, and select `Create File`.

![](../.gitbook/assets/plus_file.png)

Then type the name of your new file: `heliobot.py`.

![](../.gitbook/assets/create_heliobot.png)

You want to create this bot in your home directory so random hackers and bots on the internet can't access it directly. Make sure it says `Add a file to: /` not `Add a file to: /httpdocs` or any other folder.

Scroll down in the file manager and clcik on the new `heliobot.py` file to edit it. Then copy/paste this code in:

```python
#!/usr/bin/python3.10

import os
import discord
from dotenv import load_dotenv

load_dotenv()
token = os.getenv('DISCORD_TOKEN')

import certifi
os.environ["SSL_CERT_FILE"] = certifi.where()

client = discord.Client(intents=discord.Intents.default())

class MyClient(discord.Client):
    async def on_ready(self):
        print(f'Logged in as {self.user} (ID: {self.user.id})')
        print('------')

    async def on_message(self, message):
        # we do not want the bot to reply to itself
        if message.author.id == self.user.id:
            return

        if message.content.startswith('!hello'):
            await message.reply('Hello!', mention_author=True)


intents = discord.Intents.default()
intents.message_content = True

client = MyClient(intents=intents)
client.run(token)
```

The first line is called the shebang, and it tells the system which version of python you want to use. Johnny and Tommy also have Python 2.7, and Python 3.6, but we recommend using Python 3.10 like in the example.

Once you have your code copy/pasted in click save in the bottom left corner. Now we need the bot to be executable so in the file manager click the `rw- r-- r--` on the heliobot.py line. 

![](../.gitbook/assets/change_permissions.png)

Check all three of the `Execute/Search` boxes so it looks like this and then click save in the bottom left corner.

![](../.gitbook/assets/755_permissions.png)

Now we need to provide our Discord token to the bot so click the `+` plus sign, and select `Create File` again and this time name the file `.env`.

![](../.gitbook/assets/dot_env.png)

**Make sure you start the filename with a period.** It's easy to miss that in the screenshot. This file needs to be in the **same** directory as your Python script.

Go back to the Discord bot page and click bot on the left navigation again.

![](../.gitbook/assets/select_bot.png)

The first thing we need to do on this page is enable `Presence Intent`, `Server Members Intent`, and `Message Content Intent`. If you're sure your bot doesn't need all three of these enable just what you need, but for simplicity of this guide we're going to enable all three, and then save the changes.

![](../.gitbook/assets/discord_intents.png)

On the same page click the `Reset Token` button, and then copy/paste the token.

![](../.gitbook/assets/copy_token.png)

If you ever think someone has gotten your token, for instance if you posted it on a public wiki like I just did, be sure to come back to this page and reset it. Anyone who has your token can do whatever permissions you granted your bot to your server. Now you need to paste this token into your `.env` file that you created. So go back to the Plesk file manager and click the `.env` file to edit it. Paste the token into the file like this:

![](../.gitbook/assets/paste_the_token.png)

Make sure the line starts with `DISCORD_TOKEN=` like that. Then click `Save Changes` and close the tab. Saving your token separate from your Python code is good practice because this way you can share the code on GitHub or something like that without worrying about people getting access to your bot.

### Starting and Stopping Your Bot

You have a functional bot now, but you need a way to start and stop it.

{% hint style="warning" %}
Side note: Previous versions of this guide used Python scripts to start and stop the Discord bot. Unfortunately, the people who wanted to write their bot in Node.js always complained that they didn't want to use Python for anything. Likewise, if we used Node.js to start and stop the bot, the Python people would inevitably complain about not wanting to use Node.js for anything. Therefore, we wrote the start and stop scripts in Bash CGI to make absolutely sure that no one is happy.
{% endhint %}

We'll use Bash CGI to do that so you can control your bot through your web page. With the file manager, navigate to `/httpdocs` and create a new directory called `bot_control`.

![](../.gitbook/assets/bot_control.png)

Paste in this code into the new file:

```bash
#!/bin/bash

# edit these to match your username, main domain, and bot filename
username="krydos"
main_domain="krydos.heliohost.org"
bot_name="heliobot.py"

###################################################################

printf 'Content-Type: text/html\n\n'
running=`ps aux|grep -v grep|grep "^$username"|grep -c "$bot_name"`
file_base=`echo $bot_name|tr -cd "a-zA-Z0-9"`
log_name="$file_base.txt"
if [ "$QUERY_STRING" == "" ]; then
    if [ $running -ne 0 ]; then
        echo "$bot_name is running. <a href='?action=stop'>Stop</a> - "
    else
        echo "$bot_name is not running. <a href='?action=start'>Start</a> - "
    fi
    echo "<a href='https://heliohost.org/dashboard/load/' target='_blank'>Check Load</a><br><br>Logs: <a href='?action=clear'>Clear</a><pre>"
    tail -30 /home/$main_domain/httpdocs/$log_name
    echo "</pre><script>reloading = setTimeout('window.location.reload();', 10000);</script>"
fi
if [ "$QUERY_STRING" == "action=stop" ]; then
    pid=`ps aux|grep -v grep|grep "^$username"|grep "$bot_name"|tail -1|awk '{print $2}'`
    if [ ${#pid} -ne 0 ]; then
        kill $pid
    fi
    echo "<html><head><meta http-equiv='refresh' content='0; url=https://$main_domain/bot_control.sh' /></head><body>Stopping $bot_name...</body></html>"
fi
if [ "$QUERY_STRING" == "action=start" ]; then
    /home/$main_domain/$bot_name >> /home/$main_domain/httpdocs/$log_name 2>&1 &
    echo "<html><head><meta http-equiv='refresh' content='0; url=https://$main_domain/bot_control.sh' /></head><body>Starting $bot_name...</body></html>"
fi
if [ "$QUERY_STRING" == "action=clear" ]; then
    cat /dev/null > /home/$main_domain/httpdocs/$log_name
    echo "<html><head><meta http-equiv='refresh' content='0; url=https://$main_domain/bot_control.sh' /></head><body>Clearing logs...</body></html>"
fi
exit 0
```

Now, we need to set the permissions of this `bot_control.sh` file to be executable. On the file manager click the `rw- r-- r--` and check all the `Execucte/search` boxes just like we did the heliobot.py file earlier.

![](../.gitbook/assets/change_permissions.png)

Set the permissions of the `start.py` file to `755`.

![](../.gitbook/assets/755_permissions.png)

We also need a way to stop the bot so create `stop.py` in the `cgi-bin` directory.

```text
/home/username/public_html/cgi-bin/stop.py
```

Paste this code into the new `stop.py` script:

```python
#!/usr/bin/python3.7

import os, subprocess, signal

print("Content-Type: text/html\n\n")

counter = 0
p = subprocess.Popen(['ps', '-u', 'username'], stdout=subprocess.PIPE)
# must match your username --------^^^^^^^^

out, err = p.communicate()
for line in out.splitlines():
  if 'heliobot.py'.encode('utf-8') in line:
#     ^^^^^^^--- this has to match the filename of your loop

    counter += 1
    pid = int(line.split(None, 1)[0])
    print("Stopping bot.")
    os.kill(pid, signal.SIGTERM)

if counter == 0:
  print("Already stopped.")
```

Right click on the `stop.py` file and select `Change Permissions`.

![](../.gitbook/assets/change_permissions.png)

And change `stop.py` to `755` permissions as well.

![](../.gitbook/assets/755_permissions.png)

### Test It Out

Now everything should be ready to be tested. Open your browser and go to `domain.heliohost.org/cgi-bin/start.py` and it should start the bot. You can check if the bot is running by going to Discord and seeing if HelioBot is showing up as online now. If it is, test it out by typing the command:

```text
!heliobot
```

It should respond to you.

![](../.gitbook/assets/testing_discord_bot.png)

If it doesn't work go back and check all the steps again to make sure you did everything correctly. If you can't figure out what is wrong let us know by opening [a customer service ticket](https://www.helionet.org/index/forum/45-customer-service/). If everything is working you can shut your bot down by going to `domain.heliohost.org/cgi-bin/stop.py` Then watch your discord and after a few minutes your bot should show up as offline. It's a good idea to keep your bot offline if you don't need it so you don't cause too much load. We recommend monitoring your load by clicking the account load button in cPanel. If you get to 80+ it might be time to shut down the bot or consider [moving to a VPS](https://www.heliohost.org/vps/) where you can run your bot as much as you want and have root shell access as well.

