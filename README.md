# JavaScriptTraining

Day 14 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    2. problem solving

Notes:

xhr vs fetch

function sendHttpRequest(method, url, data) {
  const promise = new Promise((resolve, reject) => {
  const xhr = new XMLHttpRequest();
  xhr.setRequestHeader('Content-Type', 'application/json');

    xhr.open(method, url);

    xhr.responseType = 'json';

    xhr.onload = function() {
      if (xhr.status >= 200 && xhr.status < 300) {
        resolve(xhr.response);
      } else {
  xhr.response;
        reject(new Error('Something went wrong!'));
      }
      // const listOfPosts = JSON.parse(xhr.response);
    };

    xhr.onerror = function() {
      reject(new Error('Failed to send request!'));
    };

    xhr.send(JSON.stringify(data));
  });

  return promise;
  }
  
  
  function sendHttpRequest(method, url, data) {
	  return fetch(url, {
	    method: method,
	    body: JSON.stringify(data),
	    headers: {
	      'Content-Type': 'application/json'
	    }
	  })
	    .then(response => {
	      if (response.status >= 200 && response.status < 300) {
		return response.json();
	      } else {
		return response.json().then(errData => {
		  console.log(errData);
		  throw new Error('Something went wrong - server-side.');
		});
	      }
	    })
	    .catch(error => {
	      console.log(error);
	      throw new Error('Something went wrong!');
	    });
	}
  
  
  
  

Day 13 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    2. problem solving

Notes:


	1.	... the spread operator is used to create real copies of reference values.
	
	let arr = ['sports'];
	
	let arr1 = arr; // this will only store the address of the arr.
	to make an actual copy we need to use the spread operator.
	
	let realCopy = [...arr];
	
	const only records the address of objects (arrays, and actual objects) so data manipulation is possible through the array 
	apis such as (push, pop, ect). 
	
------


	2. a function inside the event listener can lead to a memory leak because of the function being created every time as 
	anonymous function.
	
------


	3. unshift(element) adds to the beginning of the array. 
	   push(element) adds to the end of the array.
	   
	   shift() deletes the first element of the array.
	   pop() deletes the last element of the array.
	   
	   splice(index, numOElementsToDelete, element to insert);
	   We can use splice to insert elements inside the array.
	   ex: splice(1, 0, 'my New Item') // this will insert an item at index 1.
	   
		element.classList.toggle('cssclass');
	   
	   


Day 12 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    2. problem solving

Day 11 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    2. problem solving

Notes:
	
	forof syntax
	
	`
	for(const item of arr){
	
	}
	`
	
	
	forin syntax
	
	`
	for(const key in obj){
	
	}
	`
	
	
	
	
Day 10 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    2. problem solving

Notes:


	const userName = 'Max';
	const altName = '';
	console.log(userName === 'Max'); // generates and prints a boolean => true
	console.log(userName); // wasn't touched, still is a string => 'Max'


	console.log(userName || null); // userName is truthy and therefore returned by || => 'Max'
	console.log(altName || 'Max'); // altName is falsy (empty string), hence 'Max' is returned => 'Max'
	console.log(altName || ''); // both altName and '' are falsy but if the first operand is falsy, the second one is always returned => ''
	console.log(altName || null || 'Anna'); // altName and null are falsy, 'Anna' is returned => 'Anna'


	console.log(userName && 'Anna'); // userName is truthy, hence second (!) value is returned => 'Anna'
	console.log(altName && 'Anna'); // altName is falsy, hence first value is returned => ''
	console.log(userName && ''); // userName is truthy, hence second value is returned => ''
	
	
	
	switch(event){
	 	case first_event:
		 //do something
		 break;
		 case second_event:
		 //do something
		 break;
		 default: 
		 //code here will executed no matter a case is found or not.
	 }
	
	switch statements always use the triple equals to decide 
	
	

Day 9 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    

Notes:

	1. double bang (!!) converts truthy and falsy values to truth and false values.
	2. refernce to episode 95 Very Improtant info



Day 8 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    

Notes:


	1. ternary operator is a solution for conditional values.
	`  const val = (condition)? true:false; `
	
	

 Day 6 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    

