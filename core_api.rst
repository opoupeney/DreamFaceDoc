.. image:: http://www.dreamface-interactive.com/img/dreamface-interactive.png

DreamFace's Core API
====================

DreamFace extends JavaScript by providing the following pre-defined functions:

``Display an Alert box``

.. js:function:: dfAlert( msg )

   :param string msg: The message to display.
   :returns: void.
   
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
   :param Function callback: the function to callback 
   :returns: void.
   
Example:
::
	dfSetContextValue( "customer", "company_name", "ACME", function() {
		dfAlert( "The customer company name has been stored" );
	});

``Set multiple values into the Application Context``

.. js:function:: dfSetContextValues( ctx_object, callback )

   :param Object ctx_object: The context object description containing all values to be stored.
   :param Function callback: the function to callback 
   :returns: void.
   
Example:
::
	var ctx_object = { "context_values": [
		{"object":"customer", "property": "company_name", "value": "ACME"},
		{"object":"customer", "property": "company_city", "value": "New York"}
	] };
	dfSetContextValues( ctx_object, function() {
		dfAlert( "The customer company name and city have been stored" );
	});

``Get a Value from the Application Context``

.. js:function:: dfGetContextValue( object_name, property_name, callback )

   :param string object_name: The context object name.
   :param string property_name: The context property name.
   :param Function callback: the function to callback. The retrieved value is passed as parameter. 
   :returns: void.

Example:
::
	dfGetContextValue( "customer", "company_name", function( value ) {
		dfAlert( "The customer company name is: " + property_name );
	});
	
``Get the entire Application Context``

.. js:function:: dfGetContextValues( callback )

   :param Function callback: the function to callback. The retrieved application context is passed as parameter. 
   :returns: void.

Example:
::
	dfGetContextValues( function( ctx_object ) {
		dfAlert( "The customer company name is: " + ctx_object.customer.company_name );
	});

