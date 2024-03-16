## Callbacks
A callback is a function passed as an argument to another function.
```html
<p id="demo"></p>
<script>
	function myDisplayer(some) {
		document.getElementById("demo").innerHTML = some;
	}

	function myCalculator(num1, num2, myCallback) {
		let sum = num1 + num2;
		myCallback(sum);
	}

	myCalculator(5, 6, myDisplayer);
</script>
```
 - In the example above, `myDisplayer` is a called a **callback function**.
 - It is passed to `myCalculator()` as an **argument**.
**NOTE:** When you pass a function as an argument, remember not to use parenthesis.
```js
const myNumbers = [4, 1, -20, -7, 5, 9, -6];
function removeNeg(numbers, callback) {
    const myArr = [];
    for(let i of numbers) {
        if(callback(i)) {
            myArr.push(i);
        }
    }
    return myArr;
}
const result = removeNeg(myNumbers, (x) => x>=0)
console.log(result)
```
In the example above, (x) => x >= 0 is a callback function.

It is passed to removeNeg() as an argument.

## Waiting for a Timeout
```js
setTimeout(myFunction, 3000);

function myFunction() {
  document.getElementById("demo").innerHTML = "Hello World!";
}
```
Instead of passing the name of a function as an argument to another function, you can always pass a whole function instead:
```js
setTimeout(function() { myFunction("Hello World"); }, 3000);

function myFunction(value) {
  document.getElementById("demo").innerHTML = value;
}
```
## Waiting for Intervals
When using the JavaScript function `setInterval()`, you can specify a callback function to be executed for each interval:
```js
setInterval(myFunction, 1000);

function myFunction() {
  let d = new Date();
  document.getElementById("demo").innerHTML=
  d.getHours() + ":" +
  d.getMinutes() + ":" +
  d.getSeconds();
}
```
## JavaScript Promises
### Promise
A Promise contains both the producing code and calls to the consuming code:
```js
let p = new Promise((resolve, reject) => {
    let a = 1 + 2;
    if (a == 2) {
        resolve('Success');
    } else {
        reject('Failure')
    }
})

p.then((message) => {
    console.log('This is in the then : ' + message)
}).catch((message) => {
    console.log('This is in the catch : ' + message)
})
```

```js
// The following code is an example of using callbacks
const userLeft = false;
const userWatchingCatMeme = false;

function watchTutorialCallback(callback, errorCallback) {
    if (userLeft) {
        errorCallback({
            name: 'User Left',
            message: ':('
        })
    } else if (userWatchingCatMeme) {
        errorCallback({
            name: 'User Watching Cat Meme',
            message: 'WebDevSimplified < Cat'
        })
    } else {
        callback('Thumbs up and Subscribe')
    }
}

watchTutorialCallback((message) => {
    console.log('Success: ' + message)
}, (error) => {
    console.log(error.name + ' ' + error.message)
})
```
Rewriting the above function using Promise:
```js
const userLeft = false;
const userWatchingCatMeme = false;

function watchTutorialPromise() {
    return new Promise((resolve, reject) => {
        if (userLeft) {
            reject({
                name: 'User Left',
                message: ':('
            })
        } else if (userWatchingCatMeme) {
            reject({
                name: 'User Watching Cat Meme',
                message: 'WebDevSimplified < Cat'
            })
        } else {
            resolve('Thumbs up and Subscribe')
        }
    })
}

watchTutorialPromise().then((message) => {
    console.log('Success:', message)
}).catch((error) => {
    console.log(error.name + ' ' + error.message)
})
```
Using Promises we can solve the problem of callback hell.

