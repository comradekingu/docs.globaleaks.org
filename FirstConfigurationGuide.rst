=========================
First Configuration Guide
=========================

You have just installed GlobaLeaks and you have to make it capable of receiving anonymous submissions that get dispatched to configured recipients. To achieve this you have to access to the Platform Wizard.


STEP 1: Access Platform Wizard
-------------------------------

You can reach the Platform Wizard from your browser in two ways:


  - From the same computer you installed GlobaLeaks on: http://127.0.0.1:8080/#/wizard

  - From your Tor Hidden Service hostname with the Tor Browser: Example: http://2rwejhgkn3c2z56g.onion/#/wizard


(You can find the onion address of your GlobaLeaks installation in /var/globaleaks/log/globaleaks.log some minutes after GlobaLeaks has been launched, following a successful run of the installation script)

Note that loading the interface may take a while, due to the high latency of Tor Hidden Service


This will bring you to the page for "Step-by-step setup"


.. image:: wizard0.png


STEP 2: Choose the primary language for the site
------------------------------------------------

In this section of the wizard you select the language which will be used as primary language for your GlobaLeaks installation.
The default choice is English, but many others lanaguages are available and more are expected to be available in the future.


.. image:: wizard1.png


Once selected, click on the "next step" button to access the General section of the wizard.


STEP 3: Configure Project's name and Description
------------------------------------------------

This part of the wizard is where you set up name and description of the project. 


.. image:: wizard2.png


Choose a name and description that best describes your project to the intended audience of your GlobaLeaks installation.

When done, click on "Next step" button to access to the section where admin credentials are configured.


STEP 4: Configure admin account
-------------------------------

In this part of the wizard email addreess and password for the admin is set up.

Keep in mind choosing a strong password in order to protect this sensitive account; an indication of the strength of the choosen password is shown to guide you in this task.


.. image:: wizard3.png


In order to proceed, click on the "Next step" button.


STEP 5: Setting up a Context
-----------------------------

In this section of the configuration wizard you set up the context (todo: insert cross-reference with matching term in glossary).


.. image:: wizard4.png


Click on the "Next step" button to proceed.


STEP 6: Setting up a Recipient for the Context
-----------------------------------------------

This section of the wizard lets you define recipients (todo: insert cross-reference with matching term in glossary) for the named context.


.. image:: wizard5.png


Note that the recipient's password is set to a pre-defined value; the configured recipient will receive an email at the email address inserted here, to change this default password to a more secure one.

Click on the "Next step" button to proceed; a page will be presented to notify you of everything having gone well, from which you can proceed to configure the details of your GlobaLeaks installation by accessing the Admin interface through the "Go to Admin interface" button.

.. image:: wizard6.png

