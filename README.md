Push SSH
========

The Push SSH script allows you to easily and quickly push your RSA key out to a remote server with one simple command. This was designed whilst working with a development Raspberry Pi where the OS was reset frequently and required pushing my key to it often.

Installation
------

To install the script you will need to run a few commands. These commands will download the script and move it to `/usr/bin/` so that it will run correctly. The commands are:

    $ wget http://dl.izzard.me/Linux/push-ssh/push-ssh
    $ sudo mv push-ssh /usr/bin/
    $ sudo chmod +x /usr/bin/push-ssh

Once you have run these commands you can start using the script.

Usage
------

The script is extreemly easy to use, simply run the following command:

```$ sudo push-ssh user@host```

This will push your file `~/.ssh/id_rsa.pub` to the remote server. That's all there is to it. You must have firest generated the key for it to work as the script doesn't generate on for you, however, you can follow the steps below to find out how to generate your own for use with the Push SSH script.

Generating a key
------

If you do not already have a key then you will need to generate a key to use . Generating a key gives you the advantage of not needing to enter your password every time you SSH into a server.

The first step is to create the directory where your SSH keys and information will be stored. To do so run the following command:

```$ mkdir ~/.ssh```

Now you have a folder to store the information in, you will need generate the key. To do so run the following command:

```$ ssh-keygen -t rsa -b 2048 -f ~/.ssh/id_rsa -C "Comment about this key"```

This will generate a key with 2048 bit for security. When asked for a password, you can choose to leave it blank or enter a password. If you wish to log into the remote computer without using a password, leave the password blank when asked.

For a full guide on all of this I recomend the excellent [article over at Tuts Plus](http://code.tutsplus.com/tutorials/ssh-what-and-how--net-25138), where I originally found these commands.

Changelog
------

Version | Features | Link
--- | --- | ---
1.1.0 | More robust code found at [Me in It](http://meinit.nl/distribute-ssh-keys-easily) which also sets permissions of directories and files | [Download](http://dl.izzard.me/Linux/push-ssh/push-ssh)
1.0.0 | The first version of Push SSH | [Download](http://dl.izzard.me/Linux/push-ssh/archive/1.0.0)

Code Author
------
The code used in the current version is from [Me in It](http://meinit.nl/distribute-ssh-keys-easily). The script was changed to this code from the previous code as the new code is more robust and sets the permissions which wasn't included in the first version.
