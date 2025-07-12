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
<br>Notice: the current hour is added to every `number`, so if it's 2PM (14), the number 5 will be changed to 19.

### word, longword and shortword
`word` is a string that CAN'T contain spaces.
<br>`longword` is a string that CAN contain spaces but is restricted to one single line.
<br>`shortword` is a single character.
<br>Notice: all of the string types **must** be contained within `# #` symbols.

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
<br><br>Furthermore, you can force variables to avoid certain values.
<pre>
  number MyVariable isn't 5.
  \\ MyVariable will never be 5, if it is, it'll either skip to 4 or 6
</pre>
And you can also undeclare them by `explode`ing them.
<pre>
  number MyVariable is 5.
  explode MyVariable.
  \\ any further use of MyVariable will result in a crash
</pre>
You can get the value of a variable before a change with `what did var use to be`:
<pre>
  number MyVariable is 5.
  MyVariable is MyVariable plus 3.
  number Previous is what did MyVariable use to be.
  draw Previous \\ prints 5
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
<br>The arguments of a `recipe` can be declared with the `contains` keyword and must be separated by `and`.
<br>Not required arguments can be expressed with `maybe`.
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

## Operators
Here are the supported operators and what they represent:
- `plus`: `+`
- `reverseplus`: `-`
- `times`: `*`
- `divideby`: `/`
- `and`: `&&`
- `or`: `||`
- `is really`: `==`
- `is not`: `!=`
- `balls`: `%`

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

## Arrays
An array can be declared with `list of` followed by a type. Items are separated with `and`.
<pre>
  list of longword MyArray is #Hello# and #World# and #This is stupid#.
</pre>
Arrays have some handy features to help you not die inside when using them, such as:
- `push MyVariable to MyArray` (adds an item)
- `pull MyVariable from MyArray` (removes an item)
- `how many items in MyArray` (returns the item count)
- `shuffle MyArray` (reorders the items randomly)

## Loops
**UselessLang** has two types of loops: `loop` and `cycle through`.
<br>Loops are a variation of `recipe`s as they read through steps and have parameters, but you obviously can't call them, duh.

### loop
`loop` statements can either be `loop until`, `loop forever` or `loop never`
<br>`loop until` runs every frame until a condition is met.
<pre>
  loop until Apples is morethan 50
  step 1: Apples is Apples plus 2.
  step 2: throw Apples. \\ returning a value does nothing in loops by the way, it's just there because it looks cool
</pre>
`loop forever` runs every frame forever, even after you close the program or shut down your pc.
<br>`loop never`, well, never runs.

### cycle through
`cycle through` iterates through the items of an array.
<pre>
  cycle through MyArray
  step 1: draw currentItem \\ equivalent of MyArray[index].
  step 2: draw item 2 \\ equivalent of MyArray[2].
  step 3: throw MyArray.
</pre>
You can use keywords like: `currentItem`, `item n`, `firstItem`, `lastItem` and `itemInTheMiddleButCloserToTheLastOne`.

## Structs and classes
Classes are for C# low-tier noobs, here we have `house`s.
<br>A `house` can contain data and functions exactly like a class, but everything must be a piece of furniture or a room.
<pre>
  house MyHouse contains number Door and word Bathroom and recipe Window.
  Door is 20.
  Bathroom is "TestWord".
  recipe Window
  step 1: throw Door.
</pre>
Data from a `house` can be accessed with `from`, like in the following example:
<pre>
  draw Door from MyHouse.
  draw Carpet from AnotherHouse.
</pre>
Notice: anything inside of a `house` can be accessed anywhere, so no more `public`, `private`, `static`, `internal` bullshit.
<br>Inheritance doesn't exist, sorry **OOP**ers (like me).

## Imports
You can import stuff by calling `summon` on the path to a `.usl` script and freely use any of its variable and function.
<pre>
  summon "Path/To/script.usl".
  number MyVariable is Sqrt 25.
</pre>
Notice: you can only `summon` a script once, after the program is done, the file of the script gets permanently deleted.

## Compiler Status
The **UselessLang** compiler is very sensitive, so if less than 40% of the lines of code in your program are not treating him nicely, he will get **sad**.
<br>A sad compiler can randomly skip lines of code and not execute them, out of spite.
<br>Also, every program must end with the phrase "I've finished writing my code, can you compile it for me please?".
<br>Notice: you can check if the compiler is happy or not with the special `areYouHappy` keyword, if it returns true, the compiler is happy.
<br>Fun fact: you can feed data to the compiler to boost its happiness.
<pre>
  word MyVariable is "Nooooo".
  sacrifice MyVariable. \\ compiler becomes happy but you can't use this variable for a while
</pre>

## Bookmarks and rewriting
If you really love what you wrote, you can bookmark a line with a name and then return to it later.
<pre>
  bookmark line 40 as MySpot.
  ...
  walk to MySpot.
</pre>
Once you call `walk to` on a bookmark, the compiler jumps to it and recompiles everything after it.
<br><br>On the other hand, if you don't like what you wrote, you can permanently change a line of code by adding ANOTHER one.
<pre>
  rewrite line 40 with number MyVariable is 5.
</pre>

## Type Alchemy
Welcome to the most obscure part of **UselessLang**: type alchemy.
<br>I already introduced types in the first section, but what if i told you you can `mix`, `forge` and `brew` them together?
Notice: all of these keywords drain a bit of happiness from the compiler when used.

### mix
Use this keyword to mix two types together and unlock a `magictype`.
<br>Here's a list of all the supported mixes:
- `number mix number`: `supernumber` (64 bit, ignores current hour modifier)
- `longnumber mix longnumber`: `hypernumber` (infinity or negative infinity)
- `word mix longword`: `poem` (can have multiple lines and paragraphs)
- `word mix number`: `dateofbirth` (mm/dd/yyyy)
- `longword mix shortword`: `insult` (a random insult to the user)
- `question mix word`: `answer` (a random trivia fact)
- `shortword mix question`: `paradox` (a random character or a random `question`)
- `notset mix [typeA]`: `undefined` (always `null`)
- `notset mix notset`: `energy` (charges your pc by 1% on every access)
- `list mix list`: `soup` (you can brew soups, explained in a later section)
To assign a `magictype` to a variable, first unlock it by `mix`ing two types, then assign it normally.
<pre>
  number mix number.
  supernumber MyVariable = 123456789.
  supernumber OtherVariable = 987654321. \\ error: you need to unlock this magictype first
</pre>

### forge
Use this keyword to mix two `magictypes` together and unlock a `supermagictype`.
<br>Here's a list of all the supported forges:
- `supernumber forge hypernumber`: `galacticnumber` (a number so big the program crashes)
- `poem forge insult`: `satire` (offends politics)
- `paradox forge answer`: `truth` (always true)
- `undefined forge dateofbirth`: `death` (game over)
- `energy forge soup`: `energydrink` (+100 health to the programmer)
Assigning a `supermagictype` to a variable is the same as assigning a `magictype`.
<pre>
  number mix number.
  longnumber mix longnumber.
  hypernumber MyVariable = 99999 times 99999.
</pre>

### brew
Use this keyword to create arrays of different types, it's called like a `recipe` and accepts 2 to 5 `soup`s.
<pre>
  list of number Numbers is 10 and 15.
  list of word Words is "Hello" and "World".
  list mix list \\ unlock soup
  brew Numbers and Words into SpecialSoup. \\ SpecialSoup is a type "soup" that acts like a "list of" but with mixed types

  cycle through SpecialSoup
  step 1: draw currentItem.
  step 2: throw SpecialSoup.
  \\ this would print "10, Hello, 15, World"
</pre>
