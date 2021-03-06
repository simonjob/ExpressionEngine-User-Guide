.. # This source file is part of the open source project
   # ExpressionEngine User Guide (https://github.com/ExpressionEngine/ExpressionEngine-User-Guide)
   #
   # @link      https://expressionengine.com/
   # @copyright Copyright (c) 2003-2018, EllisLab, Inc. (https://ellislab.com)
   # @license   https://expressionengine.com/license Licensed under Apache License, Version 2.0

Wiki Module Extension Hooks
===========================

.. contents::
  :local:
  :depth: 1

.. highlight:: php

wiki_start
----------

.. function:: wiki_start($this)

  Allows page template to be modified prior to article processing

  How it's called::

    $this->return_data = ee()->extensions->universal_call('wiki_start', $this);
    if (ee()->extensions->end_script === TRUE) return;

  :param object $this: The current Wiki class object
  :returns: Modified page template (``$this->return_data``)
  :rtype: String

  .. versionadded:: 1.6.0

wiki_article_start
------------------

.. function:: wiki_article_start($this, $title, $query)

  Additional processing/takeover of wiki article display.

  How it's called::

    ee()->extensions->universal_call('wiki_article_start', $this, $title, $query);
    if (ee()->extensions->end_script === TRUE) return;

  :param object $this: The current Wiki class object
  :param string $title: The title of the requested article
  :param object $query: The query object for the article
  :rtype: Void

  .. versionadded:: 1.6.0

wiki_article_end
----------------

.. function:: wiki_article_end($this, $query)

  Allows takeover of wiki article display.

  How it's called::

    $this->return_data = ee()->extensions->universal_call('wiki_article_end', $this, $query);
    if (ee()->extensions->end_script === TRUE) return;

  :param object $this: The current Wiki class object
  :param object $query: The query object for the article
  :returns: Modified article display (``$this->return_data``)
  :rtype: String

  .. versionadded:: 1.6.0

wiki_special_page
-----------------

.. function:: wiki_special_page($this, $topic)

  Allows complete takeover of special pages.

  How it's called::

    ee()->extensions->universal_call('wiki_special_page', $this, $topic);
    if (ee()->extensions->end_script === TRUE) return;

  :param object $this: The current Wiki class object
  :param string $topic: The requested topic (e.g. categories, files, etc.)
  :rtype: Void

  .. versionadded:: 1.6.0

edit_wiki_article_end
---------------------

.. function:: edit_wiki_article_end($this, $query)

  Add more things to do for wiki articles.

  How it's called::

    $edata = ee()->extensions->universal_call('edit_wiki_article_end', $this, $query);
    if (ee()->extensions->end_script === TRUE) return;

  :param object $this: The current Wiki class object
  :param object $query: The query object for the article
  :rtype: Void

  .. versionadded:: 1.6.0

edit_wiki_article_form_start
----------------------------

.. function:: edit_wiki_article_form_start($this, $title, $query)

  Additional processing/complete takeover of the wiki article edit form.

  How it's called::

    ee()->extensions->universal_call('edit_wiki_article_form_start', $this, $title, $query);
    if (ee()->extensions->end_script === TRUE) return;

  :param object $this: The current Wiki class object
  :param string $title: The title of the article
  :param object $query: The query object for the requested title
  :rtype: Void

  .. versionadded:: 1.6.0

edit_wiki_article_form_end
--------------------------

.. function:: edit_wiki_article_form_end($this, $query)

  Allows edit page to be modified.

  How it's called::

    $this->return_data = ee()->extensions->universal_call('edit_wiki_article_form_end', $this, $query);
    if (ee()->extensions->end_script === TRUE) return;

  :param object $this: The current Wiki class object
  :param object $query: The query object for the article
  :returns: Modified edit page (``$this->return_data``)
  :rtype: String

  .. versionadded:: 1.6.0

