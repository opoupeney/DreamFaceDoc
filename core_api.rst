.. image:: http://www.dreamface-interactive.com/img/dreamface-interactive.png

DreamFace's Core API
====================

DreamFace extends JavaScript by providing the following pre-defined functions:

``Navigate to a specific Screen``

.. js:function:: dfGotoScreen( name )

   :param string name: The screen name you want to navigate to.
   :returns: void.
   
``Get a reference to a DataWidget``

.. js:function:: dfGetDataWidget( name )

   :param string name: The DataWidget name.
   :returns: a reference to the DataWidget object.
   
``Set a Value into the Application Context``

.. js:function:: dfSetContextValue( object_name, property, value, callback )

   :param string object_name: The context object name.
   :param string property: The context property name.
   :param string value: The value to store.
   :param function callback: the function to callback 
   :returns: void.
   
Example::

	dfSetContextValue( "customer", "name", "acme", function() {
	dfAlert( "The customer name has been stored" );
	});
