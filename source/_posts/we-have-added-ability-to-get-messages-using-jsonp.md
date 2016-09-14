---
title: We have added ability to get messages using jsonp
date: 2014-04-25
---

If you want to get all your messages (maybe to display on an internal web page) via ajax you can do the following (using jquery)

~~~javascript
$.get("http://getsimpleform.com/messages.js?api_token=479afc5e07adc370e79cc75ad751d071",{}, function(response){console.log(response)}, 'jsonp')
~~~

Note that the path is `/messages.js` instead of `/messages.json` also the last argument in `$.get` is `jsonp`

###Warning

If you put this on a public page everyone can view your messages and will be able to delete them as the 'api_token' is a private token, so put this only on non public pages.
