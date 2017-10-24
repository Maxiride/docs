The echo command is one of the very first basic and easy to understand example command. Once executed it will simply reply mirroring whatever you sent to the bot first.


```php linenums="49"
public function execute()
    {
        $message = $this->getMessage();
        $chat_id = $message->getChat()->getId();
        $text    = trim($message->getText(true));
        if ($text === '') {
            $text = 'Command usage: ' . $this->getUsage();
        }
        $data = [
            'chat_id' => $chat_id,
            'text'    => $text,
        ];
        return Request::sendMessage($data);
    }
```
