.. # This source file is part of the open source project
   # ExpressionEngine User Guide (https://github.com/ExpressionEngine/ExpressionEngine-User-Guide)
   #
   # @link      https://expressionengine.com/
   # @copyright Copyright (c) 2003-2018, EllisLab, Inc. (https://ellislab.com)
   # @license   https://expressionengine.com/license Licensed under Apache License, Version 2.0

###################
System Requirements
###################

**For the best experience**, ExpressionEngine requires:

- `PHP <http://www.php.net/>`_ 7 or newer, running with `PHP-FPM <http://php.net/manual/en/install.fpm.php>`_
- `MySQL <http://www.mysql.com/>`_ 5.6 or newer **OR** `Percona <https://www.percona.com/software/mysql-database/percona-server>`_ 5.6 or newer

.. _server-wizard:

***************************
Server Compatibility Wizard
***************************

If you're not sure whether your server meets the minimum requirements,
the server wizard will run some tests and give you an answer.

-  `Download <https://ellislab.com/asset/file/ee_server_wizard.zip>`_ and unzip the archive.
-  Upload the folder to your server.
-  Point your web browser to the folder. For example: ``https://example.com/ee_wizard``

***********************
Okay, The Bare Minimums
***********************

If you are stuck in an older environment, ExpressionEngine *can* run on PHP 5.6.0+ with 32M of memory, and MySQL 5.5.3+. PHP-FPM is also optional, but `tends to handily outperform mod_php <https://www.cloudways.com/blog/php-fpm-on-cloud/>`_. That said, running older versions not only hurts performance—increasing the cost of your website—but also puts your site **at risk of security vulnerabilities**. The PHP Group will only provide security support for PHP 5.6 `until December 31, 2018 <http://php.net/supported-versions.php>`_. Oracle will also cease providing security support for MySQL 5.5 at the same time.

Why not save yourself the worry and hassle, enjoy a faster and more secure site that costs less to maintain, and upgrade now? Here's an email you can send to your host if they need a little nudge:

.. code-block:: text

  Hey there!

  I'm running the PHP/MySQL based content management system ExpressionEngine, and would like to make sure it's speedy, secure, and making the most efficient use of the resources available on my server.

  Could I speak with someone about moving to an environment that has PHP 7+ and MySQL 5.6+? If they are available, I'd love to use PHP-FPM to implement PHP, and Percona as a drop-in replacement for MySQL, too.

  Thanks!

**********************************
Control Panel Browser Requirements
**********************************

ExpressionEngine's Control Panel targets compatibility with the final-release versions of the web browsers listed here, so it's important to keep your browser up to date. These requirements do not apply to your website, which **you are 100% in control of**, just ExpressionEngine's control panel.

- Chrome
- Safari
- Firefox
- Opera
- Microsoft Edge

.. note:: In all cases, JavaScript must be enabled to use the Control Panel.

*****************
Details and Notes
*****************

.. contents::
  :local:
  :depth: 1

You can safely ignore the rest of this page unless you are experiencing problems, or are a sysadmin setting up a custom environment. All of the following are readily available in most managed environments.

PHP Extensions Required
-----------------------

Though the following are available in PHP by default, some hosts may have them disabled until you ask for them.

- `GD (or GD 2) <http://www.php.net/manual/en/ref.image.php>`_ library
- The `File Information (fileinfo) <http://php.net/manual/en/book.fileinfo.php>`_ PHP extension

.. note:: If you're on MediaTemple you will need `to create a phprc file <http://wiki.dreamhost.com/PHP.ini#How_to_add_a_phprc_file>`_ that contains the following

  ::

    extension = fileinfo.so

PHP Extensions Recommended
--------------------------

These are recommended, but not required.

- The `Internationalization <http://php.net/manual/en/book.intl.php>`_ extension, for full functionality of :doc:`variable modifiers </templates/variable_modifiers>`
- Multibyte String (`mbstring <http://php.net/manual/en/mbstring.installation.php>`_) handling

For full support of multibyte encodings, ask your web host or server admin to set ``mbstring.func_overload`` to ``6`` in your server configuration by editing :file:`php.ini` as shown below::

  ; overload(replace) single byte functions by mbstring functions.
  ; mail(), ereg(), etc are overloaded by mb_send_mail(), mb_ereg(),
  ; etc. Possible values are 0,1,2,4 or combination of them.
  ; For example, 7 for overload everything.
  ; 0: No overload
  ; 1: Overload mail() function
  ; 2: Overload str*() functions
  ; 4: Overload ereg*() functions
  mbstring.func_overload = 6

MySQL Privileges
----------------
The MySQL user connecting to the database must have the following privileges:

- ``SELECT``
- ``INSERT``
- ``UPDATE``
- ``DELETE``
- ``CREATE``
- ``INDEX``
- ``ALTER``
- ``DROP``

Apache Server
-------------

If you are hosted on an Apache server, the ``AcceptPathInfo`` option needs to be enabled for URLs to work properly. Most servers are configured this way by default, but if yours is not, you have a few options:

- Include ``AcceptPathInfo On`` in your ``.htaccess`` file to enable it
- Ask your web host or server admin to enable the option
- Set your site's URLs to use :ref:`query strings <query-strings>`

URL Segment Support
-------------------

If the :ref:`Server Compatibility Wizard <server-wizard>` lists URL Segment Support as *Unsupported*, you will need to set your site's URLs to use :ref:`query strings <query-strings>`.

MAMP
----

|MAMP|_ (external link) can be very convenient for local development, but it has some quirks. If you are using |MAMP|, you will need to use PHP 7+ due to outdated cURL and OpenSSL libraries that |MAMP| ships with its older versions of PHP.

.. |MAMP| replace:: :abbr:`MAMP (My Apache - MySQL - PHP)`
.. _MAMP: https://www.mamp.info/
