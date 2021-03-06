.. # This source file is part of the open source project
   # ExpressionEngine User Guide (https://github.com/ExpressionEngine/ExpressionEngine-User-Guide)
   #
   # @link      https://expressionengine.com/
   # @copyright Copyright (c) 2003-2018, EllisLab, Inc. (https://ellislab.com)
   # @license   https://expressionengine.com/license Licensed under Apache License, Version 2.0

Channel Settings Tab
====================

.. rst-class:: cp-path

**Control Panel Location:** :menuselection:`Developer --> Channels --> New/Edit Channel --> Settings`

.. Overview

This tab allows you to edit the preferences and settings associated with the
channel. They include General, Administrative, Channel Posting, and Comment
Posting settings.

.. Screenshot (optional)

.. Permissions

Permission Restrictions
-----------------------

* Access settings: Design & Content
* Channels: Create Channels
* Channels: Edit Channels


Fields
------

.. contents::
  :local:
  :depth: 1

.. Each Field


.. note:: We recommend using the default base URL variable ``{base_url}`` defined in :doc:`URL and Path Settings </cp/settings/urls>` in your URL settings.

Description
~~~~~~~~~~~

A short description of the channel. Spaces, punctuation, and other
special characters are allowed. This is used, for example, in RSS feeds.

XML language
~~~~~~~~~~~~

This preference determines the XML language setting that you can use for
your channel pages. This information is available as a variable for use
in the channel Templates. A drop-down list is available for selection.

Channel
~~~~~~~

The full URL to the main page for this channel.

Comment form
~~~~~~~~~~~~

The full URL to the "comments" page for this channel. The URL should
include the Template Group and Template. For example:
https://example.com/channel/comments/

Search results
~~~~~~~~~~~~~~

The full URL where you would like search results from this channel to be
pointed. The URL should include the Template Group and Template. For
example, if you wish that links off the search results page point to
your "comments" Template you might use:
{base_url}/index.php/channel/comments/.

RSS feed
~~~~~~~~~

The URL where you can view the RSS feed for this channel. For example:
https://example.com/channel/rss_2.0

.. _channel_prefs_preview_url:

Preview URL
~~~~~~~~~~~

The template path, or route, to use for :ref:`entry_live_preview` in this Channel. You
can use the variables ``{entry_id}`` and ``{url_title}`` which will be replaced
with the entry's ID or URL Title when rendering your template.
For example: ``blog/entry/{url_title}``

.. note:: If an Entry has a Page URI it will be used instead of the Preview URL for the channel.

Generated title
~~~~~~~~~~~~~~~

When a new entry is created or previewed, this value will be inserted by
default in the Title field. This is helpful if you wish every entry in a
channel to have the titles follow a certain format. The automatic URL
Title creating javascript for the Publish page will ignore this text
during processing.

URL title prefix
~~~~~~~~~~~~~~~~~

When a new entry is created or previewed, this value will be appended to
the beginning of the url_title value, which will help you insure that
url_titles are unique between channels.

Status
~~~~~~

The default status for new channel entries. The available options depend
on what :doc:`Statuses <tab-statuses>` the channel is assigned to
use.

Category
~~~~~~~~

The default category for new channel entries. The available options
depend on what :doc:`Category Group <cat/index>` the channel is
assigned to use and which categories are defined for that group. In
addition to the categories from that group, the "None" option is also
available, in which case no category will be selected by default.

Search excerpt
~~~~~~~~~~~~~~

You can specify which field from your entries to use in search result
excerpts. The list is dynamically populated depending on which :doc:`Fields <fields/index>` the channel is assigned to use. Only fields that have been set as "searchable" will be included.

HTML formatting
~~~~~~~~~~~~~~~

This setting determines how raw HTML code within entries is handled.
There are three options:

#. **Convert HTML into character entities**: This will convert the HTML
   tags so that they will display as plain text on a page when viewed.
   This would be useful if you want to display example code often.
#. **Allow only safe HTML**: This will allow "safe" HTML (<b>, <i>,
   <em>, <del>, <ins>, <strong>, <pre>, <code>, <blockquote>, <h2>,
   <h3>, <h4>, <h5>, <h6>) to be kept so that they are interpreted by
   the browser when the entry is viewed. All other HTML is converted to
   character entities and the raw code will be seen upon viewing.
#. **Allow ALL HTML**: This leaves the HTML code as written and the code
   will then be interpreted by the browser when the entry is viewed.

Show extra publish controls?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When set to yes, a second set of publish controls will appear at the top of the publish form for this channel.

Allow image URLs?
~~~~~~~~~~~~~~~~~

You can determine whether or not you want people to be able to display
images within your entries by using the URL for the image. If "Yes" is
selected for this option, people can display images as inline content in
your channel. If the setting is "No" then images will not be allowed.

Render URLs and Email addresses as links?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When this option is set to "Yes", any full URLs or email addresses will
be automatically formatted as a valid HTML link to the address. If the
option is "No" then the URL or email address will be treated and
displayed as plain text.

Status
~~~~~~

Status assigned to all new entires in the channel.

Author
~~~~~~

Default author for guest entries posted via Channel Form.

Allow guest submissions?
~~~~~~~~~~~~~~~~~~~~~~~~

When set to yes, unregistered users will be able to submit forms for this channel.

Enable entry versioning?
~~~~~~~~~~~~~~~~~~~~~~~~

