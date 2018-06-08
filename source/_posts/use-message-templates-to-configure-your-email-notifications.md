---
title: Use message templates to configure your email notifications
date: 2018-06-08 16:23:03
tags:
- Template
- Email
- Notification
---

SimpleForm has had the ability to configure how your email notifications look for a long time now.
However, it hasn't bee properly documented. This blog post tries to remedy that :)

All your forms have a settings page which can be accessed by using the following url:

`https://getsimpleform.com/forms/<api-token>/edit` (The api token is different from the form_api_token, I know I should have named it better :)  )

This page allows you to set up the following:
  1. `akismet key` to use akismet for spam prevention.
  2. `reply to` to change the reply to in your email notifications.
  3. `subject template` to change the subject of the emails that you receive on a form submission.
  4. `body template` to change the body of the email you receive on form submission.

The subject template and the body template support a special syntax called [liquid markup](https://shopify.github.io/liquid/basics/introduction/).
This allows you to create your email notifications in all sorts of shapes based on whatever logic you can think of.

SimpleForm provides variables named the same as the names of your input fields in this markup.

## Example

If we have a form which looks like below

```html
<form ... >
  <input type="text" name="name" />
  <input type="text" name="title" />
  <textarea name="message" />
  <input type="submit" value="Submit Form">
</form>
```

We can configure our body template to look like:

```
Hello Mr. K,
<br />
You received a message from {{name}}: <br />
with the title: {{title}} <br />
Message:
<br />
{{message}}
<br />
<p>Just reply to this message to continue the conversation</p>
```

This of course is a simple look, you have freedom to use any valid html body here.
Mailgun for instance has created free email templates which can be used to style your forms: https://github.com/mailgun/transactional-email-templates

Here is a bonus template from a friend of SimpleForm [@marcogargo](https://twitter.com/marcogargo):

```html
<table bgcolor="#eeeeee" cellpadding="10" cellspacing="0" border="0" width="100%" align="center" style="max-width: 500px; font-family: arial; font-size: 13px; color: #555555;">
  <tr>
    <td>
      <table width="100%" cellspacing="5" cellpadding="5">
        <tr>
          <td align="left" valign="baseline" style="font-size: 17px;">
            Hi, you have <strong style="background: #df691a; color: #fff;">&nbsp;1&nbsp;</strong> new message!
          </td>
          <td align="right" valign="baseline" style="color: #df691a;">
            Simple&nbsp;Form
          </td>
        </tr>
      </table>
    </td>
  </tr>

  <tr>
    <td>
      <!-- Start: Table with the data -->
      <table cellpadding="10" cellspacing="2" bgcolor="#eeeeee" border="0" align="left">
        <tr bgcolor="#ffffff">
          <th>Name</th>
          <td>{{name}}</td>
        </tr>
        <tr bgcolor="#ffffff">
          <th>Email</th>
          <td>{{email}}</td>
        </tr>
        <tr bgcolor="#ffffff">
          <th>Message</th>
          <td>{{message}}</td>
        </tr>
        <tr bgcolor="#ffffff">
          <th>Attachments</th>
          <td><img src={{file}} /></td>
        </tr>
      </table>
      <!-- End: Table with the data -->

    </td>
  </tr>
</table>
```

Checkout this codepen for a full view of the template: https://codepen.io/marcogargano/full/KRWgvY/

Hope you find this useful!
