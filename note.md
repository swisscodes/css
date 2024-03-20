# Selectors

`h2, p {color: gray;}` Seecting elements on the page grouped. comma seperated

These alternatives produce exactly the same result, but one is a lot easier to type:
h1 {color: purple;}
h2 {color: purple;}
h3 {color: purple;}
h4 {color: purple;}
h5 {color: purple;}
h6 {color: purple;}
h1, h2, h3, h4, h5, h6 {color: purple;}

## The universal selector

The universal selector, displayed as an asterisk ( * ), matches any element at all, much like a
wildcard. For example, to make every single element in a document bold, you would write this:
`* {font-weight: bold;}`

`*.warning {font-weight: bold;}` matches any element that has a class warning

p.warning {font-weight: bold;}
The selector now matches any `<p>` elements that have a class attribute containing the word

`.warning.urgent {background: silver;}`
By chaining two class selectors together, you can select only those elements that have both class
names, in any order

## ID Selectors

`*#first-para {font-weight: bold;}` selects all elements with the id of first-para

difference is that a document should have only one instance of a given ID value. If you
find yourself wanting to apply the same ID to multiple elements in a document, make it a class
instead.

## Attribute Selectors

There are four general types
of attribute selectors: simple attribute selectors, exact attribute value selectors, partial-match
attribute value selectors, and leading-value attribute selectors.

If you want to select elements that have a certain attribute, regardless of that attribute’s value,
you can use a simple attribute selector. For example, to select all `<h1>` elements that have a
class attribute with any value and make their text silver, write this:
`h1[class] {color: silver;}`
