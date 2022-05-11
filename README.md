# Javascript Day 6 (QA)


#### 1- What is a function & it's types?
A JavaScript function is a block of reusable code designed to perform a particular task. A JavaScript function is executed when "something" invokes it (calls it).

```
const loopUpto = 10;
  let output1 = 1;
  for (let i = 0; i < loopUpto; i = i + 2) {
    output1 = output1 + i;
  }

  console.log("Output: 1", output1);
```

```
const loopUpto2 = 100;
  let output2 = 1;
  for (let i = 0; i < loopUpto2; i = i + 2) {
    output2 = output2 + i;
  }

```

  In both code above,there is only difference of "loopUpto" and "loopUpto2" and rest of the code is getting repeated.
  Instead of this we can use reusable code.

```
  function sumUpto(limit) {
    let result = 1;
    for (let i = 0; i < limit; i = i + 2) {
      result = result + i;
    }

    return result;
  }

  console.log(sumUpto(10));
  console.log(sumUpto(100));
```

  Here "loopUpto" and "loopUpto2" can be replace by limit.So Whatever are changes just replace it with parameters by              passing them when the function get called. 

There are mainly four type of functions
1)Normal Function
2)Variable Function
3)Immediately Invoked Function Expression (IIEF)
4)Anonymous functions
                                                                                    Normal Functions
Syntax:

//Only writting of function is known as function defination.While writting a function the parameters which we provide in bracket are known as params or parameters.

function functionName(param1,param2)
{
    Function Body
}

//Function Calling
functionName(argument1,argument2)

```
  // Normal Function
  function uniqueName(a, b, c, d) {
    return "Vishal";
  }

  uniqueName(); 
  uniqueName(1); 
  uniqueName("Ankit"); 
  uniqueName(1, 20, 100)

  output for each function will be "Vishal" since uniqueName function is getting call each time.

```

Checking values for a,b,c,d
If you don't give any value to arguments then they will take undefined

```
 Normal Function
  function uniqueName(a, b, c, d) {
    console.log("value of a is "+ a )
    console.log("value of b is "+ b )
    console.log("value of c is "+ c )
    console.log("value of d is "+ d )
  }

uniqueName();  
value of a is undefined
value of b is undefined
value of c is undefined
value of d is undefined

uniqueName(1);  
value of a is 1
VM541:3 value of b is undefined
VM541:4 value of c is undefined
VM541:5 value of d is undefined

uniqueName("Ankit");  
value of a is Ankit
VM613:3 value of b is undefined
VM613:4 value of c is undefined
VM613:5 value of d is undefined

uniqueName(1, 20, 100)
value of a is 1
VM658:3 value of b is 20
VM658:4 value of c is 100
VM658:5 value of d is undefined
```
#### 2- Why are we using return inside a function?

   Whenever we called a function successfully at that time what value should be give to caller is given in return.
#### 3- What is console logging in a function?
   Console logging in a function is mainly used by a developer to print the data in a console.  This is used by a developer to         debug the code.

#### 4-Are functions arguments are mandatory?
 Functions arguments are not mandatory.It will take default value if it is there else it will show "undefined" for those parameters.

#### 5-Can we call a function without an argument if it is having params defined?

Yes.We can call a function without an argumnet if it is having params defined.  In this case The params will get undefined 
   value.
```
  function uniqueName(a, b, c, d) {
    return "Vishal";
  }

    uniqueName()
The function will get call and return "Vishal" but   
value of a is undefined 
value of b is undefined 
value of c is undefined 
value of d is undefined
    
```

#### 6-What are default argument?

If there is no value given by arguments then in that case we will be having a default value for params. This values we need to decide.In this case falsy value will also be treated like normal values except undefined.
```
  // Default Argument
function getName2(a = "No", b = 20) {
    return 'value of a= '+a + ' ,value of b = '+b;
  }

  console.log(getName2(0));
  console.log(getName2(null));
  console.log(getName2(false));
  console.log(getName2(undefined));

Output
value of a= 0 ,value of b = 20
value of a= null ,value of b = 20
value of a= false ,value of b = 20
value of a= No ,value of b = 20
```
#### 7-What is variable function?

The Functions which are stored in variables and do not need function names are known as variable function. They are always invoked (called) using the variable name. The function above ends with a semicolon because it is a part of an executable statement.

```
var fun1 = function name(a, b) {
    return a + b;
  };

  let fun2 = function (a, b) {
    return a + b;
  };

  const fun3 = function (a, b) {
    return a + b;
  };

  console.log(fun1(2, 9));
  console.log(fun2(2, 9));
  console.log(fun3(2, 9));
```

#### 8-What is anonymous function?

The function which do not have a name are known as anonymous functions.

#### 9-What is Function expression or variable function & it's usage & why we're using it?

The main difference between function declaration and function expression allow us to create an anonymous function which doesn’t have any function name.
The function expression can be used as functions which will run as soon as its define.
We can access them with variable name.

Syntax for Function Expression (anonymous) :  

```
let variableName = function(x, y) { statements... return (z) };
```
Syntax for Function Expression (named) :  

```
let variableName = function functionName(x, y) 
{ statements... return (z) };
```

Since this functions are declare with variable name like var,let,const so we cant access before their defination.
```
The following code will give you an error since we are accessing the variable function before their declaration and defination.So it will give you an error in console.

  console.log(fun1(2, 9));
  console.log(fun2(2, 9));
  console.log(fun3(2, 9));

  var fun1 = function name(a, b) {
    return a + b;
  };

  let fun2 = function (a, b) {
    return a + b;
  };

  const fun3 = function (a, b) {
    return a + b;
  };
```

This is only allowed in normal function.

```
console.log(sumUpto(10)); 
 function sumUpto(limit) { 
    let result = 1; 
    for (let i = 0; i < limit; i = i + 2) { 
      result = result + i; 
    } 
    return result; 
  }
//The Output of this will get display and accessing normal functions before there declaration and defination is possible.
```
#### 10-How browser is understanding & executing JS code?

There are basically two modes.
1)Creation Mode:In this mode browser just scan the js and it will allocate the space in memory for variables which are declare with "var" keyword with undefined value.

2)Execution mode: In this mode it will allocate actual data in all variables.



