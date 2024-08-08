*************
Menu Add-ons
*************

|  Menu add-ons are apps thats are either not in the menu by default or archived and could be deprecated.  https://github.com/fusionpbx/fusionpbx-apps
  
|

*Acl*
----

| **deprecated** (Now part of Advanced -> Access Controls)

cdr
----

| Optional version of Apps -> Call Detail Records.


content
-------

| Manage Content for any page in the interface.

fifo_agents
-----------

get_call_details
----------------

| Get call details for active calls results are in json.

hot_desking
-----------

Code integrated starting version 4.0.0 (Goto Accounts > Devices for current hot_desking) 

hunt_groups
-----------

|  **deprecated** (Now part of Appsv-> Ring Groups) A Hunt Group is a list of destinations that can be called in sequence or simultaneously.

invoices
--------

| A handy way to make an invoice or quote PDF for clients.

languages
---------

| initial version of languages.

php_service
-----------

| Manages multiple dynamic and customizable services. There are many possible uses including alerts, ssh access control, scheduling commands to run, and many others uses that are yet to be discovered.

profiles
--------

| Use this to configure your SIP profiles.

roku
-----

schemas
-------

| Provides the ability to quickly define information to store and dynamically makes tools available to view, add, edit, delete, and search.

servers
-------

signup
-------

| Allows customers on the internet to signup for a user account.

sipml5
-------

| Add sipml5 an optional webrtc client.

soft_phone
-----------

| Freeswitch Softphone used with  mod_portaudio.
| See http://wiki.freeswitch.org/wiki/Mod_portaudio and http://wiki.freeswitch.org/wiki/Freeswitch_softphone

tickets
--------

| Simple Ticket Tracking System To allow customer Support

users_bulk_add
---------------

voicemail_msgs
--------------

| Voicemails can be listed, played, downloaded and deleted. (Now part of Apps -> Voicemail

voicemail_status
----------------

| Shows which extensions have voicemails and how many.

xmpp
----

| XMPP Manager is an optional menu item. In order to have the option for XMPP Manager there are a few step to take to enble XMPP. Utilizes the Jingle protocol. Jingle is an extension to the Jabber/XMPP protocol.
| http://docs.cclpbx.com/en/latest/applications_optional/xmpp.html

Zoiper
-------

| QR and app provisioning with Zoiper

| This menu add-on will enable the abliity to do QR provisioning from IOS or android Zoiper app.  Zoiper has designed the process in a way that is cross platform.  cclpbx has the ability to click the extension you want to provision and a link wil open to either download the app on multiple platforms or if you have the app installed on a mobile device you can use the QR code scanner to scan a QR image and the mobile is ready to use.

| We will walk through the process


Zoiper.com account setup
^^^^^^^^^^^^^^^^^^^^^^^^

| There are two parts to make this function. http://oem.zoiper.com and cclpbx menu add-on.

| This all adds a one-click install for both the Desktop and Mobile Zoiper APPs in the User Portal. The page is accessible by end users.

| This can be done with the FREE Zoiper OEM account or can use the paid versions for more customization like branding.

| 1. Go to: https://oem.zoiper.com/
| 2. Sign up for Login
| 3. Configure your Desktop and Mobile Apps with the information you want.
| 4. Then click "CONFIGURE" Under Desktop. 
| 5. This will give you a LINK with a PAGE ID:(32 character)
| 6. https://www.zoiper.com/en/page/MYPAGEID?u=&h=&p=&o=&t=&x=&a=&tr="
| 7. Copy the page ID

|

Zoiper menu add-on for cclpbx
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

| On your server

::

 git clone https://github.com/fusionpbx/fusionpbx-apps
 cp -R cclpbx-apps/zoiper /var/www/fusionpbx/app
 chown -R www-data:www-data /var/www/fusionpbx/app/zoiper

| 1. Log into the cclpbx webpage
| 2. Advanced -> Upgrade
| 3. Menu Defaults and Permission Defaults.
| 4. Log out and back in

| Advanced -> Default Settings

| **Note** **MYPAGEID** and **provider_id** are two different sets of characters.  You can also find these by going into the oem.zoiper.com login and click "view" on the moblie section.


.. image:: ../_static/images/fusionpbx_zoiper9.jpg
        :scale: 75%

| **provider_id**

::

 provider_id
 The Do It Yourself way: make your own page with instructions
 
 If you want to customize this page, you can do so, just make sure to embed this html code on your website:
 <img src="https://oem.zoiper.com/qr.php?provider_id=>>>>>>>09876543210987654321098765432199<<<<<<<&u=&h=&p=&o=&t=&x=&a=&tr=" alt="QR image"  />

| **MYPAGEID**

::

 MYPAGEID
 The easy way: send your customers to our landing page
 Add a link on your website to this step by step tutorial on our website : (**click here** to see it in action).
 <a href="https://www.zoiper.com/en/page/>>>>>>>>c1234567890123456789012345678901<<<<<<<?u=&h=&p=&o=&t=&x=&a=&tr=">Configuration instructions for Android and iOS</a>

::

 Add a Default Setting
 Category: zoiper
 Subcategory: provider_id(32 character)
 Type: text
 Value: MYPAGEID(32 character)
 Enabled: True
 Save

| Goto Apps -> Zoiper
| Superadmin will see a list of ALL USER EXTENSIONS
| Users will only see the extensions assigned to them.

| Click on a link and it will take you to the Zoiper Site. Follow instructions there to download and install.

