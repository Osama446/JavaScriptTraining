# JavaScriptTraining
Day 1 TLDR:{
    Understanding ES6 Objects methods declaration and difference between let and var,
    learning about the this keyword and behavior.
    learning Object Destructuring.
    learning about the Spread Operator.
    
}


Notes:
  let keyword is block level.
  var is function block.
  functions are Objects in JavaScript.
  Arrow functions do not rebind [this] keyword unlike old functions. The arrow function inherits the [this] 
  value of it's parent object.
  Template literals can be used in the map function `<li>${var}</li>` 
  
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
  
  using the bind method will return a new function that has the value of [this] is based on the argument passed to the bind method.
  
  
  
  
  Object destructuring:
  
  const address ={
        street:'',
        city:'',
        country:''
    };
    
//old way
    const street = address.street;
    const city = address.city;
    const country = address.country;

//new way
    const { street, city, country } = address; // we do not need to call all the properties of the object we can choose as needed.
    const { streeet : st } = address // we can assign aliases to the object variables.
    
   
   Spread operator:
   const firstList = [1, 2, 3];
   const secondList = [4, 5 ,6];
   //old way
   const combined = firstList.concat(secondList)
   //new way
   const combined = [...firstList, ...secondList] 
   // we can also do 
   const combined = [...firstList, 'a',...secondList]
  
  Spread operator also works on Objects 
  const firstObj = {name:'Osama'}
  const secondObj = {job:'Front-end developer'}
  const combined = {...firstObj, ...secondObj, location:'Jordan'} // logging this will result in a new object that has both attributes with the new attribute
  
  

  
  
