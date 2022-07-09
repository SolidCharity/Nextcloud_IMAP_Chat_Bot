# Nextcloud IMAP Chat Bot

This bot is written in Python and publishes E-Mail messages from IMAP to a Nextcloud Talk conversation.

This script will read messages from an IMAP mailbox,
and post the content of the messages to a Nextcloud Talk room.
We use this for posting messages from Wordpress Wordfence to a Talk room where the administrators are listening.

# Usage

First clone the repository:

    git clone https://github.com/SolidCharity/Nextcloud_IMAP_Chat_Bot.git

Then make a copy of the configuration file and insert your own settings:

    cd Nextcloud_IMAP_Chat_Bot
    cp config.yml.sample config.yml

Now install Python virtual environment and make the first run:

    cd Nextcloud_IMAP_Chat_Bot
    pipenv install
    pipenv shell
    python imap_to_nextcloud.py config.yml

For running this script as a cronjob, you can add a line like this to your crontab:

    */15 * * * * cd $HOME/Nextcloud_IMAP_Chat_Bot && pipenv run python imap_to_nextcloud.py config.yml >> $HOME/var/imap_to_nextcloud.log
