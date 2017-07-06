Through the adminstrator control panel GlobaLeaks has room for rich customization. Everything within the basic customization guide is well tested and safe. Use caution with the advanced features. Some of them are experimental, and may be removed or changed in newer versions of the software.

Basic customization guide (safe and suggested)


The Basic Customization Guide enables you to customize all the most important features of the application like for example:

texts of the interface;
the look and feel (CSS, Fonts, Logos, Background)
All this settings are available through the admin panel offered by the application and this is the safe way to customize the application.

This is the safe and suggested guide to customize GlobaLeaks.

Node Info Customization

On page http://yoursite.com/#/admin/content, in the "Main Configuration" tab it's possible to customize the following options:

Initiative logo
Node name
Node Subtitle
Node Description
Node Footer
Node Presentation
Tor Hidden Service
Tor2web Public Site
Look and Feel Customization

On page http://[...]/#/admin/content, on tab "Theme Customization" it's possible to customize the look and feel by uploading custom CSS.

DANGER! Be aware that you can easily compromise a whistleblowers identity by embedding custom fonts, images from external sources, and links to other websites. This is especially important if you are making the platform available over HTTPS.

The file uploaded permits to override all of the default Globaleaks' CSS directives.

On the same page it's possible to upload a custom file "Load Custom File", in order to load custom files (e.g., a custom favicon.ico, a robots.txt or a background.png).

Uploaded files will be accessible in the /static path (e.g., static/file.ext).

Background Color Customization Example

This CSS example shows how to customize the Background Color of the application.

Let's create a file styles.css as follow:

body
{
   background-color: red;
}
Background Image Customization Example

This CSS example shows how to customize the Background Image of the application. Upload a background image through the "Load Custom File button"; let's suppose 'background.png'.

Let's create a file styles.css as follow:

body
{
   background-image:url('/static/background.jpg');
   background-repeat: repeat;
   background-position: top center;
   background-attachment: fixed;
}   
Font Customization Example

This CSS example shows how to customize the Font of the application. Upload a custom font through the "Load Custom File button"; let's suppose 'antani.ttf'.

Let's create a file styles.css as follow:

@font-face {
    font-family: 'Antani';
    src: url('static/antani.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
}

body {
    font-family: 'Antani', Helvetica, Arial, Sans;
    font-size: 16px;
}
Translations Customization

On page http://[...]/#/admin/content, on tab "Translation Customization" it's possible to enable current translation languages and eventually load custom translations.

GlobaLeaks is currently translated in a lot of languages thanks to the Transifex community Effort.

Translations are added to the Globaleaks package upon a new language reach more than 50% of translated sentences; if your language is missing, the best you can do is to help translating it!

CSS #BodyDefault class extensions

The application also attaches the following CSS classes to the #bodyDefault <div> so that you can customize pages based on the applications location and state. For example, when a user navigates from /#/submission to /#/login the class .ext-public will be removed from #BodyDefault and .ext-login will be added.

Class	Description
.ext-public	appended on every page intended for Whistleblower's. These are the public pages.
.ext-embed	always appended to #bodyDefault if the url of page includes ?embedded=true
.ext-authenticated	appended to every page when a user is authenticated. This field may be deprecated.
Refer to this file for an example on how to use these classes.

Translated links useful for landing pages

Globaleaks offers the possibility to provide users links automatically localized in a chosen language in order to avoid users to switch the language manually. For every link it would be possible to provide localized links by simply appending the short code of the language to the url. For example to provide a internationalized landing page for http://[...]/#/admin/submission) it would be possible to use:

http://[...]/#/admin/submission/it for Italian page
http://[...]/#/admin/submission/ru for Russian page
For the full list of the languages code available please refer to the application page http://[...]/#/admin/content, on tab "Translation Customization".

Notification Templates Customization

On page http://[...]/#/admin/content, on tabs "Plaintext Notification Templates" and "Encrypted Notification Templates" it's possible to configure mail templates for plaintext and encrypted notification respectively.

For example, by defining a notification template email with:

"Hello %ReceiverName%, you got a new Tip for you in %ContextName%"
the receiver would get an email with %ReceiverName% replaced with his configured name, and %ContextName% with the name of the Context of the submission.

The notification events are four (New Tip, new Comment, new Message or new File uploaded) and for each one is possible to configure a specific mail template. In addition it's also possible to configure the template for a txt file that will be included in all collection archives downloaded through the platform.

For each specific template are available some specific keyword; for example, encrypted version of the templates allows more keywords.

The keyword available in encrypted template could contain sensitive data

To use a keyword, just write them with the percentage signs.

The following is the list of all the availalbe keywords

Shared keywords available in all notification templates

Notification: Encrypted or Plaintext mail about a new Tip, File, Message, Comment.

%EventTime%: Pretty timedate based with english Month name (no localization available)
%NodeName%: The name of your node
%HiddenService%: The URL of the hidden service configured
%PublicSite%: The URL of the URL that can be reach from outside
%ReceiverName%: The name of the Receiver
%ContextName%: The name of the context related (every Tip is always under one and only one context)
Tip event

%TipTorURL%: URL of the hidden service + the Tip ID, usable by the receiver (prior authentication) to access the tip.
%TipT2WURL%: This URL use the Public Website (default a tor2web extenal website) usable to reach the Tip. This is actually available only if the Node is configured in order to permit Receivers access via Tor2Web (default is deny, check in admin advanced settings -> tor2web accessibility)
%TipNum%: an "unique" number of three digit assigned to every Tip. Every Receiver has a different %TipNum% for evert Tip. Shall be used to be put in the mail subject, in order to follow easily the
Encrypted Tip Event

%TipFields%: The dump of the submission fields! This is sensitive, check the security consideration here: https://docs.google.com/a/apps.globaleaks.org/document/d/1niYFyEar1FUmStC03OidYAIfVJf18ErUFwSWCmWBhcA/edit#heading=h.la9gjvhg62sq
Comment event

%CommentSource%: is "Whistleblower" or "Receiver", just is useful to specify which is the source of the comment.
all the Tip event keywords
Encrypted Comment Event

%CommentContent%: This contain the entire comments content, can be sensitive, can became from either whistleblower and receiver.
File event

%FileName%: The name of the file
%FileType%: the content type of the file
%FileSize%: The size expressed in bytes
all the Tip event keywords
Encrypted File event

(Not yet implemented, %FileDescription%, would contain the description of the file provided by the WB)
Message event

%MessageSource%: is a fixed string, at the moment. just 'whistleblower' can be, because Message are direct between one Receiver and the WB, and only Receiver can get Notification,
all the Tip event keywords
Encrypted Message event

%MessageContent%: This contain the entire messages content, can be sensitive, became directly from the whistleblower.
Non notification template

When a receiver download the full collection of the available files (in .zip format) a file named DESCRIPTION.txt is append to the archive.

This file can be customized in content and has its own set of Keyword (beside the Shared Keywork above)

Collection Archive Description

%FileList%: list of the file download
%FilesNumber%: number of the files
%TotalSize%: total size of the files

