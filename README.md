# freecad_opening_recreator
Automatically recreates windows/doors at a certain placement using a named constraints and spreadsheets.
This is very much a work in progress, it might work for you, it might not. Comments, feedback and pr's are welcome.

This macro iterates over sketches in the openings group and then uses the named constraints to find the openings in a spreadsheet and recreate them.
Host object (e.g. the wall) is automatically determined via the external references. It can also be specified in the spreadsheet, link is via the named constraint.
The spreadsheet drives things like the template (Fixed window, simple door, whatever your template is named) and all the parameters given; width, heigh, z coordinate, h1,h2 etc - see the sc_openings spreadsheet for details.

Take a look at the window_demo, change the spreadsheet parameters or change the constraint distance and see how the openings move around or change from door to window and so on.

Step by Step to implement:
1) Create a group called openings
2) Create a group called generated_openings
3) Copy the spreadsheet sc_openings from the window_demo file or recreate it.

To use:
1) Have a wall based on a sketch.
2) Inside the sketch create a named constraint. The drawing direction is import as the endpoint denotes the start of the opening placement. The direction of the constraint denotes the direction of placement. The length of the constraint doesn't matter, only where the endpoint ends and the direction the sketch line makes. Make sure to toggle construction geometry, as nothing is build on this sketch line. It is just a means to denote a vector and its direction.
3) Name the constraint , e.g. 'my_opening_1'
4) Add the constraint to the spreadsheet and optionally enter the host object you think this opening belongs to.
5) Move the sketch to the openings group
6) run the macro

To stop using:
1) Move the sketch out of the openings group. This is usefull if you're happy with the generated result or just need to do manual touch ups which you don't want undone.


