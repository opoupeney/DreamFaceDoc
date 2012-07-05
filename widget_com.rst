.. image:: http://www.dreamface-interactive.com/img/dreamface-interactive.png

DreamFace's Widget Communication API
====================================

DreamFace extends JavaScript by providing the following pre-defined functions:

``Send an event``

.. js:function:: radio( event_name ).broadcast( data )

   :param string event_name: The event to trigger.
   :param Object data: The associated data.
   :returns: void.

Example:
::
	radio( "CustomerSelected" ).broadcast( { "company_name": "ACME" } );

``Subscribe to an event``

.. js:function:: radio( event_name ).subscribe( callback )

   :param string event_name: The event to trigger.
   :param Function callback: The function that will be trigger when the event will be broadcasted.
   :returns: void.

Example:
::
	radio( "CustomerSelected" ).subscribe( function( data ) {
		dfAlert( "Customer Selected: " + data.company_name );
	});