Notes:
	`==` checks for value equality only. However, `===` compares value and type.
	
	
	Truthy and falsy values:
	
	
	 1. 0 --> false.
	 
	 
	 2. any other number other than 0 (including negative values) --> true.
	 
	 
	 3. "" empty strings are considered --> false.
	 
	 
	 4. Any other non-empty string including "false" --> true.
	 
	 
	 5. All objects ({} & []) --> true.
	 
	 
	 6. null, undefined, and NaN --> false. 
	 
	
	
 Day 5 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    

Notes:
	The defered way of importing the JS is much faster than the traditional way.
	
	Async can be used in the import tab to execute code directly when possible but it can lead to some issues so we use it only 
	in standalone scripts.
	
	defer and async can be only used in imported scripts not with scripts that exist in script tags.
	
  
	
 Day 4 TLDR:

    Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    Problem solving on codewars 
  
	
 Day 3 TLDR:

    1. Watching the JavaScript - The Complete Guide 2023 (Beginner + Advanced)
    

Notes:
  
	We can redefine global variables in local scopes in a process called shadowing.
	
	
	When we add an event listenr to we pass a string that has the action, then we pass the address of the function we want to call.
	
	To parse a string value we can use the built in function parseInt(string) or we can use the + like this.
	`currentResult = currentResult + +userInput.value;` // but if we want to be more precise we must use parseInt or parseFlaot 
	
	the increment and decrement operators ++ or -- change the return value based on their placement on the variable.
	++var will return the edited value var++ will return the value before editing
	

	
  Day 2 TLDR:

    1. Learning about Classes and Objects.
    
    2. Inheritance and constructors.
    
    3. Modulaity (export and import).
    

Notes:
  
	Classes are named using the pascals naming convention. (ex: CoolPerson)
	
	Classes are blueprints to create objects.
	
	One of the main uses for class is error handling and eleminating redunduncy.
	
	Inheritance allows childern to access methods that exist in the parent.
	
	To edit the child class constructor we need to call the super method to send the parameter to 
	parent.
	
	Moduals are private by default we need to make them public using the export keyword then import it with 
	` import moduleName from 'module' `
	
	A class is an object in JavaScript that has a construtor method.
	
	We use the carly brases only to import the named export.
	
	the types of exports are:
	//Default ->	` import moduleName from 'module' `  
	
	
	//named ->	` import { ... } from 'module' `  
	
	
Day 1 TLDR:

    1. Understanding ES6 Objects methods declaration and difference between let and var.
    
    2. learning about the this keyword and behavior.
    
    3. learning Object Destructuring.
    
    4. learning about the Spread Operator.


Notes:

      let keyword is block level.

      var is function block.

      functions are Objects in JavaScript.

      Arrow functions do not rebind [this] keyword unlike old functions. The arrow function inherits the [this] 
      value of it's parent object.

      Template literals can be used in the map function `<li>${var}</li>` 

  new methods notations example:
  `const person = {
    name:'Osama',
    walk(){
      console.log(this)
      }
    }`
  
  Accessing the method has two ways.
  1. dot notation i.e person.walk() || person.name;
  2. brackets notation person['name'] (the between the brackets can be dynamic by putting a variable instead of 'value'.)
  
  The [this] keyowrd will always give a reference to the current object.
  A reference to a method that calls the [this] keyword will console undefined in the console because the [this] reference is not accessable to the 
  defined variable that has the reference to the mehtod. (this happens in strict mode 
  becauase: it is trying to access the global object which is not allowed by strict mode)
  
  `{...myObject
  
  const walk = person.walk; 
  walk() // undefined 
    to solve this we use the bind method to make the method refer to a specific Object.
  const walk = person.walk.bind(person);
  walk() // will print the reference to the object {name:'Osama', walk:f}
  }`
  
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
   
   `const firstList = [1, 2, 3];
   const secondList = [4, 5 ,6];`
   
   //old way
   
   `const combined = firstList.concat(secondList)`
   
   //new way
   
   `const combined = [...firstList, ...secondList] `
   // we can also do 
   `const combined = [...firstList, 'a',...secondList]`
  
  Spread operator also works on Objects
  
  
    const firstObj = {name:'Osama'}
  
  
    const secondObj = {job:'Front-end developer'}
    
  
     const combined = {...firstObj, ...secondObj, location:'Jordan'}` // logging this will result in a new object that has both attributes with the new attribute
  
  

	
	
	


	
	
	
	
	
	
	
	
	
	
  
  
