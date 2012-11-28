.. image:: http://www.dreamface-interactive.com/img/dreamface-interactive.png

DreamFace's Widget Rendering API
================================

DreamFace renders widgets programatically using a JavaScript class

DataWidgetRenderer
------------------

Constructor:
.. js:function:: DataWidgetRenderer( widget_name )

   :param string widget_name: The datawidget class name.
   :returns: a new DataWidgetRenderer instance.

Example:
::
	var cust_list = new DataWidgetRenderer( "wCustomerList" );

The DreamFace engine uses a 2 steps process to generate the datawidget.

1. get a placeholder

The widget content is loaded uing an asynchronous request to the DreamFace server. The content will be displayed in a specific placeholder. The first step is therefore to generate this placeholder and add it to the HTML main document (DOM).

.. js:function:: getPlaceholder()
   :returns: a string value representing the placeholder HTML fragment.

Example:
::
	var placeholder = cust_list.getPlaceholder();
	// Add the placeholder into the body of the DOM
	$("body").append( placeholder );

2. load the widget content

Once the placeholder is added to the DOM, the widget content can be loaded.

.. js:function:: load()
   :returns: void.

Example:
::
	cust_list.load();
