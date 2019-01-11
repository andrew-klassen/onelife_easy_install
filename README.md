# onelife_easy_install
## Minimal Installation

1. clone this repository

```
apt install git
mkdir onelife_workspace
cd onelife_workspace
git clone https://github.com/andrew-klassen/onelife_easy_install.git .
```

2. run the installation script

```
chmod +x install
./install
```

Below is sample output.

Welcome to the onelife_easy_install. This installer was designed
and tested for Ubuntu 18.04. Please visit the following link
for documentation. If you wish to preform a more custom installation,
press Ctrl+c and execute the installer using "./install walkthrough".

https://github.com/andrew-klassen/onelife_easy_install

Ssh username (needs sudo power):

3. start the server

```
onelife start
```

## Onelife Documentation

onelife is the easy installer's command line utility that makes managing the   
server after installation easier. Please refer to the --help page below for  
documentation. After installation the one hour one life client will be added  
to the gnome applications menu so that the onelife utility is not needed for
the client.

root@server:~# onelife --help

This is a command line utility for managing the one hour one life server.

Usage:

	onelife set-version <version_number>:
		Sets the version for the server. This must match the
		version that the client is running. The client's
		version number can be found in the dataVersionNumber.txt
		file on the client machine.

	onelife get-version:
		Shows the version of the game the server is running.

	onelife start:
		This starts the server. Use Ctrl+z to end it gracefully.

	onelife install:
		This will install the server.

	onelife uninstall:
		Removes the server and all configuation files to free up space.

	onelife reinstall:
		This is equivalent to using uninstall and then install. It's useful
		if you want to clean out server logs and reset the map.
		Note: reconfigure is significantly faster if you are only wanting
		to reconfigure the server.

	onelife reconfigure:
		This will reconfigure the server using the walkthrough installation.
		It is also the recommened way to update an exising server, but does
		wipe the map.

	onelife set-password <password>:
		Sets the password for the server. Clients connecting will need to
		have this password saved in their settings\serverPassword.ini file.
		Clients will also need to login using an email or key. The email or
		key can be anything, but both fields can not be empty. The server 
		needs to be restarted for this setting to take affect.

	onelife get-password:
		Reveals the server's password. Unfortunately the server does not
		provide any method of storing the password in a hashed form.
		Its recommended that you use a password for your server that
		is not used anywhere else.

	onelife clear-password:
		Clears the server's password. Restart is needed for changes to
		take affect.

	onelife play:
		Starts the client.

	onelife showuser <optional_email>:
		Shows the user's email and key if server is setup with a ticketing system and if
		the account exist. This utility only shows unblocked/active users. If no email
		is provided then the utility displays all unblocked users.

	onelife adduser <email> <optional_key>:
		Creates an unblocked user. If no key is provided, the utility will generate
		a cryptographically secure 30 character key and display it to the console. This
		is the recommended method. This key can be added to the clients accountKey.ini
 		if the user wishes to do so, vs copying and pasting. If the utility is used on an
		existing email, a second key is created for them and the client can login
		using both.

	onelife blockuser <email>:
		Will prevent the user from logging in, but preserves their account email and key.

	onelife unblockuser <email>:
		Allows a perviously blocked user to be able to log back in.

	onelife resetuser <email> <optional_key>:
		Deletes all accounts for provided email and creates a new one.

	onelife map:
		Shows in real time the last location of all players known to the server.
		Use clearlog to remove old players. Works by parsing /opt/onelife/OneLife/server/log.txt.

	onelife clearlog:
		Clears the /opt/onelife/OneLife/server/log.txt log.

	onelife switch-window-mode:
		If client is running in fullscreen mode, this will switch it over to windowed.
		If client is using windowed mode, this switches them to fullscreen.

Author:

Andrew Klassen  
aklassen80@yahoo.com  

## Installation Directories

/usr/sbin  
/usr/sbin/onelife_easy_install  
/opt/onelife  
