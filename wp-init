#!/bin/bash
# Download Latest WP Core, create a wp-config.php file, create a database,
# and initailize a new user for the WordPress install
#
# This script assumes that you already have WP-CLI installed
#
# Execute this script inside the directory you want a WordPress install in
RED='\033[0;31m'
NC='\033[0m' # No Color

if [[ -z "$1" ]]
  then
    echo "Please supply the local SITE URL in the first parameter"
    exit 1
fi

if [[ -z "$2" ]]
  then
    echo "Please supply the SITE TITLE in the second parameter"
    exit 1
fi

if [[ -z "$3" ]]
  then
    echo "Please supply the USERNAME in the third parameter"
    exit 1
fi

if [[ -z "$4" ]]
  then
    echo "Please supply the ADMIN EMAIL in the forth parameter"
    exit 1
fi

 # download WordPress
wp core download

# Prompt user on wp-config.php settings
wp config create --prompt

# Create database
wp db create

# Init WP Core
wp core install --url=https://$1/ --title=$2 --admin_user=$3 --admin_password=Password1 --admin_email=$4

# Get rid of default themes
wp theme delete twentyseventeen twentysixteen twentyfifteen

# Get rid of default plugins
wp plugin delete akismet hello

echo -e "\n${RED}Setup is not complete!${NC}"
echo -e "\nMake sure you update your Apache ${RED}httpd-vhosts${NC} and ${RED}hosts${NC} file with the URL and PATH you specified"

echo -e "\n${RED}URL:${NC} https://$1/"
echo -e "${RED}PATH:${NC} `pwd`"
