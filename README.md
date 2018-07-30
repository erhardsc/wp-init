# wp-init
Create a WordPress install using the WP-CLI

This script is intended for developers using MAMP

Add the path to your MAMP PHP Version to your ~/.bash_profile
https://laurenpittenger.com/wpcli-error-establishing-database-connection-mamp/

`export MAMP_PATH=/Applications/MAMP/bin/php/php7.1.12/bin`

`export PATH="$MAMP_PATH:$PATH/Applications/MAMP/Library/bin"`

Add the path of your script to your ~/.bash_profile to make the script globally executable
I generally keep mine in /Users/{user}/scripts/

`export PATH=$PATH:/appropriate/directory`

run `source ./bash_profile` to update the PATH changes

When prompted for the dbhost, specify 127.0.0.1 instead of localhost
https://wordpress.stackexchange.com/questions/235483/mamp-pro-wp-cli-error-error-establishing-a-database-connection
