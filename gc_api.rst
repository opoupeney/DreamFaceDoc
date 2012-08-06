.. image:: http://www.dreamface-interactive.com/img/dreamface-interactive.png

DreamFace's Graphical Control API
=================================

Graphical controls can be dynamically manipulated using an object oriented notation:

.. js:function:: css( property, value )
``Set a CSS value``

   :param string property: The message to display.
   :returns: void.
    
Example:
::
	element.css( "color", "#ff0000" );

.. js:function:: validate()
``Invoke validation rules``

   :returns: the validation result.
    
Example:
::
	element.validate();

.. note:: If the graphical control is a container, the validate function will automatically trigger
validation rules of its children controls and return a global result.

.. note:: To set a validation rule on a component, go to the widget builder, select the control, and click on *validation rules*
to open the validation rules editor. Your rule must be written in javascript and must return the result. Two types of results are
accepted:

* boolean: return **true** or **false**
* object: return ``{ valid: false, error_msg: "you must enter a value greather than 10" }``

