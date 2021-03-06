<script>{
	"title": "Testing Type",
	"level": "beginner",
	"source": "http://jqfundamentals.com/legacy",
	"attribution": [ "jQuery Fundamentals" ]
}</script>

JavaScript offers a way to test the type of a variable. However, the result can be confusing – for example, the type of an array is `object`.

It's common practice to use the `typeof` operator when trying to determining the type of a specific value.

```
// Testing the type of various variables.
var myFunction = function() {
	console.log( "hello" );
};
var myObject = {
	foo: "bar"
};
var myArray = [ "a", "b", "c" ];
var myString = "hello";
var myNumber = 3;
var myRegExp = /(\w+)\s(\w+)/;

typeof myFunction; // "function"
typeof myObject;   // "object"
typeof myArray;    // "object" -- Careful!
typeof myString;   // "string"
typeof myNumber;   // "number"
typeof null;       // "object" -- Careful!
typeof undefined;  // "undefined"
typeof meh;        // "undefined" -- undefined variable.
typeof myRegExp;   // "function" or "object" depending on environment.


if ( myArray.push && myArray.slice && myArray.join ) {
	// probably an array (this is called "duck typing")
}

if ( Object.prototype.toString.call( myArray ) === "[object Array]" ) {
	// Definitely an array!
	// This is widely considered as the most robust way
	// to determine if a specific value is an Array.
}
```

jQuery also offers [utility methods](/using-jquery-core/utility-methods#testing-type) to help determine the type of an arbitrary value.
