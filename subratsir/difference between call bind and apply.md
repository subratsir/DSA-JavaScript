
~~~js
let print1 = function(){
  console.log(this.name);
}

let userDetails1 = {
  name : "Subrat Dash",
  desig : "Software Developer,
  print2 : function(){
    console.log(this.name);
  }
}

userDetails1.print2(); // Subrat Dash
// Function Borrowing
print1.call(userDetails1); // Subrat Dash

let userDetails2 = {
  name : "Ramesh Jena",
  desig : "Software Developer"
}

// Function borrowing
userDetails1.print2.call(userDetails2); // Ramesh Jena
print1.call(userDetails2); // Ramesh Jena

let print3 = function(state,country){
  console.log(this.name+" is from "+state+", "+country);
}

let newFn = print3.bind(userDetails2,"Odisha","India.");
newFn() // Ramesh Jena is from Odisha, India.

print3.apply(userDetails2,["Odisha","India."]); // arguments are passed as array. rest it works as call

~~~