# PushMeOver

The shell script *pushover* provides an cli for the service [*Pushover*](https://pushover.net/ "Pushover: Simple Notifications for Android, iOS, and Desktop"). This service can be used to send push notifications to mobile devices running *Android* or *iOS* using the *Pushover App* and Notebooks and Desktops using browser plugins. *Pushover* provides a [REST API](https://pushover.net/api "Pushover: API"), which is used by the script to send the notifications.

For using the service *Pushover* it is necessary to signup for the service, purchase a license for a [one-time or recurring fee](https://pushover.net/faq#overview-fees "Pushover: Frequently Asked Questions") **and create** an Application/API Token. The user key and the API token have to be added to the configuration file of *pushover* (`~/.pushover.conf`).

*Pushover* can send notifications to devices of single users or groups of users. Groups can be created in the user settings at [*Pushover.net*](https://pushover.net "Pushover: home") (login needed). It is also possible to use the key of other other users or their groups to adress them or their groups. I is not possible to use more than one user or group key while sending a notification. If more than one user should be notificated, it is nessessary to set up a group and use the group key.

By default the user key (or group key) in the configuration file is used to adress the user (or group), which will receive the notification. By using the `-u <user-key>`-Option of the script it is possible to set a different user or group which will receive the notification.

The syntax of *pushover* is `pushover [options] 'Text of the notification'`. If the message text is "-" (a single hyphen) the text will be read from stdin.

`pushover -h` will display a short help text.

## Supported features

The script *pushover* is capable to use most of the features of *Pushover*. It supports the following features:

* **title** option `-t <title>`  
For the title of the notification *Pushover* uses by default the name of the application which is linked to the API token. With the option `-t` an individual title can be set for the notification. If the title is longer than one word it is necessary to enclose the title with quotation marks.  
An alternative default title can also be set in the configuration file. This default can also be overridden by the option `-t`.  
In all cases the title can be set to blank by `-t ""`
* **priority** option `-p <priority>`  
The priority of the notification can be set with this option. Valid priorities are 'lowest', 'low', 'normal', 'high', and 'emergency' (read the [Pushover API documentation](https://pushover.net/api "Pushover: API") for more information).
* **sound** option `-s <sound>`  
The sound which will be played on the target device can be set with this option. Valid sounds are  'pushover' , 'bike', 'bugle', 'cashregister', 'classical', 'cosmic', 'falling', 'gamelan', 'incoming', 'intermission', 'magic', 'mechanical', 'pianobar', 'siren', 'spacealarm', 'tugboat', 'alien', 'climb', 'persistent', 'echo', 'updown', and 'none'.

## Exit codes

*pushover* will return one of theese exit codes:

| Exit code | Status |
| ---:|:--- |
| 0 | No error |
| 1 | `hexdump` not available. |
| 2 | Config file does not exist or is not readable |
| 3 | Mode of config file is not 0600 |
| 4 | API-/User-Key is missing |
| 10 | Invalid option or value |
| 11 | Missing message text |
| 20 | Error while connecting to *Pushover.net* |
| 21 | Error status from *Pushover.net* |
