
# eS2015

##Arrow Functions

Four versions:
    (arg1, arg2, ...) => expr
    (arg1, arg2, ...) => { stmt1; stmt2; ... }
    singleArg => expr
    singleArg => { stmt1; stmt2; ... }

the arrow function are always anonimous.(we ca not put )

- Are shorter to write

```
var func = () => {return 'I am func'};
func() 
```

- A single expression, without curly braces returns too

```
 var func = () => 'I return too';
```

- One parameter can be written without parens

```
var = 7
var func = p => p - 1;
```

- Many params require parens

```
var func = (param, param1) => param + param1;
```

- body needs parens to return an object

```
var func = () => ({iAm: 'an object'});
```


## Template Literals

Template Literals are strings that can include embedded expressions. This is sometimes referred to as string interpolation.

**Basic usage with an expression placeholder**
```
var person = 'Addy Osmani';
console.log('Yo! My name is ' + person + '!');
```

ES6:
```
console.log(`Yo! My name is ${person}!`);
```

**Expressions work just as well with object literals**
```
var user = {name: 'Caitlin Potter'};
console.log('Thanks for getting this into V8, ' + user.name + '.');
```

ES6:
```
console.log(`Thanks for getting this into V8, ${user.name}.`);
```

**Expression interpolation. One use is readable inline math**
```
var a = 50;
var b = 100;
console.log('The number is ' + (a + b) + ' and not ' + (2 * a + b) + '.');
```

ES6:
```
console.log(`The number is ${a + b} and not ${2 * a + b}.`);
```

**'Multi-line strings without needing \n\'**
```
console.log('string textline 1\nstring text line 2');
```

ES6:
```
console.log(`string text line 1
string text line 2`);
```

**Functions inside expressions**
```
function fn() {
  return 'result';
}
console.log('foo ' + fn() + ' bar');
```

ES6:
```
function fn() { return 'result'; }
console.log(`foo ${fn()} bar`);
```


## Computed Property Names

Computed property names allow you to specify properties in object literals based on expressions:

ES6:
```
var prefix = 'foo';
var myObject = {
  [prefix + 'bar']: 'hello',
  [prefix + 'baz']: 'world'
};

console.log(myObject['foobar']);
==> hello
console.log(myObject['foobaz']);
==> world
```


**Nested object destructuring**

**Deep objects**

```
// Deep objects
var {
  prop: x,
  prop2: {
    prop2: {
      nested: [ , , b]
    }
  }
} = { prop: "Hello", prop2: { prop2: { nested: ["a", "b", "c"]}}};
console.log(x, b);
```

==> Hello c


# prmosise

objecto to asynccronous operations

it is created under a 'object contructor'

new Promise( function(resolve, reject){

//Async operation

fs.readFile('demo.txt'... (as nodejs)
)
// resolve(result)
    
})


//....


promise.then(function(data))

resolve, reject ==> functions


we want to avoid the 'callback Hell' that means a lof of c¡function calling functios. Crazy stuff!!! :)

the most important is to manage promises. The most times you can choose, select a mmodule or package into 'npm'


then i is the more importatn methos

catch manage the asincronous oepration thta is execute in cascade

.catch(at the ent of all then)

cath is only to take the errr (to cath th e error)


the prmose has 3 states

pendding (initial) then you can have

fullfill ==> success

rejectes ==> fail


see the image:


librery : cheerio (manage with Jquery by class)





