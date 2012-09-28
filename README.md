Truss
=====

An Object Oriented CSS Framework

Overview
--------

The Truss framworks consists of components classes, modifiers classes and global css classes.

Components
----------

There are 3 components to the Truss methhodolgy:

###1.) Block Component **.B--**

Block components are used to style the structure of an element.  Typically, but not limited to, css properties like, *padding, margin, position, display, top, left, bottom, right, bottom, text-align, and width*, are used to style a *Block* component.

	<style type="css">
		.B--container{
			margin: 30px 20%;
			pardding: 20px;
		}
	</style>

	<div class="B--container"><p>Example text</p></div>


####Types####

Block components have, but aren't limited to, a variety of types.

- **.B--wrapper** ( top level type ) : Used on wrapper elements
	- **.B--container** ( top level type ) : Used on container elements 
		- **.B--content** : Used on elements that contain an entire article for example.
			- **.B--title** : Used on elements that contain a title. For example, the .B--title class would be used on an article's title element.
			- **.B--copy** : Used on elements with sections of text.  For example, the .B--copy class would be used on each paragraph within an article  
			- **.B--image** : Used on elements that are or contain an image.  For example, the .B--image class would be place on an image within an article
			- **.B--list** :  Used on list elements.
				- **.B--item** :  Used on items within a list.

The *Block types* .B--wrapper and/or .B--container are top level *Block types*.  This means that [modifiers][] on .B--wrapper or .B--container types should flow down the *Block type*  chain. These kind of modifiers are called [key-modifiers][types-1]. So for example, if the *Block type* .B--container has a key-modifier of *article*  ( class=".B--container article") , then the *article* key-modifier would be used on every descendent *Block type*.  Every descendent block type within the .B--conainter article container.  See below for an in depth example. 

	<style type="css">
		.B--container.article{
			padding: 30px;
		}
		.B--content.article{
			marigin-left: 30%;
			padding: 15px;
		}
		.B--title.article{
			text-align: center;
			margin-bottom: 20px;
		}
		.B--image.article{
			display: block;
		}
		.B--copy.article{
			padding: 7px 0;
		}
		.B--list.article{
			padding: 10px 10px 10px 30px;
		}
		.B--item.article{
			padding: 5px;
		}

	</style>

	<div class="B--container article">
		<article class="B--content article">
			<h2 class="B--title article">CSS Rocks!</h2>
			<img class="B--image article" src="/img/example.png" />
			<p class="B--copy article">Malesuada venenatis mauris. Curabitur ornare mollis velit. Sed vitae metus. Morbi posuere mi id odio. Donec elit sem, tempor at, pharetra eu, sodales sit amet, elit.</p>
			<p class="B--copy article-">Malesuada venenatis mauris. Curabitur ornare mollis velit. Sed vitae metus. Morbi posuere mi id odio. Donec elit sem, tempor at, pharetra eu, sodales sit amet, elit.  Curabitur urna tellus, aliquam vitae, ultrices.</p>  
			<ul class="B--list article">
				<li class="B--item article">Item</li>
				<li class="B--item article">Item</li>
				<li class="B--item article">Item</li>
				<li class="B--item article">Item</li>
			<ul>
		</article>
	</div>	


###2.) Skin Component **.S--**

Style components are used to add a design skin to an element.  Typically, but not limited to, css properties like, *font-size, font-family, background-color, border, and box-shadow*, are used to to style a *Skin* component.


	<style type="css">
		.S--standout{
			font-family: Arial, Helvetica, Sans-Serif;
			font-size: 30px;	
			font-weight: bold;
		}
	</style>

	<div class="B--container"><p class="S--standout">Some example text</p></div>


###3.) Utility Component **.U--**

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

####Types

- **Generic modifiers** : See modifier definition
- **Key modifiers** : Used on [top level][types] Block types. 


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

