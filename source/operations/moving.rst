Moving ExpressionEngine to Another Server
=========================================

As you use ExpressionEngine, you'll probably find the need to move the
project to another server at some point. A variety of possible reasons
include:

-  You developed the site locally, and now it's time to go live on a
   production server!
-  The site's traffic is growing, and you need to move to a server
   that's better able to handle the demand.
-  You want to duplicate your existing site to create a testing
   environment (for troubleshooting problems or testing new features).
-  You want to upgrade ExpressionEngine in a safe environment, test the
   site, and then move it to your production server.

All great reasons to move your ExpressionEngine installation, of course.
And since development and upgrades should never be performed on a live
installation, it's important to know how to copy and migrate an
installation to another server.

Just as it is with many things related to ExpressionEngine, there are a
variety of ways to migrate between servers with ExpressionEngine. This
article outlines the basic procedure for moving ExpressionEngine to
another server. Please note that you may need to perform additional
steps if you are using any third-party add-ons that store their own path
configurations.

1. Verify Server Compatibility
------------------------------

Upload the :doc:`ExpressionEngine Server Wizard
</installation/requirements>` to the new server and run it to verify
basic compatibility with ExpressionEngine.

2. Synchronize Templates
------------------------

You can skip this step if you are not saving templates as files.

From the Control Panel, go to :menuselection:`Design --> Templates -->
Template Manager --> Synchronize Templates`, select all templates and
click Submit.

3. Clear Caches
----------------

Go to :menuselection:`Tools --> Data --> Clear Caching`. Select **All
Caches** and click Submit.

4. Back-up Database and Files
-----------------------------

-  Back-up your existing ExpressionEngine database.
-  Back-up all existing ExpressionEngine files and folders.

5. Prepare the New Database
---------------------------

Create a new, empty database on the new server and import the back-up
file you created in **Step 4** into it. Typically this will be a SQL
file (or a ZIP file containing the SQL file).

6. Copy Files and Folders
-------------------------

Copy all ExpressionEngine files and folders from the old server to the
new server. At a minimum, this will typically include:

-  admin.php
-  index.php
-  images/
-  system/
-  themes/

Your folder structure may look a bit different if the site was
configured to run with the system folder renamed or above web root.

7. Verify File Permissions
--------------------------

The following permissions are typical for UNIX-based hosts. You may want
to check with your host to see if more restrictive permissions can be
used to allow PHP to write to files (666) and folders (777). On Windows
servers the following will not apply, but you will need to ensure that
the files and folders are writable by ExpressionEngine. You may need to
contact your host for this.

-  Ensure the following files are set to **666**:

   -  system/expressionengine/config/config.php
   -  system/expressionengine/config/database.php

-  Ensure the following folders are set to **777**:

   -  system/expressionengine/cache/
   -  images/avatars/uploads/
   -  images/captchas/
   -  images/member\_photos/
   -  images/pm\_attachments/
   -  images/signature\_attachments/
   -  images/uploads/

8. Update database.php
----------------------

Open system/expressionengine/config/database.php and update the settings
to match those of the new server.

9. Verify index.php and admin.php
---------------------------------

Verify that your site's root index.php and admin.php files have the
correct settings for the new server.

10. Log In and Update Paths
---------------------------

At this point, you should be able to log in to the Control Panel using
admin.php. If not, please verify that the settings made in **Steps 8**
and **9** are correct.

There are typically several areas of the Control Panel in which paths
may need to be updated, including:

-  :menuselection:`Admin --> General Configuration`
-  :menuselection:`Admin --> Security and Privacy --> Captcha Preferences`
-  :menuselection:`Admin --> System Administration --> Emoticon Preferences`
-  :menuselection:`Content --> Files --> File Upload Preferences`
-  :menuselection:`Members --> Preferences`
-  :menuselection:`Design --> Templates --> Global Preferences`
-  :menuselection:`Admin --> Channel Administration --> Channels`

You can also set many of these paths in your config.php file using
configuration variables::

	$config['site_url'] = "http://example.com/";
 
	$config['tmpl_file_basepath']   = "/home/user/example.com/templates/";
	 
	$config['theme_folder_url'] = "http://example.com/themes/";
	$config['theme_folder_path'] = "/home/user/example.com/themes/";
	 
	$config['captcha_url'] = "http://example.com/images/captchas/";
	$config['captcha_path'] = "/home/user/example.com/images/captchas/";
	 
	$config['emoticon_url'] = "http://example.com/images/smileys/";
	 
	$config['avatar_url'] = "http://example.com/images/avatars/";
	$config['avatar_path'] = "/home/user/example.com/images/avatars/";
	 
	$config['photo_url'] = "http://example.com/images/member_photos/";
	$config['photo_path'] = "/home/user/example.com/images/member_photos/";
	 
	$config['sig_img_url'] = "http://example.com/images/signature_attachments/";
	$config['sig_img_path'] = "/home/user/example.com/images/signature_attachments/";
	 
	$config['upload_preferences'] = array(
	    1 => array(                                                            // ID of upload destination
	        'name'        => 'Image Uploads',                          // Display name in control panel
	        'server_path' => '/home/user/example.com/images/uploads/', // Server path to upload directory
	        'url'         => 'http://example.com/images/uploads/'      // URL of upload directory
	    )
	);

11. Clear Caches (Again!)
-------------------------

Go to :menuselection:`Tools --> Data --> Clear Caching`. Select **All
Caches** and click Submit.

You're Done!
------------

At this point, your site should be fully functional. Check to make sure
that there are no links still pointing to the previous server. It is
recommended that links be generated using the :doc:`{path}
</templates/globals/path>` or :ref:`{site\_url} <global-site_url>`
variables for maximum portability.