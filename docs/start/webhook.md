## :point_right: Webhook installation

!!! attention
    From now on the Documentation will assume that you are using the installation with the `manager.php` functionality. If you followed the previous steps, you're fine and you don't have to worry about it since the `example-bot` already comes shipped with it.


## Meet the manager!

!!! info
    `manager.php` is a special file that can handles different management task for our bot as shown later. It is most useful when your bot lives online on a remote VPS.

!!! warning
    While developing your bot in your _local development enviroment_ `manager.php` has no real use.
    Skip to [Configure getUpdatesCLI.php](#configure-getupdatescli)

 The bare minimum setup for `manager.php` is the following, where you need to replace the `'api_key'`, `'bot_username'`, `'secret'` and `'webhook'` values with your own.




 [^1]: It **must** support the UTF-8 encoding, if you don't know what I'm talking about chances are you are good with your editor since it's the default 99% of the time.
