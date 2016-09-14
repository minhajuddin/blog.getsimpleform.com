---
title: We have added file uploads to simple form!
date: 2012-07-20
---

You can now use Simpleform to create forms capable of accepting files as inputs. This makes it capable of creating all kinds of forms.

file upload

You can checkout the demo form (with a file input) at http://getsimpleform.com/demo !

All you need to do to have file uploads in your form, is add an file input element and set the form's enctype attribute to multipart/form-data like the snippet below:

~~~html
<form id='demo-form' action="http://getsimpleform..."  method="post" enctype="multipart/form-data">
....
 <input type='file' name='avatar' />
....
</form>
~~~

Have fun!