Example for Waiting for a Timeout using Callback and using Promise
```js
// Waiting for Timeout using Callback

setTimeout(function () { myFunction("Hello World") }, 3000);

function myFunction(value) {
	document.getElementById("demo").innerHTML = value;
}
```
```js
// Waiting for Timeout using Promise

let myPromise = new Promise((resolve, reject) => {
	setTimeout(function () { resolve('Hello World Promise') }, 3000);
})

myPromise.then(function (value) {
	document.getElementById("demo").innerHTML = value
})
```
### Promise.all()
The Promise.all() static method **takes an iterable of promises as input and returns a single Promise** . This returned promise fulfills when all of the input's promises fulfill (including when an empty iterable is passed), with an array of the fulfillment values.
```js
const recordVideoOne = new Promise((resolve, reject) => {
    resolve('Video 1 Recorded')
})

const recordVideoTwo = new Promise((resolve, reject) => {
    resolve('Video 2 Recorded')
})

const recordVideoThree = new Promise((resolve, reject) => {
    resolve('Video 3 Recorded')
})

Promise.all([
    recordVideoOne,
    recordVideoTwo,
    recordVideoThree
]).then((messages) => {
    console.log(messages);
}).catch((error) => {
    console.log(error);
})
```
```js
const recordVideoOne = new Promise((resolve, reject) => {
    resolve('Video 1 Recorded')
})

const recordVideoTwo = new Promise((resolve, reject) => {
    resolve('Video 2 Recorded')
})

const recordVideoThree = new Promise((resolve, reject) => {
    resolve('Video 3 Recorded')
})

const recordVideoFour = new Promise((resolve, reject) => {
    reject('Video 4 Recorded')
})

const recordVideoFive = new Promise((resolve, reject) => {
    reject('Video 5 Recorded')
})

Promise.all([
    recordVideoOne,
    recordVideoTwo,
    recordVideoThree,
    recordVideoFour,
    recordVideoFive
]).then((messages) => {
    console.log(messages);
}).catch((errors) => {
    console.log(errors);
})
```
### Promise.race()
The Promise. race() static method **takes an iterable of promises as input and returns a single Promise** . This returned promise settles with the eventual state of the first promise that settles.
```js
const recordVideoOne = new Promise((resolve, reject) => {
    resolve('Video 1 Recorded')
})

const recordVideoTwo = new Promise((resolve, reject) => {
    resolve('Video 2 Recorded')
})

const recordVideoThree = new Promise((resolve, reject) => {
    resolve('Video 3 Recorded')
})

const recordVideoFour = new Promise((resolve, reject) => {
    reject('Video 4 Recorded')
})

const recordVideoFive = new Promise((resolve, reject) => {
    reject('Video 5 Recorded')
})

Promise.race([
    recordVideoOne,
    recordVideoTwo,
    recordVideoThree,
    recordVideoFour,
    recordVideoFive
]).then((messages) => {
    console.log(messages);
}).catch((errors) => {
    console.log(errors);
})
```

## async/await
The keyword `async` before a function makes the function return a promise:
```js
async function fun1() {
    return 'Data 1';
}

async function fun2() {
    return Promise.resolve('Data 2');
}

async function fun3() {
    return Promise.reject("Data 3")
}

fun1()
    .then((message) => {
        console.log('SUCCESS :', message)
    })
    .catch((error) => {
        console.log('ERROR :', message)
    })

fun2()
    .then((message) => {
        console.log('SUCCESS :', message)
    })
    .catch((error) => {
        console.log('ERROR :', message)
    })

fun3()
    .then((message) => {
        console.log('SUCCESS :', message)
    })
    .catch((error) => {
        console.log('ERROR :', error)
    })
```
The `await` keyword can only be used inside an `async` function.

The `await` keyword makes the function pause the execution and wait for a resolved promise before it continues:
```js
async function myDisplay() {
    let promise = new Promise((resolve, reject) => {
        resolve("Hello World. I am Bikash")
    })
    const result  = await promise;
    console.log(result);
}

myDisplay();
```
**Waiting for a Timeout**
```js
async function myDisplay() {
    let promise = new Promise(resolve => {
        setTimeout(() => {
            resolve("Hello World. I am Bikash!")
        }, 3000);
    });
    const result = await promise;
    console.log(result);
}

myDisplay();
```
