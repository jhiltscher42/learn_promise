learn_promise
=============

I made this module to make sure I knew how the Promise/A+ spec worked, and do not recommend anyone else use it, as it is not optimized, and will not be maintained as there are already several alternative libraries that do better than jQuery.

It is meant to be used with AMD (I used requireJS) and returns a plain JS object 

{
   promise(),  //constructor for an implementation of Promise/A+ promise, has a compliant .then(suc,fail) method, an    
               //.always(both) method, a .resolve(val) method, a .reject(err) method and a .restricted property which 
               //exposes the instances .then and .always methods
   
   all(a,b,...z), // utility function returns a promise which resolves with the array of resolved values of it's 
                  //arguments, if they all resolve, or rejects at the first reject.
   
   any(a,b,...z), //utility function which resolves to the value of the first of it's arguments to resolve, 
                  //and disgards the rest.
   
   some(a,b,...z),// utility function which resolves when all of its arguments resolve or reject
   
   delay(ms),     // utility function which lifts setTimeout into a promise which resolves after ms milliseconds
   
   liftNormal(fn),// utility function which takes a function that may return a normal value and turns it into a function 
                  // which returns a promise that resolves to that normal value.  If fn already returns a promise, the new                   //function's promise and reject methods are bound to it.  (ie, you don't need to unwrap the promise 
                  //value with .then twice)
   
   }
   
