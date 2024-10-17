# PostgreSQL Database Remote Connection Error

## Error: `no pg_hba.conf entry for host`

When trying to connect remotely to your PostgreSQL database, if you get an error message that says `no pg_hba.conf entry for host`, this means you don't have remote access.

## Remote Access to PostgreSQL is Disabled by Default

Most users do not need or want remote access to their PostgreSQL databases, so it's disabled on our shared hosting accounts by default for security reasons.

## How to Request Remote Access to PostgreSQL

To request remote access to PostgreSQL, please post a request in our [Customer Service forum](https://helionet.org/index/forum/45-customer-service/), making sure to provide your **hosting account username**, **database name**, and the **database user name** you want to have remote access. An admin will enable remote access for you and provide you with the remote connection details. 

## Can I edit the PostgreSQL `pg_hba.conf` file myself?

No. Allowing users to edit this file could enable them to remove password protection from other users' databases and access anything they wanted on the entire server, which would obviously be a huge security vulnerability.

## Can I enable remote access to PostgreSQL myself?

No. Plesk, like most control panels, has extremely limited support for PostgreSQL, and you can't enable remote access yourself.

If you prefer to handle remote database access yourself, you can create a MariaDB database inside Plesk. When creating the new MariaDB database, select one of the `Allow remote connections` options under MariaDB's `Access control` settings.

If you want to enable remote database connections to PostgreSQL databases yourself, you would need to get one of our [VPS Plans](https://heliohost.org/vps/).