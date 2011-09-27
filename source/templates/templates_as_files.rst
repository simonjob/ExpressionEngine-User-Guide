Saving Templates to Text Files
==============================

ExpressionEngine supports saving Template Groups and Templates as
regular folders and files on your server, so that you can use your
preferred text editor (e.g. Dreamweaver, Coda, BBEdit, etc.) to edit
Templates and then FTP the changes to the server.

-  Template Group folder names must end with *.group* and the preceding
   name must be URL safe (contain only letters, numbers, dashes,
   underscores and dots).
-  Template Files must be in an appropriately named group folder. They
   must end with an approved extension and must be URL safe. Approved
   extensions and the associated template type they will result in are:

   -  *.html* creates a 'webpage' template type
   -  *.feed* creates an 'rss' template type
   -  *.css* creates a 'css' template type
   -  *.js* creates a 'js' template type
   -  *.xml* creates an 'xml' template type

Enabling Saving Templates as Files
----------------------------------

1. Prepare the template folder
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ExpressionEngine ships with a system/expressionengine/templates folder
that can be used to store saved template files. You can create and use a
different folder elsewhere if you wish.

**NOTE:** ExpressionEngine will not create Template Group folders
directly in this folder, but rather in a subfolder named after the Site
Short Name, which defaults to "default\_site" on a single installation,
e.g.:
/home/usr/domain.com/public\_html/system/expressionengine/templates/*default\_site*/my\_template\_group.group.
This adds clarity and prevents file conflicts should you ever use the
Multiple Site Manager.

2. Set folder permissions
~~~~~~~~~~~~~~~~~~~~~~~~~

Make the folder writable by setting its permissions to 777 (or
equivalent) so that ExpressionEngine will be allowed to save the files
as well as recreate your Template\_Group/Template structure.

3. Set Template Preferences
~~~~~~~~~~~~~~~~~~~~~~~~~~~

From the Control Panel, go to Design > Templates > `Global
Preferences <../cp/design/templates/global_template_preferences.html>`_.

#. Set **Allow templates to be saved as files?** to "Yes".
#. Set the **Basepath to Template File Directory**: You must place the
   *server path* to the directory you created above in this preference.

It is important that you use the server path for the preference and not
a URL. Server paths will vary from server to server, so contact your
host if you are unsure of what it should be. A server path often looks
similar to:
/home/usr/domain.com/public\_html/system/expressionengine/templates

Creating and Synchronizing Templates and Files
----------------------------------------------

Once your site is set up to save templates as text files, there are
three ways to create templates and their related files.

Creating Flat Files Via the Template Editor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If saving templates as text files is enabled, you will see a new
checkbox become available at the bottom of your `Template editing
page <../cp/design/templates/edit_template.html>`_. When you submit your
template with the box checked, the Template will be saved as a file (in
addition to updating the database).

**Note:** The template edit page will load the latest version of the
template based on edit date. If the flat file has been edited since the
last database version was saved, the editor will load the content from
the file rather than the database. The editor will indicate whether the
content was loaded from the database of the flat file. If the editor
loads from file, until you click "save", the database will still contain
the last (outdated) version you saved via the Control Panel.

Creating Templates Via Flat Files
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When you load either the `Template
Manager <../cp/design/templates/templates.html>`_ or the `Synchronize
Templates page <../cp/design/templates/synchronize_templates.html>`_
ExpressionEngine automatically searches your template directory and
creates new template groups and templates for any appropriately named
files and folders that do not already have an associated template.

Synchronizing Templates
~~~~~~~~~~~~~~~~~~~~~~~

On occasion, you may have a number of templates flagged to 'save as
file' but no associated files. Rather than going to each template
individually and saving it, you can `Synchronize
Templates <../cp/design/templates/synchronize_templates.html>`_ and any
missing files for templates set to 'save files' will be recreated based
on the database version of the template. This will also batch update the
database copies of any templates whose files are newer.

Running your Site with Flat File Templates
------------------------------------------

If a file exists for a template flagged to save templates as text files,
ExpressionEngine will use the file version of the Template instead of
the database whenever your pages are viewed. Because ExpressionEngine is
using the file version, you can then use an external editor to make
changes to the file without using the Control Panel.

Saved Templates and the Multiple Site Manager
---------------------------------------------

Sites under the Multiple Site Manager have their own preferences for
saving templates as text files. As such, when setting up a new Site
under the Multiple Site Manager, you must set up a new location for
saving those templates.

When importing or duplicating to a new Site in the Multiple Site
Manager, if you wish to use existing templates which are saved as text
files, then the template directory must be manually copied to the
directory for the new Site.