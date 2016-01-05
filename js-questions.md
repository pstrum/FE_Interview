
## JS Questions

### Explain event delegation



### Explain how this works in JavaScript

`this` will always reference an object. The metaphor I see most often, and specifically from Kyle Simpson, is the `this` can be thought of like the address to  building that you can then enter and go up floor by floor to access what you need. This is a big part of object oriented programing, because when you create a `new` object using a constructor function, `this` will then point to the new object that was created and it can trace back up the prototype linkage to find what you need.

## Explain how prototypal inheritance works

Prototypal inheritance is the process of cloning existing objects that serve as prototypes. A new object is created based on an old one and this new object inherits the properties of the old.

### What do you think of AMD vs CommonJS?

### Explain why the following doesn't work as an IIFE: function foo(){ }();.

- What needs to be changed to properly make it an IIFE?

### What's the difference between a variable that is: null, undefined or undeclared?

- How would you go about checking for any of these states?

### What is a closure, and how/why would you use one?

### What's a typical use case for anonymous functions?

### How do you organize your code? (module pattern, classical inheritance?)

### What's the difference between host objects and native objects?

### Difference between: function Person(){}, var person = Person(), and var person = new Person()?

### What's the difference between .call and .apply?

### Explain Function.prototype.bind.

`.bind()` creates a function and sets the `this` value to the parameter. In this case, Function.prototype 

### When would you use document.write()?

### What's the difference between feature detection, feature inference, and using the UA string?

### Explain AJAX in as much detail as possible.

### Explain how JSONP works (and how it's not really AJAX).

### Have you ever used JavaScript templating?

- If so, what libraries have you used?

### Explain "hoisting".

### Describe event bubbling.

### What's the difference between an "attribute" and a "property"?

### Why is extending built-in JavaScript objects not a good idea?

### Difference between document load event and document ready event?

### What is the difference between == and ===?

### Explain the same-origin policy with regards to JavaScript.

### Make this work:

`duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]`

I would use the array prototype method `concat`. 
How this works is that you take an initial array, which would be the argument, and call on it the `concat` method with argument the exact same argument.
This would work:
```
var duplicate = function dupfunction(initialArray) {
    var newArray = initialArray.concat(initialArray);
    return newArray;
};
duplicate([1,2,3,4,5]);
```
If you wanted to log this out, just `console.log(duplicate([1,2,3,4,5]));`.
### Why is it called a Ternary expression, what does the word "Ternary" indicate?

### What is "use strict";? what are the advantages and disadvantages to using it?

### Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5

First I would declare a variable i.
```
var i;
```
The for loop would look like this:
```
for(i = 1; i<=100; i++) {}
```
Now we write a conditional statement for our variable i.
What if i is divisible by 15? Output fizzbuzz.
```
for(i=1; i <= 100; i++) {
    if (i % 15 === 0) {
        console.log("fizzbuzz");
    }
}
```
Then I would add 3 more conditions: if i is divisible by 3, output "fizz"; if i is divisible by 5, output "buzz"; and otherwise, just output i -- the number.
```
var i;
for(i=1; i <= 100; i++) {
    if (i % 15 === 0) {
        console.log("fizzbuzz");
    } else if (i % 3 === 0) {
        console.log("fizz");
    } else if (i % 5 === 0) {
        console.log("buzz");
    } else {
        console.log(i);
    }
}
```

### Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?

### Why would you use something like the load event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?

### Explain what a single page app is and how to make one SEO-friendly.

### What is the extent of your experience with Promises and/or their polyfills?

### What are the pros and cons of using Promises instead of callbacks?

### What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?

### What tools and techniques do you use debugging JavaScript code?

### What language constructions do you use for iterating over object properties and array items?

### Explain the difference between mutable and immutable objects.

- What is an example of an immutable object in JavaScript?

- What are the pros and cons of immutability?

- How can you achieve immutability in your own code?

### Explain the difference between synchronous and asynchronous functions.

Async functions go over to the browser api and run. Like setTimeout would go over there while JS goes through it's stack. When the setTimeout finishes it goes to the task queue and the event  loop pushes it to the stack when it has cleared.

### What is event loop?

- What is the difference between call stack and task queue?


## Testing Questions

### What are some advantages/disadvantages to testing your code?

### What tools would you use to test your code's functionality?

### What is the difference between a unit test and a functional/integration test?

### What is the purpose of a code style linting tool?

## Performance Questions

### What tools would you use to find a performance bug in your code?

### What are some ways you may improve your website's scrolling performance?

### Explain the difference between layout, painting and compositing.

## Network Questions

### Traditionally, why has it been better to serve site assets from multiple domains?

### Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.

### What are the differences between Long-Polling, Websockets and Server-Sent Events?

### Explain the following request and response headers:

- Diff. between Expires, Date, Age and If-Modified-...

- Do Not Track

- Cache-Control

- Transfer-Encoding

- ETag

- X-Frame-Options

### What are HTTP actions? List all HTTP actions that you know, and explain them.

## Coding Questions

### Question: What is the value of foo?

`var foo = 10 + '20';`

JavaScript will concatenate the right-hand side reference to produce the string "1020”. Because, if you add a non-string value to a string, the value will be converted to a string and then concatenated, which means chained or linked together. Therefore, with 10 + “20”, 10 gets converted to the string “10” and then linked to “20” to make “1020”.

### Question: How would you make this work?

`add(2, 5); // 7`

`add(2)(5); // 7`

