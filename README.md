# PushMeOver

The shell script *pushover* provides an cli for the service [*Pushover*](https://pushover.net/ "Pushover: Simple Notifications for Android, iOS, and Desktop"). This service can be used to send push notifications to mobile devices running *Android* or *iOS* using the *Pushover App* and Notebooks and Desktops using browser plugins. *Pushover* provides a [REST API](https://pushover.net/api "Pushover: API"), which is used by the script to send the notifications.

For using the service *Pushover* it is necessary to signup for the service, purchase a license for a [one-time or recurring fee](https://pushover.net/faq#overview-fees "Pushover: Frequently Asked Questions") and create an Application/API Token. The user key and the API token have to be added to the configuration file of *pushover* (`~/.pushover.conf` ). 

The script *pushover* is capable to use the most of the features of *Pushover*. 

The syntax of *pushvoer* is `pushover [options] 'Text of notification'`

## Supported features

*pushover* supports the following features of the service *Pushover*:

* **title** option `-t <title>`    
For the title of the notification *Pushover* uses by default the name of the application which is linked to the API token.    
With the option `-t` an individual title can be set for the notification. If the title is longer than one word it is necessary to enclose the title with quotation marks.  
An alternative default title can also be set in the configuration file. This default can also be overridden by the option `-t`.  
In all cases the title can be set to blank by `-t ""`
* **priority** option `-p <priority>`  
The priority of the notification can be set with this option.  
Valid priorities are 'lowest', 'low', 'normal', 'high', and 'emergency' (read the [Pushover API documentation](https://pushover.net/api "Pushover: API") for more information).
* **sound** option `-s <sound>`  
The sound which will be played on the target device can be set with this option.  
Valid sounds are  'pushover' , 'bike', 'bugle', 'cashregister', 'classical', 'cosmic', 'falling', 'gamelan', 'incoming', 'intermission', 'magic', 'mechanical', 'pianobar', 'siren', 'spacealarm', 'tugboat', 'alien', 'climb', 'persistent', 'echo', 'updown', and 'none'.

## Error codes

*pushover* will return one of theese error codes:

| Error code | Error |
| ---:|:--- |
| 0 | No error |
| 1 | `hexdump` not available. |
| 2 | config file does not exist or is not readable (not yet implented) |
| 3 | mode of config file is not 0600 (not yet implented) |
| 4 | missing values in config file (not yet implented) |
| 10 | invalid option or value |
| 11 | missing message text |
| 20 | error while connecting to *Pushover.net* |
| 21 | error status from *Pushover.net* |
