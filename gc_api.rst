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
* :ref:`CheckBox <checkbox>`
* :ref:`TextArea <textarea>`
* :ref:`General API <generalBasicGcApi>`
* :ref:`Validation Rules <validRules>`

.. _statictext:

Text
----
A basic text object. It can be used to display any kind of information. It produces a standard <div> HTML element. 

.. _button:

Button
------

Simple button component for the user's actions, like click, doubleclick etc. Also, the common usage of this component is to validate and submit the form.

.. image:: images/button.png

Example: this code in the button **click** system event makes the form validation.
::
	dataWidget.validate();

.. _textfield:

TextField
---------

This component is used to type the text information within the form.

.. image:: images/text_field.png

.. _datefield:

DateField
---------

This component is used to choose the dates within the form.

.. image:: images/date_field.png

.. _numberfield:

NumberField
-----------

This component is used to type the numeric values within the form. By default, it has an up/down spinner buttons letting to increment and decrement the value of the field. The **step** attribute is used to define the incrementing/decrementing value.

.. image:: images/numberfield.png

.. _combobox:

ComboBox
--------

This is the drop down list letting the user to choose one value from the list.

.. image:: images/combo_box.png

The combobox component is usually used with the DataQuery that can be configured in the **values** attribute.

.. _checkbox:

CheckBox
--------

Classical checkbox component, used to choose between values like yes/no, true/false etc.

.. image:: images/checkbox.png

Two arguments make the checkbox different from other components:

* **Checked Value:** used to pass the value when the checkbox is checked. By default, the value is *"on"*. If it's empty, the default value will be passed.
* **Unchecked Value:** used to pass the value when the checkbox is checked. By default, the value is empty and *null* will be passed in that case.

How to use **element.setValue()** method with checkbox:

* To check the ckeckbox:

   * If the **Checked Value** attribute has the default value (*on*), **element.setValue('on')** will check the component state.
   * If the **Checked Value** attribute does not have the default value (e.g. it has *yes*), **element.setValue('yes')** will check the component state.
   * **element.setValue(true)** will *always* check the component state.

* To uncheck the ckeckbox:

   * Any value passed by **element.setValue()** method will uncheck the component state except *true* and the current value of the **Checked Value** attribute.

Example: to check the component state (*MY_CHECKBOX* is the checkbox name).
::
	var my_checkbox = dataWidget.getElementByName('MY_CHECKBOX');
	my_checkbox.setValue(true);

Example: to uncheck the component state (*MY_CHECKBOX* is the checkbox name).
::
	var my_checkbox = dataWidget.getElementByName('MY_CHECKBOX');
	my_checkbox.setValue(false);

.. _textarea:

TextArea
--------

This component is used to type the large text information within the form.

.. image:: images/text_area.png

**Note:** using the **Text Transform** attribute, the component can automatically transform the typed text to upper or low cases.

.. _generalBasicGcApi:

General API
----
There are several methods common for all basic graphical components:

.. js:function:: setValue( value )
	
   Set and display the value passed as parameter in the text component.

   :param string value: the value to display.

.. js:function:: getValue()

   :returns: the current value associated with the component.
   
.. js:function:: css( key_style, value_style )

   Set a specific CSS style to the component.

   :param string key_style: The style key name.
   :param string value_style: The value to set.

.. js:function:: setAttribute( key_attr, value_attr )

   Set a specific attribute to the component. The attribute will be part of the renderer HTML element (*attribute_name="value"*).

   :param string key_attr: The attribute key name.
   :param string value_attr: The value to set.

.. js:function:: getAttribute( key_attr )

   Set a specific attribute associated to the component.

   :param string key_attr: The attribute key name.
   :returns: the current attribute value associated with the component.

.. _validRules:

Validation Rules
--------

To validate the form, developer has to define the **Validation Rules** for every form field in the component attributes section. After that, he needs to call somewhere **dataWidget.validate()** method (see the `Form Validation Guide <guides.html#form-validation>`_ for details).

Example: form containing two fields with defined validation rules and a button to validate the entire form.

.. image:: images/valid_form.png

Definition of the the validation rules is doing in the popup window. To get the code returning the current element value in runtime, click on *this* element in the bottom left area, then click on *Properties* in the bottom right area and double click on *value*:

.. image:: images/valid_rules.png

After that, code the application logic. The code of the *Name* field validation rules will be:
::
	if ("{this.Properties.value}" == '')
	    return false;
	else
	    return true;

The code of the *Age* field validation rules will be:
::
	if ("{this.Properties.value}" < 0)
	    return false;
	else
	    return true;

And the code of the **click** system event of the *Submit* button will be:
::
	dataWidget.validate();

As a result, if the user clicks on the *Submit* button when *Name* field is empty, this field will be highlighted by the red border:

.. image:: images/valid_error.png

Layouts and Containers
^^^^^^^^^^^^^^^^^^^^^^^^

* :ref:`FieldSet <fieldset>`

.. _fieldset:

FieldSet
----

This is the container for the form fields elements. See the :ref:`Validation Rules <validRules>` for an example.