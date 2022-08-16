# Type Conversion

## String + Number

const inputYear = **"1991";**

`inputYear + 18` *will return an *concatenated string\* **"1991" + 18** = **"199118"\***

> To solve this We should do Number(inputYear) + 18

    Number(inputYear +  18) = 2009

## Transform a value which is NOT a number to number

    const  stringToNumber  =  Number('Alex');

    console.log(stringToNumber);

If the value we want to convert is not at a number <br/>we will get **Not an Number (NaN)**

## Transform a number to a string

    const  numberToString  =  String(23);

    console.log(numberToString);

The above line of code will return **"23"**

# Type Coercion

## How operators convert values

| + (plus)                    | - (minus)                  | \* (multiply)              | / (dividing)               |
| --------------------------- | -------------------------- | -------------------------- | -------------------------- |
| Convert numbers to string   | Convert strings to numbers | Convert strings to numbers | Convert strings to numbers |
| "I am " + 23 + " years old" | "23" - "10" - 3            | "23" \* 2                  | "23" / 2                   |
| "I am 23 years old"         | 10                         | 46                         | 11.5                       |

### Another examples:

`2 + 3 + 4 + "5"`

#### Above line of code will result 95.

` 2 + 3+ 4 = 9.`

#### Therefore the result is: `9 + "5" = 95`

#### Same here: `"10" - "4" - "3" - 2 + "5"); 10 - 4 - 3 - 2 + '5' = '15'`
