# P5 Canvas
A simple p5 canvas component. The canvas component only exports a canvas to be used as a template for your next P5 project.


## Usage
The p5 canvas component exports only a p5 canvas component.

There is one required prop that must be passed, when adding your component.

- `elementId`: Required. Used for placement of the canvas.

By default, p5 places the canvas at the top, left of the next available spot in the window. This would make it very difficult to place the canvas exactly where you want. By creating your element with 'this' ID, you can place/layout this element wherever you choose. Pass 'this' ID to the component

### About
The current project generates a canvas, nearly the size or the inner window width/height. It is created with a red background and some basic, white, text.

### At some point
... I hope this component will be created in a way that will allow you to import the canvas and pass in the scripts/functions needed to generate your drawing. As of today, you will need to modify the scripts directly.