These are both functions. The first function, or method, takes two arguments and adds them together. If I was to construct this function, I would do this:
```
function add(x, y) {
  return x + y;
}
console.log(add(2, 5));  // 7
```
The second "add" function actually has another function within it that is being returned and called immediately. To construct this:
```
var add = function (x) {
  return function(y) {
    return x + y;
  };
};

console.log(add(2)(5)); // 7
```
### Question: What value is returned from the following statement?

`"I'm a lasagna hog".split("").reverse().join("”);`

The string object of "I'm a lasagna hog" is split into an array of strings, which would simply look like this:
```
["I", "'", "m", " ", "a", " ", "l", "a", "s", "a", "g", "n", "a", " ", "h", "o", "g"]
```
The `reverse()` method would then take that array and turn it around completely, so it would look like this:
```
["g", "o", "h", " ", "a", "n", "g", "a", "s", "a", "l", " ", "a", " ", "m", "'", "I"]
```
Finally, the `join()` method would join all the elements that make up the array into a single string. Array elements would be separated by a comma, so we use the "" separator so that we get the following:
```
"goh angasal a m'I"
```
### Question: What is the value of window.foo?

`( window.foo || ( window.foo = "bar" ) );`
`window.foo` would be equal to `"bar"` since 

### Question: What is the outcome of the two alerts below?
```
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```
You would get a nice big `Hello World` alert and then a reference error because `bar` is not defined for the second alert. Variable `foo` is declared in the global scope and then we have an immediately invoked function expression with variable `bar` declared with a right-hand side reference to `" World"` and an `alert` concatenating foo and bar. Finally there is an alert concatenating foo and bar, but bar isn't defined anywhere except the scope of the IIFE. 
### Question: What is the value of foo.length?
```
var foo = [];
foo.push(1);
foo.push(2);
```
Variable `foo` is declared, then it is given the value of an empty array `[]`. The `push` method adds the number 1 to the end of the array and returns the length of the array. Then the `push` method again runs and adds 2 to the end of the array and returns its length. If we ran `foo.length` we would get 2 since the array has 2 items in it.
### Question: What is the value of foo.x?
```
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```
Here is how JavaScript would compile and run this:

Variable `foo` is declared in the global scope. Variable `bar` is declared in the global scope. Variable `foo` equals an object with property `n` and value `1`. Variable `bar` is set to equal `foo`. Since `foo` doesn't have a property of `x` it would be created by the JavaScript engine and set to equal `foo`, which would be a circular object--a reference to itself. BUT, suddenly `foo` is changed to equal an object with property `n` equal to `2`. There now is no property x inside foo. Therefore, `foo.x = undefined`.

### Question: What does the following code print?
```
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```
`setTimeout` calls a function or executes a code snippet after a specified delay. In this sequence, setTimeout calls a function that logs the string `two` after `0` milliseconds. How JavaScript process this code is that it compiles any declarations (there are none) and then the engine runs the code. It would log to the console `one`, then `three`, and then `two`. This is because the `setTimeout` method has a minimum delay (even though it is set to 0 milliseconds). The function to print `two` only happens after that delay, but `one` and `three` print in order from top to bottom as the JavaScript engine processes those functions.
## Fun Questions:

- What's a cool project that you've recently worked on?
- What are some things you like about the developer tools you use?
- Do you have any pet projects? What kind?
- What's your favorite feature of Internet Explorer?
- How do you like your coffee?

## Peter Questions
### Angular
Angular is a client side JavaScript framework for adding interactivity to HTML. Angular answers the question: how do we tell our HTML when to trigger our JavaScript? Angular accomplishes this by using *directives*. A directive is a marker on an HTML tag that tells Angular to run or reference some JavaScript--it binds the behavior. "ng-app" creates an angular application by running a Angular module when the document loads. Everything inside the tag is in the Angular app and you can then insert dynamic values or *expressions*. To get data onto the page, you use *controllers*.

### Explain an implementation of CommonJS modules
Modules are a way to organize your code into separate chunks. To implement CommonJS modules, you add `module.exports = ...` to code that other files can then `requre`. When another file `require`s another, that module is cached so that there is no need to perform subsequent `require`s in other modules that will use it.

### Write a function that takes a string and prints the string and it’s substrings. For example, an input of “cake” would print:

cake
cak
ake
ca
ak
ke
c
a
k
e

Print index 0, 0+1, 0+1+2, 0+1+2+3
Print index 1, 1+2, 1+2+3
Print index 2, 2+3,
Print index 3
```
function stringPrint(text) {
  var textArray = text.split("");
  textArray.forEach(function(letter) {
    console.log(letter);
    var concat = letter;
    for(var i = text.indexOf(letter) + 1; i < textArray.length; i++) {
      concat += textArray[i];
      console.log(concat);
    }
  });
}

stringPrint("cake");
```
### Make a function called isMatch(string1, string2) that will return true if the strings match, and false if they don't. The rules are that each letter in string2 must match a letter in string1... Except that an asterisk in string1 can stand for 0 to infinity repeats of the string1's previous character to the corresponding part in string2.

### Write a function for the longest string in a sentence

```
function longestWord(sentence) {

  // Remove Punctuation
  var noPunc = sentence.replace(/[.,-\/#!$%\^&\*;:{}=\-_`~()]/g, "");

  // Split the sentence into an array
  var senArray = noPunc.split(" ");

  // Sort the array by word length
  senArray.sort(function(a, b) {

    // use 'b' first to have the right direction
    return b.length - a.length;
  });

  // Assign the first item in the array to sentence
  sentence = senArray[0];

  return sentence; 
}
```

