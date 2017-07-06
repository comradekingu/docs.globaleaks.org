============================
Advanced Configuration Guide
============================

https://github.com/globaleaks/GlobaLeaks/wiki/Advanced-customization-guide
last edit 2014

The Advanced Customization Guide enables you to customize every aspect of the GlobaLeaks application features of the application like for example:

tweaking every settings;
adding additional text or features by raw edit of the application core. This procedure is not immediate like modifying a single .html file because "GlobaLeaks Client" is a javascript application Optimized for use over Tor Hidden Service, through a "build process"; So it's suggested to follow this guide only to advanced GlobaLeaks users aware of the possible security risks of the procedure.
This is not the best way to customize Globaleaks.

For the safe way to do it please refer to the Basic Customization Guide.

The steps needed to accomplish the Advanced Customization Guide are the following:

Development Environment
We a Development environment should be installed on a different server and it's needed mostly to develop the template because it runs immediately from sources. That way you can iteractively modify it and hit Refresh on the browser, without having to go through the client build process. Then, when you are satisfied with your custom template developed, you can move to your production server and follow the "automatic build procedure" just to build it.

Customize the client
With this you will be able to preview in real time your template (without having to build it) on your local system. The Sysadmin can provide to the Web Designer access to the template file via FTP/SFTP to facilitate customization workflow.

First you need to Setup the GlobaLeaks Development Environment with GlobaLeaks Client running from source code. Then, you will then by able to preview your template by running:

./backend/bin/globaleaks -z -k9 -d -t -n -l DEBUG
And then connecting to 127.0.0.1:8082.
