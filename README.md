## common problem
[https://day.app/2021/06/barkfaq/](https://day.app/2021/06/barkfaq/)

## Feedback Telegram group
[Bark Feedback Group](https://t.me/joinchat/OsCbLzovUAE0YjY1)

## send push
1. Open the APP and copy the test URL

<img src="https://wx4.sinaimg.cn/mw2000/003rYfqply1grd1meqrvcj60bi08zt9i02.jpg" width=365 />

2. Modify the content and request this URL
````
You can send a get or post request, and if the request is successful, you will receive the push immediately

URL composition: the first part is the key , followed by three matches
/:key/:body
/:key/:title/:body
/:key/:category/:title/:body

title push title is a bit thicker than body font size
body Push content Please use the newline character '\n' for line breaks
The fields occupied by other functions of the category are not open yet, just ignore them
The post request parameter names are also the above
````

## Copy push content
When you receive a push, pull down the push (or swipe left in the notification center to view the push) and there is a `Copy` button, click to copy the push content.

> <img src="http://wx4.sinaimg.cn/mw690/0060lm7Tly1g0btjhgimij30ku0a60v1.jpg" width=375 />

````objc
//will copy "Verification code is 9527"
https://api.day.app/yourkey/ verification code is 9527
````

Carry the parameter automaticallyCopy=1, when the push is received, the push content will be automatically copied to the pasteboard (if you find that it cannot be copied automatically, try restarting the phone)
````objc
//Automatically copy "The verification code is 9527" to the pasteboard
https://api.day.app/yourkey/ verification code is 9527?automaticallyCopy=1
````


Carry the copy parameter, the above two copy operations will only copy the value of the copy parameter
````objc
//Automatically copy "9527" to the pasteboard
https://api.day.app/yourkey/ verification code is 9527?automaticallyCopy=1&copy=9527
````

## Other parameters

* url
````
// Clicking on push will jump to the address of the url (when sending, the URL parameters need to be encoded)
https://api.day.app/yourkey/Baidu URL?url=https://www.baidu.com
````
*isArchive
````
// Specify whether to save the push information to the history record, 1 is to save, other values ​​are not to save.
// If this parameter is not specified, the push information will be saved according to the settings in the APP.
https://api.day.app/yourkey/Push to save?isArchive=1
````
* group
````
// Specify the push message group, you can view the push by group in the history.
https://api.day.app/yourkey/ needs group push?group=groupName
````
* icon (only supported on iOS15 or above)
````
// Specify the push message icon
https://api.day.app/yourkey/requires custom icon push?icon=http://day.app/assets/images/avatar.jpg
````
* Timely notice
````
// Set up time-sensitive notifications
https://api.day.app/yourkey/Time-sensitive notifications?level=timeSensitive

// optional parameter value
// active: The default value when not set, the system will immediately turn on the screen to display the notification.
// timeSensitive: Time-sensitive notifications, which can be displayed in a focused state.
// passive: only add the notification to the notification list, no screen reminder
````

## backend code
[bark-server](https://github.com/Finb/bark-server)
> Deploy the backend code on your own server. Docker support

## Chrome plugin
[Bark-Chrome-Extension](https://github.com/xlvecle/Bark-Chrome-Extension)
> This is a chrome plug-in that can help you easily push the text or URL on the web page to the Bark mobile phone.

Show results

![](http://wx4.sinaimg.cn/mw690/0060lm7Tly1fyaqyhzdnxg30660dcu0h.gif)


## Online timing sending
[https://api.ihint.me/bark.html](https://api.ihint.me/bark.html)

## Windows Push Client
[https://github.com/HsuDan/BarkHelper](https://github.com/HsuDan/BarkHelper)

## Cross-platform command line application
[https://github.com/JasonkayZK/bark-cli](https://github.com/JasonkayZK/bark-cli)

## Quicker actions
Use Quicker software to push selected text to iPhone on Windows with one click, support to open URL and automatically copy push content
[https://getquicker.net/Sharedaction?code=e927d844-d212-4428-758d-08d69de12a3b](https://getquicker.net/Sharedaction?code=e927d844-d212-4428-758d-08d69de12a3b)

## Bark for Wox
[https://github.com/Zeroto521/Wox.Plugin.Bark](https://github.com/Zeroto521/Wox.Plugin.Bark)
