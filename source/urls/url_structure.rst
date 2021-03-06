.. # This source file is part of the open source project
   # ExpressionEngine User Guide (https://github.com/ExpressionEngine/ExpressionEngine-User-Guide)
   #
   # @link      https://expressionengine.com/
   # @copyright Copyright (c) 2003-2018, EllisLab, Inc. (https://ellislab.com)
   # @license   https://expressionengine.com/license Licensed under Apache License, Version 2.0

URL Structure
=============

Pages (Templates) are organized in Template Groups. To access a Template
within a Template Group you'll use this URL structure::

	https://example.com/template_group/template

For example: If you want to access the "archives" Template within the
"site" Template Group you'll use this::

	https://example.com/site/archives

The Concept
-----------

The goal was to make the URLs produced by ExpressionEngine search-engine
friendly by making the URL structure mimic a traditional *static* site.
In order to accomplish this, the use of query strings was eliminated
from the URLs.

Most dynamic publishing systems use query strings. That is, URLs that
look like this:

.. code-block:: none

	https://example.com?id=2&page=1

Notice the question mark and ampersand? Those are part of a "query
string". These enable dynamic systems to fetch and display specific
information. Query strings, however, are disliked by search engines,
which limit the amount of dynamic information they catalog. For that
reason, query strings have been eliminated completely from
ExpressionEngine. Instead, its URLs are segment driven, like this::

	https://example.com/site/archives

Viewing your Site
-----------------

Because you don't actually have physical pages on your site, the URL you
use will determine what you see on your site. At its simplest, you
access pages on your site using this URL formula:

https://example.com/template\_group/template

Notice that the Template Group and Template are contained in the URL. An
Example: Let's say you create a Template Group called "channel", and
within it you create a Template called "about\_me". To access it you
will use the following URL:

https://example.com/channel/about\_me

If you only specify the Template Group in the URL (and leave off a
Template name), EE assumes you want to show the "index" template for
that group:

https://example.com/channel

The above URL is identical to doing this:

https://example.com/channel/index

.. note:: It is best if you **always** specify the Template
   Group name when you access content.

.. _entries-and-other-things:

Entries and Other Things
------------------------

That isn't all, though. You'll often have URLs on your site that point
to a specific channel entry, category, or other things. For instance,
you might have a URL like this:

https://example.com/channel/comments/147

This URL tells EE to display the channel entry number 147 using the
"comments" Template in the "channel" Template Group. So, EE knows what
to display and where/how to display it. You can also use a "URL Title"
to indicate a specific entry instead of the entry number. URL Titles are
specified when you create an entry. So, the URL might be:

https://example.com/channel/comments/my\_url\_title

Again, "channel" is the Template Group, "comments" is the Template, and
now "my\_url\_title" is the URL Title for the entry to be displayed.
Similarly, you might display a single category in your archives:

https://example.com/channel/archives/C13

Here, the URL indicates to display the category with the Category ID of
"13" using the "archives" Template in the "channel" Template Group.

.. _query-strings:

Query Strings
-------------

Some web servers — typically Windows-based servers — still have
difficulty with the default ExpressionEngine setup that doesn't use
query strings. In cases like this, you can tell the system to **Force
URL Query Strings** under :menuselection:`Settings --> Debugging & Output`.

With this option enabled, the URLs output by ExpressionEngine are
slightly different, but still far more readable and search
engine-friendly than a typical dynamic system might output. With **Force
URL Query Strings** turned on, an ExpressionEngine URL might look like
this::

	https://example.com?/site/archives

You'll notice that it is almost identical to the regular setting, only
with the addition of the question mark.

In a select few cases, turning on **Force URL Query Strings** by itself
won't be enough. If URLs continue to not work even with that setting on,
then open system/user/config/config.php and set::

$config['uri_protocol']	= 'QUERY_STRING';
