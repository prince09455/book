## Explain `this` keyword in javascript

`this` is a keyword in javascript its value depends on how function is called . there are four cases
1) arrow function :- ``this`` is always undefind inside arrow function.
2) dot operator :- when function is called with dot (.) operator then `this` is equal to object before the dot operator.
 ```javascript
 const x= {
    a : 1,
    b : 2,
    c : function (){
        console.log(this);
    }
 }
 
 x.c(); // here `this` keyword is equal to x inside c.
 ```

 3) new keyword :- when function is called with `new` keyword then 
    - an empty object is created inside function and assigned to `this` keyword
    - always `this` is return
```javascript 
    function User(firstName, lastName){
        // this = { } (implicit)
        this.firstName = firstName;
        this.lastName = lastName;
        console.log(this);
        // return this; (implicit)
    }
    let y = new User('first', 'last');

```
4) default case: in all other cases `this` keyword is equal to `window` object.


## explain new keyword in javascript
same as no 3 of above question.

## explain class in javascript
Class is just syntatical sugar over function.
class can be implemented using `new` keyword in javascript.

```javascript
     function User(firstName, lastName){ //this is called as constructor function
        this.firstName = firstName;
        this.lastName = lastName;
    }

    class User{
        constuctor(firstName, lastName){ 
            this.firstName = firstName;
            this.lastName = lastName;
        }
    }
```
both are equivalent. 

```javascript
     function User(firstName, lastName){ //this is called as constructor function
        this.firstName = firstName;
        this.lastName = lastName;
    }
    User.prototype.test= function(){
        console.log("test");
    }


    class User{
        constuctor(firstName, lastName){ 
            this.firstName = firstName;
            this.lastName = lastName;
        }
        test (){
            console.log("test");
        }
    }
```

## Object.keys(), Object.values(), Object.entries().
## currying
when a function returns function it is called currying. it can be used to fix some arguments.
ex- 
```javascript

function sum(a){
    return function (b){
        console.log(a+b);
    }
}

const sumWithTwo= sum(2);
sumWithTwo(3);


```
## bind call apply
these are used to assign value of `this` keyword.
1) `.bind` accepts one argument which is assigned to `this` keyword. returns function with updated value of `this`.
ex -
```javascript

    function test(a){
        console.log(this, a)
    }
    let y = test.bind({})
    y(123) // logs {} 123
```

2) `.call` accepts multiple arguments . first argument assigned to `this` keyword and remaining arguments passed to the function.
    it calls the function unlike `.bind`;

    ```javascript
    function test(a){
        console.log(this, a)
    }
     test.call({}, 123) // logs {} 123
    ```

3) `.apply` accepts two arguments first argument is assigned to `this` keyword. seacond argument is of type array.
    array is spred and paased as arguments to original function.

     ```javascript
    function test(a){
        console.log(this, a)
    }
     test.call({}, [123]) // logs {} 123
    ```

## logical questions related to unique element in array




## optional chaining
```javascript
const  apiResponse = {
 
  address: {
    society: {
      block: 'a',
      floor: 2,
       corridor: {
        isAvailable: false
      }
    }
  }
 
}

const corrdiroAvailable = Boolean(apiResponse.address.society.corridor?.isAvailable)

```
## string literal 
```javascript
const x = `${variable} hello`; 
```

