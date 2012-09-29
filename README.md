Truss
=====

An Object Oriented CSS Framework

Overview
--------

The Truss framworks consists of components classes, modifiers classes.

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
		- **.B--content** : Used on elements that contain a group of content. For example, it would be good to use this component on an article.
			- **.B--title** : Used on elements that contain a title. For example, the .B--title class would be used on an article's title element.
			- **.B--copy** : Used on elements with sections of text.  For example, the .B--copy class would be used on each paragraph within an article. 
			- **.B--image** : Used on elements that are or contain an image.  For example, the .B--image class would be placed on an image within an article.
			- **.B--list** :  Used on list elements.
				- **.B--item** :  Used on items within a list.

The *Block types* .B--wrapper and/or .B--container are top level *Block types*.  This means that [modifiers](#modifiers) on .B--wrapper or .B--container types should flow down the *Block type*  chain. These kind of modifiers are called [key-modifiers](#types-1). So for example, if the *Block type* .B--container has a key-modifier of *article*  ( class=".B--container article") , then the *article* key-modifier would be used on every descendent *Block type*.  See below for an in depth example. 

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
			margin-left: 30%;
		}
	</style>

	<div class="B--container example"><p>Some example text</p></div>
	<div class="B--container avatar"><img src="/img/avatar.png" /></div>

####Types

- **Generic modifiers** : See modifier definition
- **Key modifiers** : Used on [top level](#types) Block types. 
- **Global modifiers** :  
	Global modifierys are CSS classes that can be used by muliple components.  For example, say there are two paragraphs within and HTML page.  Both of these paragraphs have the same font-family, font-size, and font-weight.  The only difference is the color of one of the paragraphs needs to be  red and the other paragraph needs to be gray.  In this case, two Global CSS classes, .red and .gray can be created. 

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

	The difference between *Global* modifiers and *Generic* modifiers is that generic modifiers are always combined classes.  So in the example below, .special in, .S--standout.special, is a *Generic* modifier, while .red is a *Global* modifier.  However, it is important to note that both the *Global* and *Generic* modifiers are undistinguishable in the HTML markup. 

		<style type="css">
			.S--standout.{
				font-family: Arial, Helvetica, Sans-Serif;
				font-size: 30px;	
				font-weight: bold;
			}
			.S--standout.special{
				text-transform: uppercase;
			}
			.red{
				color: red;
			}
		</style>
	
		<p class="S--standout.special">Example text -- First example</p>
		<p class="S--standout.red">Example text -- Second example</p>


FAQ
---

- ***Why do you use these ugly .B--, .S--, .U--, prefixes?***

The main reason is to make it clear to the developer the function of the class. If there are are no prefixes then it would be hard for the developer to differentiate between a *Block*, *Skin*, *Utility*, or *Modifier* class when looking at the HTML source code.

This is an open source project though, so I'm open to alternatives.

- ***Why do Block Types like, .B--container, .B--content, .B--list, etc.. exist?  These classes are just added CSS bloat.***

The Block types are used for two primary reasons.  One, they prevent css specificity problems.  Two, if you keep all of your Block Types together in your CSS, it helps structure your .css file.

- ***ids aren't used in this framework. Why?***

Ids aren't inherently bad, but the entire purpose of using an Object Oriented framework, is to reuse code.  Ids by definition can only be used once, so they aren't a great fit with an Object Oriented CSS approach.

- ***Can ids still be used for JavaScript hooks?***

Yes.  But since Block Components are unique ( when combined with modifiers ), it's not necessary.  If that just doesn't do it for ya, you could even create your own component, called .JS-- and use that for JavaScript hooks.

- ***Why do you seperate components into Blocks, Skins, and Utilities?***

Seperating Blocks and Skins allows developers to add a Skin to any element on a page without affecting the elements structure. 

- ***My \<li\> is more like a .B--container component than a .B--item component.  Is it ok to use the .B--container component instead?***  

Yes. Using the .B--container component, in this case, is correct.


Influences/Thanks
-----------------

- [Nicole Sullivan](http://www.stubbornella.org/content/)
- [OOCSS](https://github.com/stubbornella/oocss/wiki)
- [BEM Framework](http://bem.github.com/bem-method/html/all.en.html)










