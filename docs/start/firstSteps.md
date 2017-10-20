# First steps with the "plug-n-play" example-bot

## Configuring the bot with your credentials


!!! important
    Telegram supports **two** different methods to "talk" with your bot, they are referred as _Webhook_ and _getUpdates_. The main difference is that with the former Telegram servers send updates to your bot while with the latter it's your bot that asks for them.

    We will first go through the _getUpdates_ method for developing locally and then we will switch to the _Webhook_ — yes it will be as easy as flipping a switch.


### :point_right: getUpdatesCLI setup

!!! info
    This configuration is the suggested one for a _local development environment_ as it is **way easier** to setup and yet very effective. When switching to a _remote host_ the Webhook performs better, at a proper time the method will be explained and implemented.


Open your `getUpdatesCLI.php` with any text editor[^1] and modify these lines with your bot credentials:

```php linenums="15"
// Add you bot's API key and name
$bot_api_key  = 'your:bot_api_key';
$bot_username = 'username_bot';
```



Now head to the very end of the file and add:

```php linenums="90"
 sleep(3); // Makes the script sleep for three seconds, let it chill
```

Here we go, the `example-bot` is now ready to be fired up! :fire:


### Preliminary testing of the example-bot

 So far so good, in a shell execute the following command:

```shell
 $ while true; do ./getUpdatesCLI.php; done
```

If everything has been set up right the bot is now running in your virtual machine, open a Telegram chat with it and try the basic command `/whoami`, the bot should answer with your profile picture, id and other infos.

??? summary "What have we done so far and getUpdatesCLI.php breakdown"
    * Lines 16-17: We specified our bot credential to allows the framework to interact with the Telegram APIs.
    * Lines 20-21: As we will see later on the bot can recognzie __who__ is executing a command, this way we can restrict certain commands to admin users.
    * Lines 25-26: All the commands are separate files and you can organize them in separate folders, we need to specify their paths for the framework to be able to recognize them.
    * Lines 29-35: For various usage cases a MySQL database it is very useful, during the "Vagrant up" ran earlier in the docs we automagically generate one for you with the default username and password like the ones specified in getUpdatesCLI.
    * Lines 50-53: You can uncomment this lines to enable logging, very useful when something isn't working. The logs will be written in the bot root direcotry.
    * Lines 58-60: In the case where the bot will handle download and upload of files here you can specify its location.
 ---
