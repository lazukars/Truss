Truss
=====

An Object Oriented CSS Framework

Overview
--------

The Truss framworks consists of components classes, modifiers classes and global css classes.

Components
----------

There are 3 components to the Truss methhodolgy:

**1.) .B-- Block** Component ( .B--example )

Block components are used to style the structure of an element.  Typically, but not limited to, css properties like, padding, margin, position, display, top, left, bottom, right, bottom, text-align, and width, are used to style a *Block* components.

	<style type="css">
		.B--container{
			margin: 30px 20%;
			pardding: 20px;
		}
	</style>

	<div class="B--container"><p>Some example text</p></div>

**2.) .S-- Skin** Component ( .S--example )

Style components are used to add a design skin to an element.  Typically, but not limited to, css properties like, font-size, font-family, background-color, border, and box-shadow, are used to to style a *Skin* component.


	<style type="css">
		.S--standout{
			font-size: 30px;	
			font-weight: bold;
		}
	</style>

	<div class="B--container"><p class="S--standout">Some example text</p></div>

**3.) .U-- Utility** Component ( .U--example )