When set to enable, ExpressinEngine will save revisions of each entry for this channel.

Maximum versions per entry
~~~~~~~~~~~~~~~~~~~~~~~~~~

Maximum number of revisions to be saved per entry.

Enable author notification?
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Whenever a new comment is submitted, the author of the entry can be
notified. An email will be sent to the email address associated with the
author member in the system.

Enable channel entry notification?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If the previous setting is set to "Yes", then these are the recipients
of the email alert. You may define a single email address or list
multiple addresses by separating them with a comma. Ex:
"admin@example.com, joe@example.com"

Enable comment notification?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can specify a list of email addresses to receive notifications when
a comment is posted. This setting determines whether or not the list
will receive the updates. The addresses are specified in the next
setting.

If the previous setting is set to "Yes", then these are the recipients
of the email alert. You may define a single email address or list
multiple addresses by separating them with a comma. Ex:
"admin@example.com, joe@example.com"

.. _channel_prefs_allow_comments:

Allow comments?
~~~~~~~~~~~~~~~

Determines whether or not comments are allowed in this channel.

Allow comments default?
~~~~~~~~~~~~~~~~~~~~~~~

When set to yes, the "Allow comments" option on the publish page will be set to
"yes" by default

Require membership?
~~~~~~~~~~~~~~~~~~~

Determines whether visitors to the website must be members in order to
post. If this preferences is set to "Yes" and an unregistered visitor
attempts to post a comment the comment will not be accepted and the
visitor will receive a message.

Require Email?
~~~~~~~~~~~~~~

You can optionally require that anyone posting comments must list an
email address. You can determine in your
:doc:`/cp/design/index` whether or not the address is shown
publicly, but requiring an email address in order to post comments can
help reduce the number of "spam" comments you receive since the visitor
must submit a valid email address.

Moderate comments?
~~~~~~~~~~~~~~~~~~

If this option is enabled, then comments will not immediately appear on
the site. Instead, the comments will go into a queue and await
review/moderation by an administrator.

Member Groups (such as the SuperAdmin Group by default) can be set to
bypass comment moderation and have their comments posted immediately.
That option can be set at :menuselection:`Members --> Member Groups`.

Maximum characters allowed?
~~~~~~~~~~~~~~~~~~~~~~~~~~~

You may set a maximum number of characters allowed in any comment.
Setting this preference to 0 (zero) will not place a restriction on the
number of characters allowed.

Comment time limit
~~~~~~~~~~~~~~~~~~

This is the optional number of seconds that must lapse after a comment
is posted before that same user can post another comment. This setting
can help reduce comment "spam". The preference can be left blank or set
to 0 (zero) if you do not want to impose a limit.


Comment expiration
~~~~~~~~~~~~~~~~~~

The number of days after an entry is posted in which to allow comments.
After that period has expired, the entry will be closed to commenting
and the comment form will no longer appear. Existing comments will still
be displayed. Enter 0 (zero) for no expiration. Note that this
preference sets the *default* setting for the channel. The setting can
be overridden and changed on a per-entry basis.

You may override this setting in the
:doc:`/comment/control_panel/index` section of the Comment
Module so that comments are set to be moderated rather than closed once
the expiration period is passed.

If you also select the checkbox accompanying this setting, then all
existing entries in this channel will be updated to reflect the new
setting when you submit.

Text formatting
~~~~~~~~~~~~~~~

This setting determines how comments are formatted by the system. There
are three possible choices:

#. **None**: No automatic formatting is done; the comment is left as-is.
   This could be useful if you want people to be able to use full HTML
   in their comments.
#. **xhtml**: Comments will be formatted as valid XHTML. Text blocks
   with double line breaks will be turned into paragraphs, line breaks
   will be replaced by <br /> tags, special characters will be formatted
   as character entities, etc.
#. **Auto <br />**: All line breaks in the comment will be converted
   into <br /> tags. This includes any line breaks that may occur inside
   HTML code, which could cause unexpected displays.

HTML formatting
~~~~~~~~~~~~~~~

Like the channel setting, this preference determines how raw HTML code
within comments is handled. There are three options:

#. **Convert HTML into character entities**: This will convert the HTML
   tags so that they will display as plain text on a page when viewed.
   This would be useful if you want to display example code often.
#. **Allow only safe HTML**: This will allow "safe" HTML (<b>, <i>, <u>,
   <em>, <strike>, <strong>, <pre>, <code>, <blockquote>) to be kept so
   that they are interpreted by the browser when the entry is viewed.
   All other HTML is converted to character entities and the raw code
   will be seen upon viewing. Note that while <h2>, <h3>, <h4>, <h5>,
   <h6> are considered "safe" in channel entries, they are not allowed
   in comments.
#. **Allow all HTML (not recommended)**: This leaves the HTML code as
   written and the code will then be interpreted by the browser when the
   entry is viewed. This is generally not recommended since visitors
   would be able to submit HTML code which could drastically alter the
   display of your webpage.

Allow image URLs?
~~~~~~~~~~~~~~~~~

You can determine whether or not you want people to be able to display
images within comments by using the URL for the image.

Render URLs and Email addresses as links?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When this option is set to "Yes", any full URLs or email addresses will
be automatically formatted as a valid HTML link to the address. If the
option is "No" then the URL or email address will be treated and
displayed as plain text.
