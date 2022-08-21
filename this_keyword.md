#  This keyword

  

    const sayName = function(name) {
        console.log(name)
        console.log(this)
    }
    
    sayName(‘Cloudstar’)

  

In this function the **this** keyword will be **undefined**. Why? Because function declaration have **own scope for this keyword.** And as they are not attached to any object or so they will get undefined.

  

    const sayName = (name) ⇒ {
            console.log(name)
            console.log(this)
       }
        
       sayName(‘Cloudstar’)

  

In this function the **this** keyword will return the **window object.** Why? Because arrow function take the lexical scope**strong text** of the **parent scope**. So as it is defined on the **global scope** the parent of the arrow function is the **window**.

  

Let’s see now how the this keyword can work.

  

     const cloudstar = {
            name = ‘Cloudstar’,
            sayName = function() {
                console.log(`My name is: ${this.name}`
            }
    cloudstar.sayName()

  

Here the this keyword will point to the cloudstar object. So basically the **`this.name`** can be translated to **`cloudstar.name`**

  

Note: the **this** keyword will not point to **cloudstar** because is defined into the **object cloudstar**. Will point to it because that **object is calling the method sayName**. Let’s take another example.

  

    jonas = {name: ‘Jonas’ }
    jonas.sayName = cloudstar.sayName

  

The above line is calling **object borrowing** (we basically borrow the sayName method from cloudstar and give it to jonas object)

  

And now if we call **jonas.sayName()** the result will be as you guessed already: **‘Jonas’**. Why is that?

  

Because **jonas object** is calling the sayName method.

  

And let’s take a last look into this.

  

const something = cloudstar.sayName

  

And now let’s **simply call it**.

  

    something()

  

Can you guess the example?

  

Corect! It **cannot read property name of undefined**. Why? It is because we simply call the method **without attaching to any object** which contains the name.