Download Link: https://assignmentchef.com/product/solved-shape
<br>
<p class="ui header product-top-header" title="Shape Solution"> Compile this code. After pressing any key to clear the instructions, You  should see three rectangles labeled ‘#’, ‘b’, and ‘c’. You should also see  two triangles, labeled ‘d’ and ‘e’. Pressing ” and ‘&lt;‘ will change which  shape is labeled ‘#’. Pressing ‘w’, ‘a’, ‘s’, and ‘d’ will move the shape  labeled ‘#’. Pressing ‘space’ will randomize the selected shape.

Read through this code! Try to understand it before starting the assignment. Comment confusing lines with what you think code is doing, and experimentwith existing code to test your understanding.Once you feel comfortable with this code, accomplish each of the following,and make sure your code compiles and runs after each step is completed.

1. Getting comfortable with the code

a) Create a “makeRandom” method in both the Rect and Tri classes, based

on the “makeRandomRect” and “makeRandomTri” functions in

“application.cpp”. The makeRandom function should take no parameters,

and instead make itself random. Removing the old “makeRandomRect”

and “makeRandomTri” functions as well. Be sure to consider what to do

about “screenMin” and “screenMax”.

b) Create a print method for the Tri class, similar to the print method

for the Rect class. This method may come in very handy when debugging.

2. Create Shape base class

a) Create a header file (without a .cpp file) for a Shape class.

b) Create the Shape class, which should have no member variables.

c) Make the Shape class an interface for the Rect and Tri classes. Shape

should have pure-virtual methods for each method that Rect and Tri have

in common.

d) Make sure Shape has a virtual destructor with an empty body.

3. Make Rect and Triangle extend Shape

4. Change selected

a) Change the type of “Application::selected” from “void *” to “Shape *”.

b) Every piece of code that typecasts “selected” (and the logic around it)

can be removed now. Simply call functions using the “Shape” interface.

c) Remove the “selectedType” variable from Application. Logic that needs

some form of RunTime Type Information should use dynamic_cast instead.

5. Merge all Shape objects into a single array

a) Create an array of Shape pointers in the Application called “shapes”.

b) Making a complementary NUM_SHAPES variable would make sense.

b) Remove “rectangles” and “triangles” arrays.

c) Put each Tri and Rect object managed by the Application class into

the “shapes” array. This will require re-factoring in multiple files.

While removing references to “rectangles” and “triangles” arrays, it

may make sense to replace pairs of for-loops using each of the old

arrays with a single for-loop using just “shapes”.

6. Make “shapes” dynamic

a) Give Application::init() 2 parameters: int numRect, int numTri

b) Make “shapes” a pointer of type “Shape **”, and allocate it to be

“numShapes” big, where “numShapes” is an int member of Application

equal to (numRect + numTri), defined in Application::init().

c) When calling “app.init()” in main, pass valid arguments for numRect

and numTri.

d) De-allocate the “shapes” array in Application::Release().

7. Clean up old variables

a) Remove the TYPE_RECT and TYPE_TRI variables from Application.

b) Remove NUM_TRI and NUM_RECT, and any NUM_SHAPES variable as well. Use

numShapes where needed.

8. Add Circle class

a) Create a header file AND a source file for a Circle class.

b) Use Rect and Tri as examples to create the Circle class with.

c) A Circle class should have at least a 2 dimensional position, and a

radius.

d) A simple algorithm for drawing a Circle will be similar to drawing a

Rect or Tri, thought it might include the following code:

float dx = center.x – col, dy = center.y – row;

if( dx*dx + dy*dy &lt;= radius * radius ) {

moveCursor(col, row);

putchar(letter);

}

e) Add an additional parameter to Application::init(), “int numCircles”.

Implement init to generate Circle objects along with Rect and Tri

objects.

9. Implement add/remove for the shapes array

a) Add code that increases the size of the shapes array, adding a random

shape, whenever the ‘=’ or ‘+’ key is pressed. Take a look at the week

5 lecture showing explicit constructors for help with this algorithm.

a) Add code that decreases the size of the shapes array, removing the last

shape, whenever the ‘-‘ or ‘_’ key is pressed. End the program when the

last shape is removed. Removing a shape, like adding a shape, can be

done by allocating an array of a different size (smaller this time).

Achievements: (if you finished, and would like a challenge, try these)

[Remove the Offending] Instead of removing the last shape when ‘-‘ is

pressed, remove only the currently selected shape.

[Extra Random] When ‘space’ is pressed to randomize a shape, it also changes

type, into another kind of Shape (Rect, Tri, Circle, …).

[Triangle Centroid] Have the triangle class calculate its Centroid instead

of its average when doing the getCenter() calculation.

[That’s Where I Draw The Line!] Implement a Line class, extending shape,

which is composed of just 2 Vector2 objects. Make sure it can draw,

move, and randomize, just like the other shapes!

[Page Flipping] Instead of having each Shape print directly to the screen,

have each Shape print to a 2D character array large enough to fill the

screen, and only print that 2D array to the screen.

[Look Ma, No Leaks!] Download and use VLD (Visual Leak Detector) to find

your memory leaks. If VLD shows you a memory leak, fix it by using

“delete” on allocated memory. VLD is a free tool for Visual Studio,

search for it using your favorite search engine!

[No Touching!] Implement an algorithm that detects if any shapes are

colliding with any other shapes of any type. When no shapes are

colliding, display a message identifying “No Collisions!”.

[I’ve Poly-Gone Too Far!] Create a Polygon class that Tri and Rect derive

from. Re-implement Rect to store 4 Vector2 instead of just min and max.

With this design, it’s possible to rotate the shapes about their center.

Implement a “virtual void rotate(float radians) = 0;” pure-virtual

function in shape, implement it in each Shape, and test it! For example,

have the ‘q’ key rotate the shape counter-clockwise 1/8*PI radians.