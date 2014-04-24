Metaweblog API / Movable Type
=============================

.. contents::
   :local:
   
Introduction
------------

The Metaweblog API (Application Programming Interface) is an interface
or "protocol" that allows other programs to interact with ExpressionEngine.
In practical terms, it allows you to post and edit entries using a Metaweblog
API-compatible program of your choosing instead of the ExpressionEngine
Control Panel.

ExpressionEngine supports the Metaweblog API as well as an extension to
it known as the Movable Type API. It is important to understand that the
Metaweblog API was originally designed for posting to one Channel Field, and does
not support comments, etc. Thus, it is typically only used for simple entry
posting purposes. The Movable Type API is slightly more flexible in that it
supports posting content to up to four Channel Fields.


Configuration
-------------

The Metaweblog API Control Panel is accessed via
:menuselection:`Add-Ons --> Modules --> Metaweblog API` in the Control Panel.
This page lists all of your existing configurations as well as the URL to be
used for connecting to that configuration with your Metaweblog API-compatible
software.

Click on a configuration's name to edit it. The following options are available:

Configuration Name
~~~~~~~~~~~~~~~~~~

The name of this configuration.

Use Default Text Formatting Preferences
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If Yes, the Channel Fields' content will be sent as if they are being displayed
on a webpage, with the field's Text Formatting preference respected. If No, the
fields' content will be sent untouched.

The "No" setting is useful when you want to publish and edit content in its "raw"
state with your software, regardless of how it will actually appear on the site.

Entry Status
~~~~~~~~~~~~

Choose the Entry Status for all entries submitted using this
Configuration. If you choose the 'Do Not Set Status' option, then
whatever the Client sends for status (open or closed) will be accepted.

Channel Field Group
~~~~~~~~~~~~~~~~~~~

Here you choose the Field Group to use for this Configuration. This
choice determines which fields are available for selection in the
following preferences.

Excerpt Field
~~~~~~~~~~~~~

Here you determine which field from your Field Group corresponds to the
"Excerpt Field" in your Metaweblog API-compatible program. Only
text-type fields are available for selection. This field is only
available when using the Movable Type API.

Content Field
~~~~~~~~~~~~~

Here you determine which field from your Field Group corresponds to the
"Content Field" in your Metaweblog API-compatible program. Only
text-type fields are available for selection.

More Field
~~~~~~~~~~

Here you determine which field from your Field Group corresponds to the
"More Field" in your Metaweblog API-compatible program. Only text-type
fields are available for selection. This field is only available
when using the Movable Type API.

Keywords Field
~~~~~~~~~~~~~~

Here you determine which field from your Field Group corresponds to the
"Keywords Field" in your Metaweblog API-compatible program. Only
text-type fields are available for selection. This field is only
available when using the Movable Type API.

Upload Folder for File Uploading
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If your Metaweblog API-compatible program allows you to upload files,
you may specify into which folder you want files uploaded. Your
choices are determined by what you have set up at
:menuselection:`Content --> Files --> File Upload Preferences`.

The user sending the files via the Metaweblog API must have permission to
upload to that folder. If you do not wish to allow uploads via the Metaweblog API,
select "None".

.. note:: When using an upload folder with the MetaWeblog API, make sure to use
   absolute paths.

.. note:: Many Metaweblog API-compatible programs do not support a file upload
   feature. You may also encounter issues when uploading very large files.

Connecting with a Metaweblog API Compatible Program
---------------------------------------------------

In general, you will use the URL of your desired configuration as shown
on the Metaweblog API Control Panel page at :menuselection:`Add-Ons -->
Modules --> Metaweblog API` to connect with your program. Below is
information specific to some common programs.

MarsEdit
~~~~~~~~

#. Create a New Blog in MarsEdit.
#. Name it anything you wish, enter the URL of your site's homepage, and
   click **Finish**.
#. Click **Edit Settings** on the next dialog that appears.
#. For *System Name*, choose **ExpressionEngine**.
#. For *System API*, ensure **Movable Type API** is selected.
#. For *API Endpoint URL*, enter the URL of your desired configuration
   as shown on the Metaweblog API Control Panel page at
   :menuselection:`Add-Ons --> Modules --> Metaweblog API`.
#. For *Blog ID*, enter the **Channel ID** of the Channel you'll
   be posting to.
#. Click **OK**, then right-click on the newly created Blog in the
   MarsEdit sidebar and choose **Enter Password...**
#. Enter the **username** and **password** for your ExpressionEngine
   account.
#. You should now be able to edit and post entries using MarsEdit.

Ecto
~~~~

#. Click **New Account**.
#. For *System*, choose **ExpressionEngine** or **MovableType**.
#. For *Access Point*, enter the URL of your desired configuration
   as shown on the Metaweblog API Control Panel page at
   :menuselection:`Add-Ons --> Modules --> Metaweblog API`.
#. Enter the **username** and **password** for your ExpressionEngine
   account.
#. At first, ecto will show the existing entries from all Channels
   you have access to. In the sidebar on the left side of ecto's main
   screen, click the triangle next to your ExpressionEngine site and
   click the Channel that corresponds to the **Channel Field Group**
   you selected for this configuration in ExpressionEngine's
   Metaweblog API Control Panel page. Attempting to publish to or
   edit entries from other Channels may result in unexpected behavior.
#. You should now be able to edit and post entries using ecto.