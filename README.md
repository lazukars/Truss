Truss
=====

An Object Oriented CSS Framework

Overview
--------

The Truss framworks consists of components classes, modifiers classes and global css classes.

Components
----------

There are 3 components to the Truss methhodolgy:

**1.) .B--** Block Component *( .B--example )*

Block components are used to style the structure of an element.  Typically, but not limited to, css properties like, padding, margin, position, display, top, left, bottom, right, bottom, text-align, and width, are used to style a *Block* component.

	<style type="css">
		.B--container{
			margin: 30px 20%;
			pardding: 20px;
		}
	</style>

	<div class="B--container"><p>Some example text</p></div>

**2.) .S--** Skin Component *( .S--example )*

Style components are used to add a design skin to an element.  Typically, but not limited to, css properties like, font-size, font-family, background-color, border, and box-shadow, are used to to style a *Skin* component.


	<style type="css">
		.S--standout{
			font-size: 30px;	
			font-weight: bold;
		}
	</style>

	<div class="B--container"><p class="S--standout">Some example text</p></div>

**3.) .U--** Utility Component *( .U--example )*

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

Modifiers are CSS classes that create unique *Block*, *Style*, and *Utility* components that have common namespaces. For example, say there are two contianers that have the same *Block* component .B--container.  In order to create two unique containers, a modifier class can be added to each of the containers. 


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




