.. # This source file is part of the open source project
   # ExpressionEngine User Guide (https://github.com/ExpressionEngine/ExpressionEngine-User-Guide)
   #
   # @link      https://expressionengine.com/
   # @copyright Copyright (c) 2003-2018, EllisLab, Inc. (https://ellislab.com)
   # @license   https://expressionengine.com/license Licensed under Apache License, Version 2.0

#########################
Displaying Search Results
#########################

.. contents::
	:local:
	:depth: 2

******************
Search Results Tag
******************

The Search Results Tag controls how you display results from your
searches. Example::

  <table border="0" cellpadding="6" cellspacing="1" width="100%">
      <tr>
          <th>{lang:title}</th>
          <th>{lang:excerpt}</th>
          <th>{lang:author}</th>
          <th>{lang:date}</th>
          <th>{lang:total_comments}</th>
          <th>{lang:recent_comments}</th>
      </tr>

  {exp:search:search_results switch="resultRowOne|resultRowTwo"}

      <tr class="{switch}">
          <td width="30%" valign="top"><b><a href="{auto_path}">{title}</a></b></td>
          <td width="30%" valign="top">{excerpt}</td>
          <td width="10%" valign="top"><a href="{member_path='member/index'}">{author}</a></td>
          <td width="10%" valign="top">{entry_date format="%m/%d/%y"}</td>
          <td width="10%" valign="top">{comment_total}</td>
          <td width="10%" valign="top">{recent_comment_date format="%m/%d/%y"}</td>
      </tr>

      {if count == total_results}
          </table>
      {/if}

      {paginate}
          <p>Page {current_page} of {total_pages} pages {pagination_links}</p>
      {/paginate}

  {/exp:search:search_results}

  </table>

The Search module uses the same pagination syntax as all first-party
modules. Please look at the :doc:`/templates/pagination` documentation
for more information.

Parameters
==========

.. contents::
	:local:

backspace=
----------

::

	backspace="7"

Backspacing removes characters (including spaces and line breaks) from
the last iteration of the loop. For example, if you put a <br /> tag
after each result field you'll have this::

	Entry 1<br />
	Entry 2<br />
	Entry 3<br />

You might, however, not want the <br /> tag after the final item. Simply
count the number of characters (including spaces and line breaks) you
want to remove and add the backspace parameter to the tag. The <br />
tag has 6 characters plus a new line character, so you would do this::

	{exp:search:search_results backspace="7"}
		{title}<br />
	{/exp:search:search_results}

That will produce code like this::

	   Entry 1<br />
	   Entry 2<br />
	   Entry 3

.. _search-id-parameter:

search_id=
----------

::

	search_id="{segment_4}"
	
The search_id is a 32 character ID number automatically included in search URLs and used to retrieved cached search results.  The search_id can be 
manually specified via parameter in cases where the URL does not follow the standard template_group/template pattern.

Variables
==========

Nearly all of the :ref:`Channel Entries Tag
Variables <channel_entries_single_variables>` are available for the
search results page so that you can display as much or as little of the
channel entry's data as possible depending on your needs. There are also
some search results specific variables available in the results page:

.. contents::
	:local:

auto\_path
----------

::

	{auto_path}

This parameter is replaced with the URL to the entry with the URL Title
appended to the end. Unlike other "path" variables, this variable does
**not** require the Template\_Group/Template to be specified. Instead,
the path will automatically be determined by the Search Results URL
setting for the channel in :doc:`Channel
Management </cp/channel/index>`.

excerpt
-------

::

	{excerpt}

An excerpt from the entry. The excerpt consists of the first 50 words
from the field specified for search excerpting in your :doc:`Channel
Management </cp/channel/index>` settings for your
channels. HTML markup is stripped prior to output.

full\_text
----------

::

	{full_text}

The text from the entry. Unlike the {excerpt} variable, this one returns
the entire text from the field specified for search excerpting in your
:doc:`Channel Management </cp/channel/index>`
settings for your channels.

id\_auto\_path
--------------

::

	{id_auto_path}

This parameter is replaced with the URL to the entry with the Entry ID
appended to the end. Unlike other "path" variables, this variable does
**not** require the Template\_Group/Template to be specified. Instead,
the path will automatically be determined by the Channel URL setting for
the channel in `Channel Management
</cp/channel/index>`.

member\_path
------------

::

	{member_path='member/index'}

The Template\_Group/Template with which to display the member profile of
the author of the entry. Typically, this variable will be specified as
{member\_path='member/index'}.

*******************
Search Keywords Tag
*******************

This tag lets you display the keywords used to perform a search. It is
used on the search results page in order to show the user exactly what
search terms they used::

	{exp:search:keywords}

This may also be used on the template specified by the
:ref:`no_result_page <search_advanced_no_result_page>` parameter of the
:doc:`simple search form <simple>` and :doc:`advanced search form
<advanced>`.

The only parameter for this tag is the :ref:`search-id-parameter` parameter.

There are no variables associated with this
ExpressionEngine tag.

************************
Search Total Results Tag
************************

This tag lets you display the total number of results found during a
search. It is used on the search results page to show the total number
of matches::

	{exp:search:total_results}

This may also be used on the template specified by the
:ref:`no_result_page <search_advanced_no_result_page>` parameter of the
:doc:`simple search form <simple>` and :doc:`advanced search form
<advanced>`.

The only parameter for this tag is the :ref:`search-id-parameter` parameter.

You may alternatively use the tag pair::

	{exp:search:total_results}
		{total_results}
	{/exp:search:total_results}

The only variable associated with this tag is {total_results}.

