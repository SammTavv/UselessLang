# UselessLang
Probably the most unappetizing programming language.
<br>Let's start this with a general overview of the *fantastic* features.

## Types
In **UselessLang** there are a few types that can be typed to uhhh code, i guess.
<br>These include:
- `number`
- `longnumber`
- `word`
- `longword`
- `shortword`
- `question`
- `notset`

### number and longnumber
`number` is just a normal 32 bit integer.
<br>`longnumber` is just a normal float.

### word, longword and shortword
`word` is a string that CAN'T contain spaces.
<br>`longword` is a string that CAN contain spaces.
<br>`shortword` is a single character.
<br>Notice: all of these types **must** be contained within `# #` symbols.

### question
`question` is a boolean, that means it can be either `true` or `false`.
<br>If you're unsure of the answer to a `question`, you can set it to `idk`, which randomly returns `true` or `false` every time it's accessed.
<br>Notice: `true` will be compiled to `false` and viceversa, because this is my language and i can do what i want :)

### notset
`notset` is a type that is always initialized to be `null`, but you can assign it another type later on, like in this example:
<pre>
  notset MyVariable.
  MyVariable is number.
  MyVariable is 5.
</pre>
Be careful though, you can't set a value to a `notset` before assigning it a type.
<pre>
  notset MyVariable is 5.
  \\ error
</pre>

## Variables
Variables can be declared like this:
<pre>
  number MyVariable is 5.
</pre>
A variable can contain multiple words as its name
<pre>
  number &lt;This is my variable&gt; is 5.
  &lt;This is my variable&gt; is 10.
</pre>
Be careful, every line must end with a `.` symbol.
<br><br>Furthermore, you can force variables to avoid certain values:
<pre>
  number MyVariable isn't 5.
  \\ MyVariable will never be 5, if it is, it'll either skip to 4 or 6
</pre>
And you can also undeclare them by `explode`ing them:
<pre>
  number MyVariable is 5.
  explode MyVariable.
  \\ any further use of MyVariable will result in a crash
</pre>

## Comments
As you may have seen, comments are prefixed by `\\`.
<br>Multiline comments are awful and messy, so **UselessLang** doesn't support them.

## Functions
Functions can be created with the `recipe` keyword. The body of a `recipe` is defined by its steps, check out this example:
<pre>
  recipe MyFunction
  step 1: number MyVariable is 5.
  step 2: throw MyVariable.
</pre>
Functions **must** `throw` (return) a type, even if it's not used or doesn't serve any purpose.
<br>The arguments of a `recipe` can be declared with the `contains` keyword and must be separated by `and`. Not required arguments can be expressed with `maybe`.
<pre>
  recipe Sum contains number num1 and number num2 and maybe number num3
  step 1: number result is num1 plus num2 plus num3.
  step 2: throw result.
</pre>
A function can be called by simply typing its name, followed by its arguments.
<pre>
  number result is Sum 5 and 4 and 7.
  draw result. \\ this prints 16
</pre>

## Conditional statements
Conditional statements such as `if`, `else`, `else if`, `if else` and `elf` execute any precedent line of code that has a `-` symbol before it.
<pre>
  -draw #Hello#.
  if (MyVariable is lessthan 10)
</pre>
You can also chain conditional statements like so:
<pre>
  -draw #Hello#.
  -SomeFunction.
  if (Time is 50)
  -draw #I hate you#.
  -SomeFunction
  else
</pre>
