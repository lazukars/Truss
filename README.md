Truss
=====

An Object Oriented CSS Framework

Overview
--------

The Truss framworks consists of components classes, modifiers classes and global css classes.

Components
----------

There are 3 components to the Truss methhodolgy:

###1.) .B--### Block Component *( .B--example )*

Block components are used to style the structure of an element.  Typically, but not limited to, css properties like, padding, margin, position, display, top, left, bottom, right, bottom, text-align, and width, are used to style a *Block* component.

	<style type="css">
		.B--container{
			margin: 30px 20%;
			pardding: 20px;
		}
	</style>

	<div class="B--container"><p>Example text</p></div>

####Types####

Block components have a variety of types.

- **.B--wrapper** : Used on wrapper elements
	- **.B--container** : Used on container elements 
		- **.B--content** : Used on elements that contain an entire article for example.  The article in this case *is*  the content.
			- **.B--title** : Used on elements that contain a title. For example, the .B--title class would be used on an article's title element.
			- **.B--copy** : Used on elements with sections of text.  For example, the .B--copy class would be used on each paragraph within an article  
			- **.B--image** : Used on elements that are or contain an image.  For example, the .B--image class would be place on an <img> within an article
			- **.B--item** :  Used on items within a list.


###2.) .S--### Skin Component *( .S--example )*

Style components are used to add a design skin to an element.  Typically, but not limited to, css properties like, font-size, font-family, background-color, border, and box-shadow, are used to to style a *Skin* component.


	<style type="css">
		.S--standout{
			font-family: Arial, Helvetica, Sans-Serif;
			font-size: 30px;	
			font-weight: bold;
		}
	</style>

	<div class="B--container"><p class="S--standout">Some example text</p></div>

###3.) .U--### Utility Component *( .U--example )*

Utility components are used to abstract commonly used CSS properties.  For example, if the design calls for horizontally aligned elements, the utility component .U--array across can be used.


	<style type="css">
		.U--array.across > * {
			display: -moz-inline-box;
			-moz-box-orient: vertical;
			display: inline-block;
			vertical-align: middle;
			*vertical-align: auto;

		}
	</style>
	
	<ul class="U--array across">
		<li>One</li>
		<li>Two</li>
		<li>Three</li>
		<li>Four</li>
	</ul>


Modifiers
---------

Modifiers are CSS classes that create unique *Block*, *Style*, and *Utility* components that have common namespaces. For example, say there are two contianers that have the same *Block* component class .B--container.  In order to create two unique containers, a modifier class can be added to each of the containers. 


	<style type="css">
		.B--container.example{
			margin: 30px 20%;
			pardding: 20px;
		}
		.B--container.avatar{
			display: block;
		}
	</style>

	<div class="B--container example"><p>Some example text</p></div>
	<div class="B--container avatar"><img src="/img/avatar.png" /></div>

Globals
-------

Globals are CSS classes that can be used by muliple components.  For example, say there are two paragraphs within and HTML page.  Both of these paragraphs have the same font-family, font-size, and font-weight.  The only difference is the color of one of the paragraphs needs to be  red and the other paragraph needs to be gray.  In this case, two Global CSS classes, .red and .gray can be created. 

	<style type="css">
		.S--standout{
			font-family: Arial, Helvetica, Sans-Serif;
			font-size: 30px;	
			font-weight: bold;
		}
		.red{
			color: red;
		}
		.gray{
			color: gray;
		}
	</style>

	<p class="S--standout.red">Example text -- First example</p>
	<p class="S--standout.gray">Example text -- Second example</p>

