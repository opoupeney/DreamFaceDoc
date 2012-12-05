.. image:: /images/dreamface-interactive.png

Guides
======

DreamFace provides several guides to give developers best practices in implementing sophisticated and powerful
features required when developing an Enterprise Cloud application:

* :ref:`Form Validation <formvalidation>`

.. _formvalidation:

Form Validation
---------------

When you develop a form with DreamFace, you can attach validation rules to each field (TextField, DateField, NumberField,
ComboBox, ...). You may want to validate all fields by verifying their respective validation rules. To do so, the DataWidget
object provides a *validate()* method that will evaluate validation rules and set a status on each field. The status can have 3 different
states:

* unvalidated: the field has not been validated yet
* validated: the validation rules has been verified
* error: the validation rules triggered an error.

Example:
::
	dataWidget.validate();

The datawidget has also a global validation status that is set according to the status of all fields:

* error: at least one field is in error mode. This status has the highest priority
* unvalidated: at least one field has not been validated yet
* validated: all fields are in success mode.

To check the global validation status of a widget, we use the method *getValidationStatus()*, such as:

Example:
::
	if (dataWidget.getValidationStatus()=="validated") {
		alert( "all fields have been validated" );
	};