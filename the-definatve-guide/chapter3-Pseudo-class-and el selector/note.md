# Pseudo-Class and -Element Selectors

## First child

 `#ericmeyer > :first-child //direct first child`
 `#ericmeyer:first-child` // selects elements with this id that is sametime a first child of any element

## Last child

 `#ericmeyer > :last-child`
 `#ericmeyer:first-child //same rules as above but for last child`

## Only Child

:only-child

a[href] img:only-child {border: 2px solid black;} //selects any  a element that has attribute href that has only 1 child of a attribute descendent

e.g
`<a href="http://w3.org/"><img src="w3.png" alt="W3C"></a>`
`<a href="http://w3.org/"><span><img src="w3.png" alt="W3C"></span></a>`

wil still select both of them because they are descendents of a and only child of there element

You should remember two things about :only-child . The first is that you always apply it to
the element you want to be an only child, not to the parent element

a[href] > img:only-child // this is only direct child that is only, not about descendent

`p:first-child:last-child {background-color: red;}` // combining this 2 gives us same effect of only-child

## Using only-of-type selection

a[href] `img:only-of-type {border: 5px solid black;}` it means select only of type img. here descendents also works. so if we have another element that has img has only child that is a descedent of `<a>` it will be selected

`table:only-of-type{color: red;}`
`table:first-of-type:last-of-type {background: red;}` // combining this gives us same effect as above

## Selecting every nth child

Let’s start with the :nth-child() equivalent of :first-child , which is :nth-child(1) . In the following example, the selected elements will be the first paragraph and the
first list item:
`p:nth-child(1) {font-weight: bold;}`
`li:nth-child(1) {text-transform: uppercase;}`

`:nth-child(3n + 1)`  // here n means numbers of item
start from n which is = 0 starting from 0  = (3*n) = 0 (+1) = 1 fist element
next element is (3 * 1) =  3 (+ 1) = 4  do that till n

`:nth-child(2n)`
will select even-numbered children, and either :nth-child(2n+1) or :nth-child(2n-1)
will select odd-numbered children. You can commit that to memory, or you can use the two
special keywords that `:nth-child() accepts: even and odd`.

we can also use minus -  to go the other way round
li:nth-child(-n + 5) {font-weight: bold;}  // this means -0 + 5 -1+5 -2+5......

`nth-last-child()` same as `nth-child()` but starts from last/buttom


## User Action Pseudo-Classes

`:hover` Refers to any element over which the mouse pointer is placed—e.g., a
hyperlink over which the mouse pointer is hovering

`:active` Refers to any element that has been activated by user input—e.g., a
hyperlink on which a user clicks during the time the mouse button is held
down, or an element a user has tapped via touch screen

`:focus` Refers to any element that currently has the input focus—i.e., can accept
keyboard input or otherwise be activated in some way

`:focus-within`
Refers to any element that currently has the input focus—i.e., can accept
keyboard input or be activated in some way—or an element containing
an element that is so focused

`:focus-visible`
Refers to any element that currently has the input focus, but only if the
user agent thinks it is an element type that should have visible focus

`:enabled` Refers to UI elements (such as form elements) that are enabled—that is,
available for input

`:disabled` Refers to UI elements (such as form elements) that are disabled—that is,
not available for input

`:checked` Refers to radio buttons or checkboxes that have been selected, either by
the user or by defaults within the document itself

`:indeterminate`
Refers to radio buttons or checkboxes that are neither checked nor
unchecked; this state can be set only via DOM scripting, and not by user
input

`:default` Refers to the radio button, checkbox, or option that was selected by
default

`:autofill` Refers to a user input that has been autofilled by the browser

`:valid` Refers to a user input that meets all of its data validity requirements

`:invalid` Refers to a user input that does not meet all of its data validity
requirements

`:out-of-range`
Refers to a user input whose value is below the minimum or above the
maximum values allowed by the control

`:required` Refers to a user input that must have a value set

`:optional` Refers to a user input that does not need to have a value set

`:read-write`
Refers to a user input that is editable by the user

`:read-only` Refers to a user input that is not editable by the user

`:placeholder-shown`

The :autofill pseudo-class is a little bit different from the other two: it matches any element
that has had its value automatically filled in or auto-completed by the browser. This may be
familiar to you if you’ve ever filled out a form by having the browser fill in stored values of your
name, email, mailing address, and so on. The input fields that are filled in usually get a distinct
style, like a yellowish background. You can add to that using :autofill , perhaps like this:

:in-range
:out-of-range

## Logical Pseudo-Classes

Let us suppose you want to apply a style to every list item that does not have a class of
moreinfo
`li:not(.moreinfo) {font-style: italic;}`

select all elements with a class of moreinfo that
are not list items
`.moreinfo:not(li) {font-style: italic;}`

`*.link:not(li, p) {font-style: italic;}`

`form *:not(p + *)`
Translated, that’s “select any element that is not the adjacent sibling `<p>` element, and is also
the descendant of a `<form>` element.

## The :is() and :where() pseudo-classes

`ol li, ul li {font-style: italic;}`
`:is(ol, ul) li {font-style: italic;}`

`ol ol li, ol ul li, ul ol li, ul ul li {font-style: italic;}`
`:is(ol, ul) :is(ol, ul) li {font-style: italic;}`

## The :has() Pseudo-Class

`div:has(img) {
    border: 3px double gray;
}`  any div that has img inside of it

its a descendent selector so no matter how deep the img is, as long as the div contains img deep down, the div will be selected

if we want the div that only has img as a direct child/children we use this below
`div:has(> img) {
  border: 5px solid red;
  color:blue;
}`
