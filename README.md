# JavaScriptTraining
Day 1 TLDR:{
    

}


Notes:
  let keyword is block level.
  var is function block.
  functions are Objects in JavaScript.
  
  new methods notations example:
  const person = {
    name:'Osama',
    walk(){
      console.log(this)
      }
    }
  
  Accessing the method has two ways.
  1. dot notation i.e person.walk() || person.name;
  2. brackets notation person['name'] (the between the brackets can be dynamic by putting a variable instead of 'value'.)
  
  The [this] keyowrd will always give a reference to the current object.
  A reference to a method that calls the [this] keyword will console undefined in the console because the [this] reference is not accessable to the 
  defined variable that has the reference to the mehtod. (this happens in strict mode 
  becauase: it is trying to access the global object which is not allowed by strict mode)
  
  {...myObject
  
  const walk = person.walk; 
  walk() // undefined 
    to solve this we use the bind method to make the method refer to a specific Object.
  const walk = person.walk.bind(person);
  walk() // will print the reference to the object {name:'Osama', walk:f}
  }
  
  using the bind method will return a new function that has the value of [this] is based on the argument passed to the bind method   

  
  
  
  

  
  
