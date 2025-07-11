# UselessLang
Probably the most unappetizing programming language.
<br>Let's start this with a general overview of the *fantastic* features.

## Types
In UselessLang there are a few types that can be typed to uhhh code, i guess.
<br>These include:
- `number`: `int32`
- `longnumber`: `float`
- `word`: `string` (without spaces)
- `longword`: `string` (with spaces)
- `shortword`: `char`
- `question`: `bool`
- `notset`: `null`

### number and longnumber
`number` is just a normal 32 bit integer.
<br>`longnumber` is just a normal float.

### word, longword and shortword
`word` is a string that CAN'T contain spaces.
<br>`longword` is a string that CAN contain spaces.
<br>`shortword` is a single character.

### question
`question` is a boolean, that means it can be either `true` or `false`.
<br>If you're unsure of the answer to a `question`, you can set it to `idk`, which randomly returns `true` or `false` every time it's accessed.
**WARNING**: `true` will be compiled to `false` and viceversa, because this is my language and i can do what i want :)

### notset
`notset` is a type that is always initialized to be `null`, but you can assign it another type later on, like in this example:
<pre>
  notset MyVariable.
  MyVariable is number.
  MyVariable is 5.
</pre>
<br>Be careful though, you can't set a value to a `notset` before assigning it a type.
<pre>
  notset MyVariable is 5.
  \\ error
</pre>

## Variables
Variables can be declared like this:
<pre>
  number MyVariable is 5.
</pre>
<br>A variable can contain multiple words as its name
<pre>
  number &lt;This is my variable&gt; is 5.
  &lt;This is my variable&gt; is 10.
</pre>
<br>Be careful, every line must end with a `.` symbol.
<br>Furthermore, you can force variables to avoid certain values:
<pre>
  number MyVariable isn't 5.
  \\ MyNumber will never be 5, if it is, it'll either skip to 4 or 6
</pre>
And you can
