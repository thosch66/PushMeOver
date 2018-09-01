# PushMeOver

The shell script *pushover* provides an cli for the service [*Pushover*](https://pushover.net/ "Pushover: Simple Notifications for Android, iOS, and Desktop"). This service can be used to send push notifications to mobile devices running *Android* or *iOS* using the *Pushover App* and Notebooks and Desktops using browser plugins. *Pushover* provides a [REST API](https://pushover.net/api "Pushover: API"), which is used by the script to send the notifications.

For using the service *Pushover* it is necessary to signup for the service, purchase a license for a [one-time or recurring fee](https://pushover.net/faq#overview-fees "Pushover: Frequently Asked Questions") and create an Application/API Token. The user key and the API token have to be added to the configuration file of *pushover* (`~/.pushover.conf` ). 

The script *pushover* is capable to use the most of the features of *Pushover*. 

The syntax of *pushvoer* is `pushover [options] 'Text of notification'`
