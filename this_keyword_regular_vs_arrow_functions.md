
# This keyword (regular function vs arrow function)

const cloudstar = {

```
 name: ‘Cloudstar’,

 year : 1998,

 sayName = function() {

    console.log(‘My name is: ${this.name}

 },

 calcAge: function() {

      console.log(this)

      console.log(‘You are age: ${this.year - 2022} years’

  }
}

cloudstar.calcAge()
```





Here the result will be as you guessed already **23 years**

```
const cloudstar = {
	 name: ‘Cloudstar’,

	 year : 1998,

	 sayName = function() {

	    console.log(‘My name is: ${this.name}

	 },

	 calcAge: () ⇒ {

	      console.log(this)

	      console.log(‘You are age: ${this.year - 2022} years’

	  }
}

cloudstar.calcAge()
```

Will result to **undefined**. Because the **this** keyword into the **arrow function** will **point to window object** (global scope) and the **year** is **not defined** there.

Lets see another example of this keyword.



```
const cloudstar = {
 name: ‘Cloudstar’,
 year : 1998,
 sayName = function() {
    console.log(‘My name is: ${this.name}
    
    const showBirthdayYear = function() {
	console.log(this.year)
	}
	
	showBirthdayYear()

 },

 calcAge: () ⇒ {
      console.log(this)
      console.log(‘You are age: ${this.year - 2022} years’

  }
}
```



So now let's call `cloudstar.sayName()`

Note that `sayName` have a function inside and after it’s declaration is calling it. Could you guess what will be the result?

> Cannot read property of undefined because it’s don’t have a object
> attached to it

So in order to make it work we can attach a new variable before the function declaration: `const self = this;`

```

 sayName = function() {
    console.log(‘My name is: ${this.name}

	const self = this;
	const showBirthdayYear = function() {
		console.log(self)
		console.log(self.year)
	}
	  
	showBirthdayYear()
 }
```

Now the result we get from `showBirthdayYear()` will be **1998**.

**Self will become the cloudstar object**. Because cloudstar it’s calling the sayName function & that is calling `showBirthdayYear()`.

## Alternative solution.

Instead of creating a new variable self = this. We can transform the showBirthdayYear to an arrow function. Why you may asking? 
Because the arrow function **doesn't** have it’s own scope for **this** keyword and **it’s looking up to it’s parent scope to get it**.