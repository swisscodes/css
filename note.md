# Pseudo-Class and -Element Selectors

## First child

 #ericmeyer > :first-child

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

## Using only-of-type selection

a[href] img:only-of-type {border: 5px solid black;} it means select only of type img. here descendents also works. so if we have another element that has img has only child that is a descedent of `<a>` it will be selected
