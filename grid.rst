.. image:: http://www.dreamface-interactive.com/img/dreamface-interactive.png

DreamFace's Grid Graphical Component
====================================

Grid is the one of the moset complex graphical components in the DreamFace's toolbox. It's used to  interactively show the information in the form of the table with different possibilities like summarising the column values, edit selected cells etc.

* :ref:`Basic Usage <basicUsage>`
* :ref:`Columns Summary <columnsSummary>`
* :ref:`Grouping Rows <groupingRows>`
* :ref:`Locking Columns <lockingColumns>`
* :ref:`Editing Rows <editingRows>`
* :ref:`Live Search <liveSearch>`
* :ref:`Paging and Passing Parameters to DataQuery<pagingAndPassingParams>`
* :ref:`Refreshing the Dynamic Chart depending on the Grid Column <dynChartsLinkedToGrid>`
* :ref:`Putting the Dynamic Charts in the Grid Column <dynChartsInGrid>`

.. _basicUsage:

Basic Usage
----

.. _columnsSummary:

Columns Summary
------

.. _groupingRows:

Grouping Rows
---------

.. _lockingColumns:

Locking Columns
---------

.. _editingRows:

Editing Rows
-----------

.. _liveSearch:

Live Search
--------

Live Search capability lets user to find and highlight the data that have already been downloaded by the grid. This functionality can work in two ways:

* With a preconfigured toolbar containing all the necessary buttons and fields.
* Programmatically, using the Live Search Grid API.

Live Search with Preconfigured Toolbar
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To use the preconfigured Live Search toolbar, user has to open the Grid **values** attribute and put both the **Live Search** and **Show Toolbars** parameters to **yes**. 

As a result, the Grid will have a Live Search toolbar with a text filed to type the looking value, buttons **Next** and **Previous** and a checkbox to filter the case sensitivity of the looking values. The found values will be highlighted by the color. The row containing the currently selected value will be higlighted as well.

Also, at the bottom of the grid, there will be status bar showing the number of the found values.

.. image:: images/grid_preconf_live_search.png

Programmatical Live Search
^^^^^^^^^^^^^^^^^^^^^^^^^^

Sometimes, developer does not want to use the preconfigured toolbars and wants more flexibility. For such cases, there is a Grid Live Search API. Using this API, developer can use only one text field without any buttons or with them. Any component can use this API that gives the developer a very flexible system. Also, one text filed can be used for searching in several grids.

To use this functionality, user has to open the Grid **values** attribute and put the **Live Search** parameter value to **yes**.

Live Search API is attached to the Grid instance and containes the following functions:

.. js:function:: liveSearch.search( dataToSearch )
	
   Searches the passed data in the Grid instance.

   :param object value: Data to search. The object has several properties: **text** (*string*) - text to search, **caseSensitive** (*boolean*) - case sensitive or not, **statusCallback** - callback function passing the status text as an argument containing the number of entries found.

.. js:function:: liveSearch.searchPrevious()
	
   Highlights the previous found entry in the grid.

.. js:function:: liveSearch.searchNext()
	
   Highlights the next found entry in the grid.

Example:

.. image:: images/grid_program_live_search.png

Grid's **name** attribute is *PEOPLE_GRID*. TextFiled component contains this code in the **change** system event:
::
	var peopleGrid = dataWidget.getElementByName('PEOPLE_GRID').getExtComponent();

	peopleGrid.liveSearch.search({text:element.getValue(),
                     		      caseSensitive:false, 
		                      statusCallback:function(statusText){console.log(statusText);}
                    		     });

Button *Previous* contains this code in the **click** system event:
::
	var peopleGrid = dataWidget.getElementByName('PEOPLE_GRID').getExtComponent();
	peopleGrid.liveSearch.searchPrevious();

Button *Next* contains this code in the **click** system event:
::
	var peopleGrid = dataWidget.getElementByName('PEOPLE_GRID').getExtComponent();
	peopleGrid.liveSearch.searchNext();

.. _pagingAndPassingParams:

Paging and Passing Parameters to DataQuery
--------

.. _dynChartsLinkedToGrid:

Refreshing the Dynamic Chart depending on the Grid Column
--------

.. _dynChartsInGrid:

Putting the Dynamic Charts in the Grid Column
--------