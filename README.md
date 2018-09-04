# wp-init
Create a WordPress install using the WP-CLI

What this script does
- Downloads WP Core
- Prompts user on wp-config.php settings
- Creates database based on settings in wp-config
- Installs WP Core
- Deletes default themes
- Deletes default plugins
- Updates MAMP Apache httpd-vhosts.conf file with a new Virtual host
- Updates your system /etc/hosts file

This script is intended for developers using MAMP or Vagrant

# Setup - MAMP

This script assumes you already have WP-CLI installed
https://wp-cli.org/

 - Add the path to your MAMP PHP Version to your ~/.bash_profile
https://laurenpittenger.com/wpcli-error-establishing-database-connection-mamp/

`export MAMP_PATH=/Applications/MAMP/bin/php/php7.1.12/bin`

`export PATH="$MAMP_PATH:$PATH/Applications/MAMP/Library/bin"`

 - Add the path of your script to your ~/.bash_profile to make the script globally executable. I generally keep mine in /Users/{user}/scripts/

`export PATH=$PATH:/appropriate/directory`

- run `source ./bash_profile` to update the PATH changes

- Change the VirtualHost configuration within the script to better match what is on your system

# Usage - MAMP

Make a directory for which you want WordPress installed

`mkdir {dir}`

Run this command inside the directory you just made

`wp-init-mamp {SITE URL} {SITE TITLE} {USERNAME} {ADMIN EMAIL}`

EX:

`wp-init-mamp example.test Example username username@example.com`

When prompted for the dbhost, specify 127.0.0.1 instead of localhost
https://wordpress.stackexchange.com/questions/235483/mamp-pro-wp-cli-error-error-establishing-a-database-connection

# Setup - Vagrant

 - Add the path of your script to your ~/.bash_profile to make the script globally executable. I generally keep mine in /Users/{user}/scripts/

`export PATH=$PATH:/appropriate/directory`

- run `source ./bash_profile` to update the PATH changes

- Set synced_folder ownership to it's default (vagrant) in the VagrantFile

`config.vm.synced_folder ".", "/vagrant/sites"`

# Usage - Vagrant

Navigate to the vagrant folder on your local machine
Make a directory for which you want WordPress installed

`mkdir {dir}`

Run this command inside the directory you just made

`wp-init {SITE URL} {SITE TITLE} {USERNAME} {ADMIN EMAIL}`
