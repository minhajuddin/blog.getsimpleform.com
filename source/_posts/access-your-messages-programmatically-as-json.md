---
title: Access your messages programmatically as json
date: 2012-09-09
---

Access your messages programmatically as json

You can now access the messages in simpleform as json. You just have to append a `.json` to the url. e.g. `http://getsimpleform.com/messages.json?api_token=479afc5e07adc370e79cc75ad751d071` This way you can display your messages anywhere you want.

Update:

Here is some code to get the data using jsonp.

~~~javascript
//replace the api_token with your api token!
$.ajax('http://getsimpleform.com/messages.json?api_token=2d124f03e54c6bf83ae49ab756c4d04c', {
  complete: function(data) {
    console.log(JSON.parse(data.responseText));
  },
  dataType: 'jsonp'
})
~~~

###Fair Warning!!

You need to remember that if you are embedding this code on a public page, *Everyone can read your messages*.

