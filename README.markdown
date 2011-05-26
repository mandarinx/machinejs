#Machine.js
Make behaviour trees in JavaScript

By mary rose cook
http://maryrosecook.com
maryrosecook@maryrosecook.com

##What is Machine.js?

Machine.js lets you use a hierarchical state machine to control a JavaScript object.

==Licence

The code is open source, under the MIT licence.  It uses Base.js by Dean Edwards.

==Tutorial

===A primer on behaviour trees

A behaviour tree is a normal state machine, except the states are connected in a hierarchical structure.  At fork states, the object controlled by the tree does nothing.  A fork state simply leads into one of a set of subsequent states (their children).  At leaf states - states with no children - action is taken by the object.

Movement from state to state is controlled by two mechanisms: strategies and can functions. Each fork state has a strategy that

===Import libraries

You will need to import machine.js and base.js. If you are running your behaviour tree in a web page, you might do that like this:

===Define an object

Define the object that will be controlled by the behaviour tree. Any normal JavaScript object will do.

===Write a behaviour tree

Write some JSON that defines your object's behaviour tree.

===Add behaviours to your object

For each state in your behaviour tree, add a synonymous function to your object. This will be run once when the object moves to the corresponding state. For each state, also add a function called "canNameOfState". This should return true if the object is allowed to move to the corresponding state.

For example, if your state is called "kiss", you would add a function to your object called "kiss" that does the kissing, and a function called "canKiss" that returns true if kissing is allowed.

===Put it all together

Instantiate your object. Make an instance of Machine. Use the instance of machine to generate a behaviour tree, passing in the tree JSON and your object. Repeatedly call <code>tick()</code> on the state machine.