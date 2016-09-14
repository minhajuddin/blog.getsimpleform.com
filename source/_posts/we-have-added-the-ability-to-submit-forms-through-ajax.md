---
title: We have added the ability to submit forms through ajax
date: 2013-07-29
---

You can now submit form through ajax in a simple way. Below is an example using jquery which submits data to our demo form.

~~~javascript
$.ajax({
  dataType: 'jsonp',
  url: "http://getsimpleform.com/messages/ajax?form_api_token=39c8f9e5a2de15ad63469475702522b9",
  data: {
    name: "John",
    message: "Boston",
  }
}).done(function() {
  //callback which can be used to show a thank you message
  //and reset the form
  alert("Thank you, for contacting us");
});
~~~

Note that the url here is different than the normal form url. It has an extra `/ajax` in it. For normal forms the url for action would be `http://getsimpleform.com/messages?form_api_token=39c8f9e5a2de15ad63469475702522b9` but for ajax requests it should be `http://getsimpleform.com/messages/ajax?form_api_token=39c8f9e5a2de15ad63469475702522b9`
