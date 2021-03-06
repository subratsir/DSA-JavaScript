# Difference between normal function and arrow function

- Arrow functions do not have their own this value. The value of this inside an arrow function is always inherited from the enclosing scope.

```js
name = "Suresh";
let a = {
   name : "Ramesh",
   ab : function(){
	console.log(this.name);
   }
}
a.ab(); // Ramesh
console.log(name); // Suresh

let b = {
   name : "Mahesh", 
   ac : () => {
	console.log(name);
   }
}
b.ac(); // Suresh
console.log(name); // Suresh
```

- Arrow functions do not have arguments array  

```js
function a(){
	console.log(arguments);
}

a(2,3,4,5);
```

```
[object Arguments] {
  0: 2,
  1: 3,
  2: 4,
  3: 5
}
```

```js
let b = () => {
	console.log(arguments);
}

b(2,3,4,5);
```

```
Uncaught ReferenceError: arguments is not defined
```

- If a function is constructable, it can be called with new, i.e. new User(). If a function is callable, it can be called without new (i.e. normal function call). Arrow functions are callable but not constructable.
  
```js
let a = function(name, roll){
	this.name = name,
  this.roll = roll,
  this.prin = function(){
  	console.log(`Roll number of ${this.name} is ${this.roll}`);
  }
}

let b = new a("Subrat", 15);
b.prin(); // Roll number of Subrat is 15
```

```js
let c = (name, roll) => {
	this.name = name,
  this.roll = roll,
  this.prin = function(){
  	console.log(`Roll number of ${this.name} is ${this.roll}`);
  }
}

let d = new c("Ramesh", 15);
d.prin(); // Uncaught TypeError: c is not a constructor
```


  [Home](https://github.com/subratsir/DSA-JavaScript/blob/main/subratsir/README.md)

         
         
         
