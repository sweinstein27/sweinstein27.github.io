---
layout: post
title:      "Closures, Scope and Hositing in JavaScript"
date:       2019-02-04 12:15:49 -0500
permalink:  closures_scope_and_hositing_in_javascript
---


## **Hoisting**

In JavaScript, a variable can be used before it has been declared. The reason this works is due to hoisting. Hoisting is JavaScript’s behavior that moves all declarations to the top of the current scope.  Not all variables are hoisted. Variables with *Let* or *Const* are not hoisted. It is important to note that JavaScript only hoists declarations and not initializations. If a variable has been declared before it is used, but not initialized yet, the value of the variable will be undefined.  To avoid bugs, developers should declare all variables at the beginning of every scope. 

## **Scope**

Scope is the accessibility of variables, functions and objects in your code, when the code is being run. Scope determines the visibility of variables in your code. 

JavaScript has two types of scopes: global and local scope. A variable defined within a function is in local scope. Variables defined outside of a function are in the global scope. 

When you begin coding JavaScript, you are in the global scope. There is only one global scope throughout a document. A variable in global scope can be accesses or altered in other scopes. Variables defined within a function exist in the local scope. As a result of this, variables with the same name can be used in different functions. 
*Let* and *Const* were introduced in ECMAScript 6 and can be used in place of *Var*. *Let* and *Const* support the declaration of local scope inside block statements, while *Var* does not. 

## **Context**

Context is used to refer to the value of this in a portion of your code. When a function is called as a method of an object, *this* is set to the object the method is called on. The same principle applies when invoking a function with the new operator to create an instance of an object. When invoked in this manner, the value of *this* within the scope of the function will be set to the newly created instance. When called as an unbound function, *this* will default to the global context or window object in the browser 

## **‘This’ in Arrow Functions**

One of the most exciting features of ES6 was the introduction of arrow functions, which have a shorter syntax than their predecessor. Arrow functions do not bind their own* this*, arrow functions bind to their context, so *this* actually refers to the originating context. 

## **Closures**

Accessing variables outside of its immediate lexical scope creates a closure. A closure is formed when a nested function is defined inside of another function, allowing access to the outer function’s variables. Returning the nested function allows you to maintain access to the local variables, arguments, and inner function declarations of its outer function. An example looks like the following:

![](http://dmitriilin.com/wp-content/uploads/2018/05/use-closures-for-custom-js-variables-in-GTM-closure-min.jpg)
 



