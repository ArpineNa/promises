# promises

Promises introduction in JavaScript
№1
Make a promise, inside which there will be a delay of 5 seconds, after which the promise should be fulfilled, returning some text as its result. Display this text on the screen.


const promise = new Promise(function(resolve) {
	setTimeout(function() {
		resolve("Hi Hakob");
	}, 5000);
});

promise.then(function(result) {
	console.log(result);  
});

 // 
PS C:\Users\Armen\OneDrive\Desktop\AGBU\lesson3> node ana      
Hi Hakob



Exceptions within promises in JavaScript

№1
 
Make an async code that will generate random numbers from 0 to 5. Wrap it all in a promise. Let the promise return the result of dividing one by the generated number. Let the promise fail if a division by zero occurs, and succeed in all other cases.


const data =[0,1,2,3,4,5]

const promise = new Promise(function generateRandomNumber(resolve, 
	reject) { 
	setTimeout(function generateRandomNumber() {
		const randomNumber = Math.floor(Math.random() * 6);
		
		if (randomNumber === 0) {
			resolve(1 / randomNumber);
			} 
				else {
			reject("Division by zero is not allowed.");
		}
	}, 3000);
}); 



promise.then(function generateRandomNumber(result) {
	console.log(result); 
}, function generateRandomNumber (error) {
	console.log(error);  
});




PS C:\Users\Armen\OneDrive\Desktop\AGBU\lesson3> node ana
Division by zero is not allowed.


Object with a promise error in JavaScript
№1

Modify the following code according to what you learned:
let promise = new Promise(function(resolve,
	reject) { 
	setTimeout(function() {
		let isError = false;
		if (!isError) {
			resolve('success');
		} else {
			reject('error');
		}
	}, 3000);
});

2.    const promise = new Promise(function(resolve,
	reject) { 
	setTimeout(function() {
		const isError = false;
		if (!isError) {
			resolve('success');
		} else {
			throw new Error ('error');
		}
	}, 3000);
});

Individual exception catching in promises in JavaScript
№1

Rewrite the following code via the catch method:
let promise = new Promise(function(resolve,
	reject) { 
	setTimeout(function() {
		let isError = false;
		if (!isError) {
			resolve('success');
		} else {
			reject(new Error('error'));
		}
	}, 3000);
});
promise.then(
	res => console.log(res),
	err => console.log(err.message),
);



const promise = new Promise(function(resolve, 
	reject) { 
	setTimeout(function() {
		let isError = false;
		
		if (!isError) {
			resolve('success');
		} else {
			reject(new Error('error'));
		}
	}, 3000);
});

promise.then(
	res => console.log(res),
	).catch (
		err => console.log(err.message),
		)
PS C:\Users\Armen\OneDrive\Desktop\AGBU\lesson3> node ana
success


Promise states in JavaScript

№1
Make a promise that will succeed after some time. Print it to the console and examine its initial state and completed state.

const promise = new Promise (function(resolve, reject) {
            setTimeout(() => {
                let isError = false;
                
                if (!isError) {
                resolve('ignored ');
        }else {
			reject('error');
		}
	}, 3000);
    });

    setInterval(function() {
        console.log(promise); 
    }, 1000);


PS C:\Users\Armen\OneDrive\Desktop\AGBU\lesson3> node ana
Promise { <pending> }
Promise { <pending> }
Promise { 'ignored ' }
Promise { 'ignored ' }
Promise { 'ignored ' }
Promise { 'ignored ' }
Promise { 'ignored ' }

№2

Make a promise that will fail after some time. Print it to the console and examine its initial state and completed state.
const promise = new Promise (function(resolve, reject) {
                setTimeout(() => {
                    let isError = false;
                    
                    if (!isError) {
                    resolve('error ');
            }else {
    			reject('aaaa');
    		}
    	}, 3000);
        });
    
        setInterval(function() {
            console.log(promise); 
        }, 1000);
    
    promise.then((result) => {
        console.log('Completed state:', promise);
        console.log(result);
    }).catch((error) => {
        console.error('Error:', error);
    });

PS C:\Users\Armen\OneDrive\Desktop\AGBU\lesson3> node ana
Promise { <pending> }
Promise { <pending> }
Completed state: Promise { 'error ' }
error 
Promise { 'error ' }
Promise { 'error ' }
Promise { 'error ' }
Promise { 'error ' }
