Core {#Core}
============

Core contains an handful of common sense functions used in [MooTools](http://mootools.net).


Function: nil {#nil}
--------------------


Function: extend {#extend}
--------------------------


Function: implement {#implement}
--------------------------------



Function: typeOf {#typeOf}
--------------------------

Returns the type of object that matches the item passed in.

### Syntax:

	typeOf(obj);

### Arguments:

1. obj - (*object*) The object to inspect.

### Returns:

* 'element'    - (*string*) If object is a DOM element node.
* 'textnode'   - (*string*) If object is a DOM text node.
* 'whitespace' - (*string*) If object is a DOM whitespace node.
* 'arguments'  - (*string*) If object is an arguments object.
* 'array'      - (*string*) If object is an array.
* 'object'     - (*string*) If object is an object.
* 'string'     - (*string*) If object is a string.
* 'number'     - (*string*) If object is a number.
* 'date'       - (*string*) If object is a date.
* 'boolean'    - (*string*) If object is a boolean.
* 'function'   - (*string*) If object is a function.
* 'regexp'     - (*string*) If object is a regular expression.
* 'class'      - (*string*) If object is a Class (created with new Class, or the extend of another class).
* 'collection' - (*string*) If object is a native htmlelements collection, such as childNodes, getElementsByTagName, etc.
* 'window'     - (*string*) If object is the window object.
* 'document'   - (*string*) If object is the document object.
* 'event'      - (*string*) If object is an event.
* false        - (*boolean*) If object is undefined, null, NaN or none of the above.

### Example:

	var myString = 'hello';
	typeOf(myString); //Returns "string".



Function: instanceOf {#instanceOf}
----------------------------------


Function: Array.each {#Array-each}
----------------------------------

Used to iterate through arrays, or iterables that are not regular arrays, such as built in getElementsByTagName calls or arguments of a function.

### Syntax:

	Array.each(iterable, fn[, bind]);

### Arguments:

1. iterable - (*array*) The array to iterate through.
2. fn       - (*function*) The function to test for each element.
3. bind     - (*object*, optional) The object to use as 'this' within the function. For more information see [Function:bind][].

#### Argument: fn

##### Syntax:

	fn(item, index, object)

##### Arguments:

1. item   - (*mixed*) The current item in the array.
2. index  - (*number*) The current item's index in the array. In the case of an object, it is passed the key of that item rather than the index.
3. object - (*mixed*) The actual array/object.

### Example:

	Array.each(['Sun','Mon','Tue'], function(day, index){
		alert('name:' + day + ', index: ' + index);
	}); //Alerts "name: Sun, index: 0", "name: Mon, index: 1", etc.


Function: Object.each {#Object-each}
------------------------------------

Used to iterate through an object.

### Syntax:

	Object.each(obj, fn[, bind]);

### Arguments:

1. obj		- (*object*) The object to iterate through.
2. fn       - (*function*) The function to test for each element.
3. bind     - (*object*, optional) The object to use as 'this' within the function. For more information see [Function:bind][].

#### Argument: fn

##### Syntax:

	fn(item, index, object)

##### Arguments:

1. item   - (*mixed*) The current item in the array.
2. index  - (*number*) The current item's key.
3. object - (*mixed*) The actual array/object.

### Example:

    //Alerts "The first day of the week is Sunday", "The second day of the week is Monday", etc:
	Object.each({first: "Sunday", second: "Monday", third: "Tuesday"}, function(value, key){
		alert("The " + key + " day of the week is " + value);
	});



Function: Object.merge {#Object-merge}
--------------------------------------

Merges any number of objects recursively without referencing them or their sub-objects.

### Syntax:

	var merged = Object.merge(obj1, obj2[, obj3[, ...]]);

### Arguments:

1. (objects) Any number of objects.

### Returns:

* (*object*) The object that is created as a result of merging all the objects passed in.

### Examples:

	var obj1 = {a: 0, b: 1};
	var obj2 = {c: 2, d: 3};
	var obj3 = {a: 4, d: 5};
	var merged = Object.merge(obj1, obj2, obj3); //returns {a: 4, b: 1, c: 2, d: 5}, (obj1, obj2, and obj3 are unaltered)

	var nestedObj1 = {a: {b: 1, c: 1}};
	var nestedObj2 = {a: {b: 2}};
	var nested = Object.merge(nestedObj1, nestedObj2); //returns: {a: {b: 2, c: 1}}


Function: Object.clone {#Object-clone}
--------------------------------------

Function: Object.append {#Object-append}
--------------------------------------

 
----------------------


Deprecated Functions {#Deprecated-Functions}
============================================


Function: $chk {#chk}
---------------------

Checks to see if a value exists or is 0. Useful for allowing 0.

### Syntax:

	$chk(item);

### Arguments:

1. item - (*mixed*) The item to inspect.

### Returns:

* (*boolean*) If the object passed in exists or is 0, returns true. Otherwise, returns false.

### Example:

	function myFunction(arg){
		if($chk(arg)) alert('The object exists or is 0.');
		else alert('The object is either null, undefined, false, or ""');
	}



Function: $clear {#clear}
-------------------------

This method has been deprecated. Please use [Function:clear](/core/Types/Function/#clear) instead.


Function: $defined {#defined}
-----------------------------

Checks to see if a value is defined.

### Syntax:

	$defined(obj);

### Arguments:

1. obj - (*mixed*) The object to inspect.

### Returns:

* (*boolean*) If the object passed is not null or undefined, returns true. Otherwise, returns false.

### Example:

	function myFunction(arg){
		if($defined(arg)) alert('The object is defined.');
		else alert('The object is null or undefined.');
	}



Function: $arguments {#arguments}
---------------------------------

Creates a function which returns the passed argument according to the index (i) passed.

### Syntax:

	var argument = $arguments(i);

### Arguments

1. i - (*number*) The index of the argument to return.

### Returns

* (*function*) The function that returns a certain argument from the function's arguments.

### Example:

	var secondArgument = $arguments(1);
	alert(secondArgument('a','b','c')); //Alerts "b".



Function: $empty {#empty}
-------------------------

This method has been deprecated. Use [Function.from](/core/Types/Function/#Function-from) instead.

### Example:

	var myFunc = Function.from();
	

Function: $lambda {#lambda}
-------------------------

This method has been deprecated. Use [Function.from](/core/Types/Function/#Function-from) instead.

### Example:

	myLink.addEvent('click', Function.from(false)); //Prevents a link Element from being clickable.


Function: $extend {#extend}
---------------------------

Copies all the properties from the second object passed in to the first object passed in.

### Syntax:

	$extend(original, extension);

### Arguments:

1. original  - (*object*) The object to be extended.
2. extension - (*object*) The object whose properties will be copied to original.

### Returns:

* (*object*) The first object passed in, extended.

### Examples:

	var firstObj = {
		'name': 'John',
		'lastName': 'Doe'
	};
	var secondObj = {
		'age': '20',
		'sex': 'male',
		'lastName': 'Dorian'
	};
	$extend(firstObj, secondObj);
	//firstObj is now: {'name': 'John', 'lastName': 'Dorian', 'age': '20', 'sex': 'male'};



Function: $merge {#merge}
-------------------------

This method has been deprecated. Please use [Object.merge](#Object-merge) instead.


Function: $each {#each}
-----------------------

This method has been deprecated. Please use [Array.each](#Array-each) or [Object.each](#Object-each) instead.


Function: $pick {#pick}
-----------------------

This method has been deprecated. Please use [Array.pick](/core/Types/Array/#pick) instead.


Function: $random {#random}
-----------------------

This method has been deprecated. Please use [Number.random](/core/Types/Number/#Number-random) instead.


Function: $splat {#splat}
-------------------------

This method has been deprecated. Please use [Array.from](/core/Types/Array/#Array-from) instead.


Function: $time {#time}
-----------------------

This method has been deprecated. Please use *Date.now()* instead.

### Syntax:

	var time = Date.now();

### Returns:

* (*number*) - The current timestamp.



Function: $try {#try}
---------------------

This method has been deprecated. Please use [Function.stab](/core/Types/Function/#Function-stab) instead.


Function: $type {#type}
-----------------------

This method has been deprecated. Please use [typeOf](#typeOf) instead.




[Hash]: /core/Native/Hash
[Array]: /core/Native/Array
[Function:bind]: /core/Native/Function/#Function:bind
[Function:delay]: /core/Native/Function/#Function:delay
[Function:periodical]: /core/Native/Function/#Function:periodical
