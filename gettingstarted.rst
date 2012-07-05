.. DreamFace documentation master file, created by
   sphinx-quickstart on Tue Jun 12 17:08:40 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. image:: http://www.dreamface-interactive.com/img/dreamface-interactive.png

Getting Started
===============

Requirements
------------

DreamFace supports all major web browsers, from Microsoft Internet Explorer 6 to the latest
version of Google Chrome. However, during development using the DreamFace Studio, only
the following browsers are supported for a better debugging experience:

Google Chrome 10+
Apple Safari 5+
Mozilla Firefox 4+ with the Firebug Web Development Plugin

Architecture
------------

DreamFace is a Cloud Application Platform. There is no need to install a specific IDE or Server,
the only tool required is a web Browser.

.. note:: DreamFace can also be installed in a private cloud for a complete security.
	

Anatomy of an Application
-------------------------

A DreamFace Application is composed of several main elements:

* DataQueries: reusable elements are used to invoke web services and persist metadata

* DataWidgets: reusable elements used to display the data

* Screens: represent a web page or mobile screen in which are assembled DataWidgets according a specific layout.

A DreamFace application represent a simple or complex sequence of screens.