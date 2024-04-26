# SVG

The root `<svg>` element defines the width and height of the finished graphic in
pixels. It also defines the SVG namespace via the xmlns attribute. The`<title>` element’s
content is available to a viewing program for use in a title bar or as a tooltip pointer, and
the `<desc>` element lets you give a full description of the image.
e.g

```html
    <svg width="140" height="170"
    xmlns="http://www.w3.org/2000/svg">
    <title>Cat</title>
    <desc>Stick Figure of a Cat</desc>
    <!-- the drawing will go here -->
    </svg>

x = horizontal -----
y = vertical |
