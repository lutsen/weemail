WeeMail
=======

WeeMail is a set of email templates and partials to build some common types of responsive HTML emails.


CodeKit templates
-----------------

WeeMail uses the [CodeKit](http://incident57.com/codekit) .kit [template syntax](http://incident57.com/codekit/help.html#kit).
You can compile the templates using CodeKit. The syntaxt is quite simple, so it should be easy to convert them to your own favourite template language as well.
Email code gets messy very quickly, and the partials make the code much easier to read.


### CSS ###

All the CSS code is in **_partials/head.kit**
Make sure to [inline the CSS](https://inliner.cm/) before sending your emails!


### Variables ###

The variables to define the main colors, widths and fonts are defined in **_partials/variables.kit**



Supported email clients
-----------------------

WeeMail has been tested to work on:

- AOL Web
- Gmail
- Google Apps
- Office 365
- Outlook.com
- Yahoo Mail
- Apple Mail 9
- Outlook 2000*
- Outlook 2003*
- Outlook 2007*
- Outlook 2010*
- Outlook 2013*
- Outlook 2016 (Mac)
- Outlook 2016 (Win)*
- Thunderbird
- Android 4.0
- Gmail (Android)
- iPad
- iPhone 5s
- iPhone 6
- iPhone 6 Plus

*Rounded corners won't work here


Outlook fonts fallback issue
----------------------------

Outlook font fallback sometimes doesn't work, resulting in text being rendered in times. This can happen with the $font_title and $font_btn specified in this template. Read how to fix this here: https://litmus.com/blog/typography-tips-for-email-designers


Sending emails
--------------

Before sending emails, make sure to take these important steps:


### Remove comments ###

To prevent your email to be marked as spam, remove any comments from your HTML code.
You could use regular expressions for this:

- CSS: `/\*[\s\S]+?\*/`
- HTML: `<!--(.*?)-->`


### Inline your styles ###

Some email clients require your CSS styles to be inline to work correctly. You can move them inline with this tool:
https://inliner.cm/


### Host your images ###

Host the images in your email online (and use their right URLs ofcourse).


Preheader
---------

The preheader is in **_partials/preheader.kit** and contains text that appears after the subject line in a preview/notification in the inbox. Not creating a preheader means generally the first bit of text content gets used. This can be bad when areas like the web version link are first. The preheader can be visible, but in this partial it is only visible in the preview/notification in the inbox, and not in the email itself.


Columns
-------

**_partials/column_1.kit** spans 1 column, and **_partials/column_2.kit** spans 2 columns. Both are responsive if the email clients supports this.


Gutter
------

All td cells in a column table should have the gutter class.


Ruler
-----

A horizontal ruler can be added with **_partials/ruler.kit**


Fixes
-----

These are some partials to fix specific emial client bugs.


### fix_outlook_images.kit ###

Fix images in Outlook when using DPI scaling on Windows:
https://www.campaignmonitor.com/forums/topic/8035/
https://litmus.com/community/discussions/151-mystery-solved-dpi-scaling-in-outlook-2007-2013
http://msdn.microsoft.com/en-us/library/microsoft.office.interop.word.defaultweboptions.pixelsperinch%28v=office.14%29.aspx

When using scaling factors greater than 100% (96 DPI) Outlook often displays images incorrectly.
This Microsoft Office specific XML forces images to be rendered at 96 PPI, making them display correctly.
Outlook 2007 doesn't quite render images properly at 96 PPI and still enlarges them slightly.


### fix_gmail.kit ###

http://freshinbox.com/blog/gmail-on-ios-increases-font-size-on-some-emails

The Gmail iOS app likes to mess around with font sizes. It increases font sizes to make them more legable on mobile.
It can however have very unpredictable results and break email templates or make them look worse.
Using the method below leverages a email width check to prevent the font sizing behaviour occurring.


### Outlook.com ###

Outlook.com strips out tags it doesn't like, including links with href="#"
So for testing, use a link to an URL!


Credits
-------
Some code based on [Central College Nottingham HTML Email Boilerplate (Redux Version)](https://github.com/centralcollegenottingham/HTML-Email-Boilerplate-Redux) and the [Email on Acid boilerplate](https://www.emailonacid.com/blog/article/email-development/html_boilerplate). Placeholder images from [pipsum.com](http://pipsum.com). Icon from [iconmonstr.com](http://iconmonstr.com/).

WeeMail is a project of [Lútsen Stellingwerff](http://lutsen.land/) from [HoverKraft](http://www.hoverkraft.nl/).