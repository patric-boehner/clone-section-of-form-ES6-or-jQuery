> Just updated to now include a 'non-jQuery' plain JavaScript (ES6) version!

# Duplicate a section of a form, maintaining accessibility (a11y)

Using jQuery or plain JavaScript (ES6), you can now duplicate a section of a form (as well as destroy the last cloned section), the whole form, or just one or two inputs. This also allows the user to add an empty form section with unique, iterative `ID`, `for`, `name`, and `label` to maintain accessibility (a11y) and work with the database.

To help you get a jumpstart on this, the .js files are well-commented.

## Overview

A more detailed overview [can be found here](https://tristandenyer.com/using-jquery-to-duplicate-a-section-of-a-form-maintaining-accessibility/ "can be found here"). I will be working on porting it over to this page soon. (Still working on this todo.)

## jQuery version

The [jQuery version](https://github.com/tristandenyer/clone-section-of-form-ES6-or-jQuery/tree/master/jQuery "jQuery version") has been in development since June 2013, and is more stable, at the moment.

## ES6 JavaScript version

The [ES6 version](https://github.com/tristandenyer/clone-section-of-form-ES6-or-jQuery/tree/master/ES6-JavaScript "ES6 version") was a direct port over from the jQuery version. While it works in the same way the jQuery one does, there are some notable todos and refactoring that needs to be done before it can be used in production environments.

## Capabilities

This cloning script is built to:
- allow a user to duplicate a section (one or more inputs) of a form
- _not_ duplicate the user’s inputs from the original section, but show a fresh, empty section below the original
- stop a user from adding new sections at a specified integer (default is 5 total)
- maintain the accessibility of matching the labels to the input attributes, even after cloning
- increment the updated `for`, `id` and `name` attributes (ID2_, ID3_, ID4_) so as to be unique pairs
- be customizable to work with your existing form

This is _not_ a drop-in-and-it-works solution. You can see in the .js files that we depend on querying for classnames to update the `for`, `id` and `name` attributes of inputs, among other things.

## How it works

1. you wrap the section you want to allow to be cloned with a div with a class of `clonedInput`.
2. on click, we clone that section and all of its children nodes
3. then we increment a number variable (to keep track of sections; `for`, `id` and `name` attributes; removing sections...)
4. increment the `for`, `id` and `name` attributes (ID2_, ID3_, ID4_) of inputs
5. set all input values to null
6. insert the cloned and updated section after the previous
7. check if we are at the max allowable sections, and update buttons accordingly

## Demos

The ES6 demo can be viewed here: https://github.com/tristandenyer/clone-section-of-form-ES6-or-jQuery/blob/master/ES6-JavaScript/index.html (download repo and view).

### Duplicate a whole section of a form

The Bootstrap 3.4 demo for duplicating a whole section of a form [can be found here](https://tristandenyer.com/demos/dynamic-form-bootstrap-3-0.html "View Demo: Duplicate a whole section of a form").

### Duplicate multiple elements independently

The Bootstrap 3.4 demo supporting duplicating multiple elements independently [can be found here](https://tristandenyer.com/demos/dynamic-form-bootstrap-3-3-4-multiple.html "View Demo: Duplicate multiple elements independently").

### Cool Time Budget Calculator on Codepen

I found a pen that uses version 0.9.4.1 to create a simple form for a calculator. [View it here](https://codepen.io/anon/pen/bdJvgG "View Cool Time Budget Calculator on Codepen").

## Questions/support

You can best reach me by using [my contact page](https://tristandenyer.com/contact/ "Contact Tristan Denyer").

Or on Twitter: [@tristandenyer](https://twitter.com/tristandenyer "Tristan Denyer on Twitter")

## License

The MIT License (MIT)
