.. image:: http://www.dreamface-interactive.com/img/dreamface-interactive.png

DreamFace's Graphical Controls
==============================

In order to render datawidgets, DreamFace introduces the notion of *graphical controls*. A graphical control is a reusable, configurable and programmable component used to display an information.
Graphical Controls are grouped in several categories:

* Basic
* Layouts and Containers
* Custom

Basic Graphical Controls
^^^^^^^^^^^^^^^^^^^^^^^^

* :ref:`Text <statictext>`
* :ref:`Button <button>`
* :ref:`TextField <textfield>`
* :ref:`DateField <datefield>`
* :ref:`NumberField <numberfield>`
* :ref:`ComboBox <combobox>`
* :ref:`TextArea <textarea>`

.. _statictext:

Text
----
A basic text object. It can be used to display any kind of information. It produces a standard <div> HTML element. 

.. js:function:: setValue( value )
	
   Set and display the value passed as parameter in the text component.

   :param string value: the value to display.

.. js:function:: getValue()

   :returns: the current value associated with the component.
   
.. js:function:: css( key_style, value_style )

   Set a specific CSS style to the component.

   :param string key_style: The style key name.
   :param string value_style: The value to set.

.. _button:

Button
------

.. _textfield:

TextField
---------

.. _datefield:

DateField
---------

.. _numberfield:

NumberField
-----------

.. _combobox:

ComboBox
--------

.. _textarea:

TextArea
--------

