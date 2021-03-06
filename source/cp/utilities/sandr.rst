.. # This source file is part of the open source project
   # ExpressionEngine User Guide (https://github.com/ExpressionEngine/ExpressionEngine-User-Guide)
   #
   # @link      https://expressionengine.com/
   # @copyright Copyright (c) 2003-2018, EllisLab, Inc. (https://ellislab.com)
   # @license   https://expressionengine.com/license Licensed under Apache License, Version 2.0

Data Search and Replace
=======================

.. rst-class:: cp-path

**Control Panel Location:** :menuselection:`Developer --> Utilities --> Search and Replace`

.. Overview

This section of the Control Panel allows you to search for text within
your site and replace it with another piece of text. This search and
replace operation can be performed on your entry titles, within any of
the entry fields, or within your Templates.

.. Screenshot (optional)

.. Permissions

Permission Restrictions
-----------------------

* Access Tools sections: Utilities
* Access Tools sections: Data Operations

Fields
------

.. contents::
  :local:
  :depth: 1

.. Each Field

Search for this text
~~~~~~~~~~~~~~~~~~~~

Here you can input the text for which you would like to search. You must
be very careful about what text you search for. If you input "car", then
words such as "carnivore" and "cartoon" will also be matched. If you
want to make sure you match only the word "car" then you must place
spaces on each side of the term, like " car ". In those cases you need
to make sure that your replacement term also contains the spaces in a
similar fashion or else you won't get the results you expect.

Replace with this text
~~~~~~~~~~~~~~~~~~~~~~

Here you specify what text you would like to replace the text for which
you are searching. Be sure that the syntax you uses matches the "search"
text. For instance, if your search text is for a specific word or phrase
and uses spaces on either side of the search term, then your replacement
text also needs to include those spaces on either side so that the
resulting text has the correct format.

Search and replace in
~~~~~~~~~~~~~~~~~~~~~

This setting consists of a drop-down list of the possible database areas
for which you can perform the search and replace. The list includes:

-  **Site Preferences**: Select a site to search and replace text within
   the site's preferences (including such prefs as those for Channels
   and Upload Directories).
-  **Channel Entry Titles**: Select this to search and replace text
   within the entry titles.
-  **Channel Fields**: Under this heading, each of the available
   :doc:`/cp/channel/fields/index` is listed.
-  **Templates**: Select this to search and replace text within all of
   your Templates.

Current password
~~~~~~~~~~~~~~~~

You must enter your password to search and replace.