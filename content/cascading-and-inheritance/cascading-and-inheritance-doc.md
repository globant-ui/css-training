# Cascading and Inheritance

When working with css, you'll often see some rules affecting elements in different ways. Some elements take styles from their parents, like when you assign an specific font-family to the `body` tag. And some have styles already defined on their own, like a `strong` tag, which text is already bold. This happens due to the Cascade an Inheritance rules.

To grasp these concepts, let's explain them very briefly.

## Inheritance

This defines which rules will be passed from parent to child. Rules like font-family or color are taken directly from the element's parent, as long as they don't define a rule for said property on their own. Other properties like background or height are not inherited, meaning that each new element in the hierarchy will have the default values set by the user agent. You don't really need a list to remember this kind of behavior, as you can see, they all just make sense.

    body {
	    font-family: "Source Sans Pro",sans-serif;
	    height: 100%
	}

	.example {
		color: tomato;
	}

In this example, the `.example` element will inherit the `body` font styles, but not the height property.

## Cascade

The Cascade kicks in when a rules for precedence is needed in case of conflicts. Some elements will inevitably be affected by more than one style declaration. In this cases, later properties override earlier properties, more specific selectors override less specific selectors, specified properties override inherited properties, and so on. The Cascade will define the order in which properties are applied.

The rules for Cascading and Inheritance are defined by the [W3C Standard](http://www.w3.org/TR/css-cascade-3/), but frankly it is a pain in the ass to read or try to memorize them. The more you write css, the more familiar these rules will become.

    span {
	    color: tomato;
	}

	.example span {
		color: steelblue;
	}

In this case every span in the document except the ones in a `.example` classed element will be red. As the `.example span` selector is more specific, it'll take precedence over the `span` rule.

## Credits

email: Juan Fernandez <j.fernandez@globant.com>
