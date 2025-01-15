# Ruby on Rails

{% hint style="warning" %}
Ruby on Rails is available on [Morty](servers/virtual/morty.md), [Tommy](servers/virtual/tommy.md), [Johnny](servers/virtual/johnny.md), or the [VPS plans](https://heliohost.org/vps/).
{% endhint %}

## Preface

HelioHost is one of the few free web hosts to offer the Ruby programming language. A combination of Perl's syntax and Smalltalk's semantics, Ruby is a mature production language that remains popular. Ruby's compatibility with multiple programming paradigms allows it great versatility and makes it an easy language to learn for existing developers.

We also offer the powerful Ruby on Rails web application framework. This framework contains all the essentials for building a web application, and greatly simplifies the task by providing libraries tailored to do almost any task. By utilizing the Model-View-Controller architectural pattern, Rails effectively separates different aspects of your web application, allowing for modular design and extensibility.

## How to set up Ruby on Rails

### Download the example project

Download the example Ruby on Rails files from: [heliohost.org/downloads/ror_ruby3.2.2_rails8.0.1.tar.gz](https://heliohost.org/downloads/ror_ruby3.2.2_rails8.0.1.tar.gz)

### Upload the example project

Navigate to your home directory and click the `+` button to upload the tar.gz file. Locate the `ror_ruby3.2.2_rails8.0.1.tar.gz` file that you just downloaded, and upload it to Plesk. Make sure you upload it to your home directory, not `httpdocs`.

![](../.gitbook/assets/ror_upload.png)

### Extract the example project files

Now click the filename of `ror_ruby3.2.2_rails8.0.1.tar.gz` to extract the tar.gz file. Make sure that it is extracting the files to the `/` directory and not to `httpdocs` or anywhere else.

![](../.gitbook/assets/ror_extract.png)

### Edit the `environment` file

Click on the `config` directory, and then click the `environment.rb` file to edit it. You'll need to change the line that says `ror.helioho.st` to your actual domain. Then save the file.

![](../.gitbook/assets/ror_domain.png)

### Install Ruby

Now click `Websites and Domains` on the main left Plesk menu. Next click the header `Get Started` and then click `Ruby` from the menu displayed. 

![](../.gitbook/assets/ror_ruby.png)

### Enable Ruby

The test Ruby on Rails files are designed for Ruby 3.2.2 so ensure you have `Ruby Version` set to `3.2.2-p53`. Change the `Application Mode` from `production` to `development` so you can see errors later, and wait until you see a confirmation message that says `Information: Application mode was successfully updated`. Then click `Enable Ruby` and wait for the confirmation message saying Ruby was enabled:

![](../.gitbook/assets/ror_enable.png)

### Wait for Ruby Deployment

{% hint style="info" %}
In order for the Rails application to be deployed it requires an Apache restart. Apache restarts happen every 2 hours. Please be patient and wait for the full 2 hours before assuming anything is broken.

Toggling the `Application Mode` between `production` to `development` also requires an Apache restart for the new setting to take effect.
{% endhint %}

If everything is working it should look like this: 

![](../.gitbook/assets/ror_works.png)

Once you've got this basic example working we encourage you to edit the files, and create your Ruby on Rails website. Let us know if you have any questions.

## Troubleshooting

If you receive an error message that says `Web application could not be started by the Phusion Passenger(R) application server. Please read the Passenger log file (search for the Error ID) to find the details of the error. You can also get a detailed report to appear directly on this page, but for security reasons it is only provided if Phusion Passenger(R) is run with environment set to development and/or with the friendly error pages option set to on.` then this means you did not set the `Application Mode` from `production` to `development`.

To enable more detailed error reporting, please refer to [the steps listed above](#enable-ruby) to set the `Application Mode` from `production` to `development`.  
After changing to development mode, restart your app.  
You will then need to wait for up to 2 hours for the next Apache restart for the new setting to take effect.  
We recommend leaving the `Application Mode` as `development` so that you can see error logs.  

### Further Support 

If it doesn't work, go back and check all of your steps again. If it's been more than a full 2 hours and it still isn't working please make a new post in the [Customer Service forum](https://helionet.org/index/forum/45-customer-service/?do=add), making sure to provide your **username** and any **error messages** you are encountering.