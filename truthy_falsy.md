## Truthy & Falsy

> <h3>The falsy values are not really false. <br/> But will become false
> once we convert to a boolean</h3>

<h4>In JS we have 5 values which are falsy</h4>

| 0 (zero) | " " (empty string) | Undefined | Null | NaN |
| -------- | ------------------ | --------- | ---- | --- |

    Boolean(0) // * -> false

    Boolean(undefined) // * -> false

    Boolean('Alex') // * -> true

    Boolean({}) // * -> true

    Boolean('') // * -> false

  <br/>
Type coercion examples <br/>
Basically here JS will transform <strong>falsy</strong> into false & <strong>truthy</strong> into true

    const  personHaveMoney  =  money  =>  {

    if (money) {

    console.log("Don't spend it all :)");

    }  else  {

    console.log('You should get a job');

    }

    };

<br/>

    personHaveMoney(0);  // * You should get a job
    personHaveMoney(100);  // * "Don't spend it all :)

Another Example:

    let  height  =  0;

    const  isHeightDefined  =  ()  =>  {

    if (height) {

    console.log('YAY! Height is defined');

    }  else  {

    console.log('Height is UNDEFINED');

    }

    };

<br/>

    isHeightDefined();  // * let height; Height is undefined. Because UNDEFINED is FALSY

    isHeightDefined();  // * let height = 123 ; Height is undefined. Because UNDEFINED is FALSY

    isHeightDefined();  // * let height = 0 ; Height is undefined. Because 0 is FALSY
