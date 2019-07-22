# VPSLara

Install laravel on VPS

---

You'll need a VPS Account before getting started. Make sure to select Ubuntu Server:

## Installation

SSH into your server and run the following command:

```
curl -sL https://github.com/tdmrut/vpslara/archive/master.tar.gz | tar xz && source vpslara-master/install
```

You can make sure it's installed by running

```
vpslara -h
```

## Setup Your Laravel Server

```
vpslara setup
```

The default configuration will install Nginx, PHP7.2, and MySQL 5.7. If you wish to use PHP7.1, you can include the argument `php71` like so:

```
vpslara setup php71
```

## Creating a New Site

You can now Clone a Repo or Create a New Laravel app within the `/var/www` folder:

```
cd /var/www && laravel new mywebsite
```

Then, you'll need to setup a new Nginx Host by running:

```
vpslara host mywebsite.com /var/www/mywebsite
```

`vpslara host` accepts 2 parameters:

1. Your website domain *(website.com)*
2. The location of the files for your site *(/var/www/website/public)*

Finally, point your Domain to the IP address of your new server... And Wallah, you're ready to rock 🤘 with your new Laravel website.

## Passwords

When installing and setting up vpslara there are 2 passwords that are randomly generated.

1. The password for the new vpslara user created on the server.
2. The default MySQL password

To get the `vpslara` user password you can type in the following command:

```
vpslara pass
```

And the password for the `vpslara` user will be displayed. Next, to get the default MySQL root password you can type the following command:

```
vpslara mysqlpass
```

And the MySQL root password will be displayed.

## Switching to vpslara user

When you SSH into your server you may want to Switch Users back to the vpslara user, You can do so with the following command:

```
su - vpslara
```

Make sure to star this repo and watch this repo for future updates. Thanks for checking out vpslara ⛵
