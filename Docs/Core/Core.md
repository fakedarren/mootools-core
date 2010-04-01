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


Function: Function.from {#Function-from}
----------------------------------------


Function: Array.from {#Array-from}
----------------------------------

Returns an array, not necessarily a new one <-cpojer

To get a new copy do Array.slice(array) or Array.prototype.slice.call(array_like_object)  if it needs to be fast :D


Function: Number.from {#Number-from}
------------------------------------


Function: String.from {#String-from}
------------------------------------


Function: Function.hide {#Function-hide}
----------------------------------------


Function: Function.protect {#Function-protect}
----------------------------------------------


Constructor: Type {#Type} <-- Private
-------------------------
Function: Type.isEnumerable {#Type-isEnumerable} <-- Private
Function: Type.implement {#Type-implement} <-- Private
Function: Type.extend {#Type-extend} <-- Private
Function: Type.alias {#Type-alias} <-- Private
Function: Type.mirror {#Type-mirror} <-- Private


Function: Number.random {#Number.random}
----------------------------------------


Function: Object.each {#Object.each}
------------------------------------
Function: Array.each {#Array.each}
------------------------------------


Function: Array.clone {#Array-clone}
------------------------------------


Function: Object.merge {#Object-merge}
--------------------------------------

Function: Object.clone {#Object-clone}
--------------------------------------

Function: Object.append {#Object-append}
--------------------------------------


Constructor: Hash {#Hash}
Function: Hash.each {#Hash-each}
Function: Hash.getClean {#Hash-getClean}
Function: Hash.getLength {#Hash-getLength}



Core Compatibility {#Core-Compatibility}
========================================


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

### See also:

- [Function:delay][]
- [Function:periodical][]



Function: $each {#each}
-----------------------

Used to iterate through iterables that are not regular arrays, such as built in getElementsByTagName calls, arguments of a function, or an object.

### Syntax:

	$each(iterable, fn[, bind]);

### Arguments:

1. iterable - (*object* or *array*) The object or array to iterate through.
2. fn       - (*function*) The function to test for each element.
3. bind     - (*object*, optional) The object to use as 'this' within the function. For more information see [Function:bind][].

#### Argument: fn

##### Syntax:

	fn(item, index, object)

##### Arguments:

1. item   - (*mixed*) The current item in the array.
2. index  - (*number*) The current item's index in the array. In the case of an object, it is passed the key of that item rather than the index.
3. object - (*mixed*) The actual array/object.

### Examples:

#### Array Example:

	$each(['Sun','Mon','Tue'], function(day, index){
		alert('name:' + day + ', index: ' + index);
	}); //Alerts "name: Sun, index: 0", "name: Mon, index: 1", etc.


#### Object Example:

    //Alerts "The first day of the week is Sunday", "The second day of the week is Monday", etc:
	$each({first: "Sunday", second: "Monday", third: "Tuesday"}, function(value, key){
		alert("The " + key + " day of the week is " + value);
	});



Function: $type {#type}
-----------------------

Returns the type of object that matches the element passed in.

### Syntax:

	$type(obj);

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
	$type(myString); //Returns "string".


[Hash]: /core/Native/Hash
[Array]: /core/Native/Array
[Function:bind]: /core/Native/Function/#Function:bind
[Function:delay]: /core/Native/Function/#Function:delay
[Function:periodical]: /core/Native/Function/#Function:periodical
