---
title: ReCaptcha
---

A captcha is a program that can help ensure that only actual people, not spammers or robots, are using particular parts of your site. [ReCaptcha](http://recaptcha.net) displays an image of two words and asks the user to type them in before continuing.

As of version 1.3, Omeka has built-in support for ReCaptcha, a free captcha service from Google. Several Omeka plugins that used to handle captchas individually now all use Omeka's built-in support.

Configuring
---------------------------------------------------------------

In order to enable ReCaptcha for your plugins, you need to do a little configuration.

1.  Go to [recaptcha.net](http://recaptcha.net) to sign up for a
 ReCaptcha key. When you sign up, ReCaptcha will provide you with a  "public" and "private" key. You will need both.
2.  Once you have your keys, go to your Omeka admin panel, and go to Site Settings → Security Settings.
3.  At the bottom of the form, there are two text boxes, one for the public key, one for the private key. Copy the keys you got in Step 1 into the appropriate boxes.
4.  Click "Save Changes" at the bottom of the page.

Now, plugins will be able to display a captcha, and prevent automated programs from abusing your site.

Plugins that use ReCaptcha
---------------------------------------------------------------

The following plugins use Omeka's ReCaptcha support, and configuring ReCaptcha as explained above should enable captchas for all of them. Please make sure you are using the latest version of these plugins.

-   [Contribution](http://omeka.org/codex/Plugins/Contribution "Plugins/Contribution")
-   [SimpleContactForm](http://omeka.org/codex/Plugins/SimpleContactForm "Plugins/SimpleContactForm")


