---
title: Hello World
date: 2012-06-18
---

Today we have launched [Simple Form](https://getsimpleform.cmo) to make online forms easier to build and style. It is very flexible, It allows you to use a form without the annoying iframes and doesn't impose any pre-built themes on your forms.

The only thing you need to change, to use simple form, is the `action` attribute on your form and use the `post method` on it.

An example of the form's usage is at http://minhajuddin.com/about/#Contact_Me . You can checkout the source, it's very simple.

~~~html
<form action="http://getsimpleform.com/messages?form_api_token=475339605245a246498c3b1d364a845b" method="post">
  <input type='hidden' name='redirect_to' value='http://minhajuddin.com/thank-you' />
  <label for='name'>Name</label>
  <br />
  <input type='text' id='name' name='name' placeholder='Your Name' />
  <br />
  <label for='email'>Email</label>
  <br />
  <input type='text' id='email' name='email' placeholder='Your Email' />
  <br />
  <label for='email'>Message</label>
  <br />
  <textarea id='message' name='message' placeholder='Message' rows='8' cols='50'></textarea>
  <br />
  <input type='submit' value='Submit' />
</form>
~~~

As you can see, simple form integrates easily and seamlessly into your app. Hope you guys find it useful.

## Edit

I should have mentioned this earlier, Simple Form sends you an email notification whenever a new form entry is made on your form (Please add bot@getsimpleform.com to your contacts so it doesn't go to your spam folder). We'll make the notifications more flexible in a future version :)
