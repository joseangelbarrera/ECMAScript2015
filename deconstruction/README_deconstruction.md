#Deconstruction

[Notes fron Juanma](https://github.com/addyosmani/es6-equivalents-in-es5#destructuring-assignment)

## Template Strings



**A template string, is wrapped in ` (backticks) instead of \' or "'**

```
var str = `like a string`;
```

**Can evaluate variables an functions, which are wrapped in "${" and "}"**

```
'x' = ${x}
"x + '+' + y" = `${x}+${y}`
'x+y' = `${x+y}`;
var evaluated = `${ getDomain() }`;
```



## Enhanced Object Literals

**Shorthand property names**
```
var o = { a, b, c };
```

**Shorthand method name and dynamic property name**
```
var o2 = {
  myMethod,
  ['myPropertyNum'+b]: 'bar'
}
```

**scape this**

var messages = {
  get latest () {
    if (this.log.length == 0) return undefined;
    return this.log[this.log.length - 1]
  },
  set current (str) {
    this.log[this.log.length] = str;
  },
  log: []
}
­
messages.current = "hey!";
messages.latest // hey!






## getter

The get syntax binds an object property to a function that will be called when that property is looked up.

{get prop() { ... } }
{get [expression]() { ... } }

**Using a computed property name**

```
var expr = 'foo';
var obj = {
  get [expr]() { return 'bar'; }
};
console.log(obj.foo); // "bar"
```

## setter



## Array

1º A symple way to ad value to varaible names:

As you can see in this example you pair naim-value quickly:

```
var [first, second, third, , fifth = 5] = [1, 2];

first // 1
second // 2
third // undefined
fifth // 5

```

Also is a good way to interchange the value of thow variable.

```
[second, first] = [first, second] // swap values
first // 2
second // 1
```


## Exercises

[Source](http://tddbin.com/#?)

```
let [firstValue] = [1];
```

firstValue ==> 1

```
const [firstValue, secondValue] = [1, 2];
```

firstValue ==> 1

```
const all = ['ax', 'why', 'zet'];
const [ , , z] = all;
```

z ==> zet

```
let [x, y] = ['ax', 'why'];
[y, x] = [x, y];
```

[x, y] ==> ['why', 'ax']

```
const user = [['Some', 'One'], 23];
const [[firstName, surname], age] = user;
```

user ==> 'Some One = 23 years'

```
let [a, b] = [c, d] = [1, 2];
```

==> [a, b, c, d] = [1, 2, 1, 2]

```
for (var [ , a, b] of [[0, 1, 2]]) {}
```

==> [a, b] = [1, 2]


## String

**Destructure every character**
```
let [a, b, c] = 'abc';
```

[a, b, c] ==> ['a', 'b', 'c']


**Missing characters are undefined**
```
const [a, , c] = 'ab';
```

c ==> void 0


**Unicode character work too**
```
const [space, , coffee] = 'a ☕';
```

coffee ==> '\u{2615}'


## Objects

```
var {foo, bar} = {foo: 'lorem', bar: 'ipsum'};
```

foo ==> lorem
bar ==> ipsum


var customer = {
  name: 'John',
  surname: 'Doe',
  dateOfBirth: {
    year: 1988
  }
};
­
var {name, surname, dateOfBirth: {year}, children} = customer;
name // 'John'
surname // 'Doe'
year // 1988
children // undefined



var foo = { bar: 'pony', baz: 3 }
var {bar, baz} = foo
console.log(bar)
// <- 'pony'
console.log(baz)
// <- 3


var {user: x} = {user: 5};
console.log(x);

// => 5

Fail-safe
var {user: x} = {user2: 5};
console.log(x)

==> undefined

**More values**
```
var {prop: x, prop2: y} = {prop: 5, prop2: 10};
console.log(x, y);
```
==> 5 10


**Short-hand syntax**
```var { prop, prop2} = {prop: 5, prop2: 10};
console.log(prop, prop2);
```
==> 5 10

**Equal to**
```
var { prop: prop, prop2: prop2} = {prop: 5, prop2: 10};
console.log(prop, prop2);
```
==> 5 10

## Potential grammar hiccups

**Oops: This doesn't work:**
```
var a, b;
{ a, b } = {a: 1, b: 2};
```

**But this does work**
var a, b;
```
({ a, b } = {a: 1, b: 2});
console.log(a, b);
```
==> 1 2




