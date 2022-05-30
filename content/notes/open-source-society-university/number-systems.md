---
title: "self test"
date: "2022-05-30 02:28"
author: "[Doriel Rivalet](https://github.com/DorielRivalet)"
tags:
- math
---


# Metadata
2022-05-27 04:42

Title: self test

Author: [Doriel Rivalet](https://github.com/DorielRivalet)

Tags: #math #programming #geometry #javascript #ruby #cpp #lua #python #object-oriented-programming

# Content

let see if i can give my own outline (or rather overview) of math in general in a day, also combine programming with it

lets start with nothing

how can we represent nothing?

well u could use the symbol 0, from the arabic numberals

or when talking about sets, u have the empty set {}

lemme grab a LaTeX cheatsheet since i never wrote in math notation in markdown before

$$0$$

$${}$$

```lua
nil
```

```javascript
null
```

now, how can we represent the opposite of nothing, i.e. something? 

the inverse

if we look at one of our hands, we should have 5 fingers. how do we know that we have 5? whats the action that we did to determine that value? counting.

```python

fingersOnHand = 5

def countFingersOnHand:
	return fingersOnHand

print(countFingersOnHand()) #returns 5
```

$$5 = 1+1+1+1+1$$

[i could show why 1+1=2 but showing hundreds of pages for it is not needed for the general overview i'm aiming for](https://en.wikipedia.org/wiki/Principia_Mathematica)

our hand is an object and we iterated through the elements of the object which in this case are our fingers. the act of counting is the iteration.

$$
\begin{bmatrix}
1 & 2 & 3 & 4 & 5\\
thumb & index & middle & ring & pinky
\end{bmatrix}
$$

whats the data type we are currently dealing with? integers

10 is the action of doing addition by 1 and iterating 10 times that same operation

we can do 1+10, 1+11, etc.

we have addition, whats the inverse of it? subtraction

if we do 1-2 then we get -1, a negative integer

but how is this represented in computers?

well, lets start over again

we have nothing, we can represent it by 0

and we have something, we can represent it by 1

lets call counting with only these two symbols binary counting

but why is it called binary? well, bi means two. -nary because of the numerical system

0, then 1, then 10

but why is it going from 1 to 10? because we can only use two symbols

suppose we use 3 symbols instead: 0, 1 and 2

u would count like this:

0, then 1, then 2, then 10, then 11, then 12, then 20, then 21, and so on

do u see the pattern?

but, we use binary for efficiency purposes. (by the way, using 10 symbols would be the decimal system, and 16 symbols the hexadecimal system, which goes from 0 to 1 to 2, ... to 9, then A  which is 10 in decimal, B which is 11 in decimal, ... and finally F which is 15 in decimal)

the number has to be stored somewhere in the computer.

it has to be stored in memory.

but what is *it*? information

how do we represent an unit of information?

[[notes/open-source-society-university/bytes]]

lets allocate 1 byte:

```
ourMemory = 00000000
```

so now we can currently go from 0 to 15, but what if we want to go from -7 to 7?

we can make the first digit represent the sign of our number

so for doing operations such as ```4-5```, we can use the int16 struct. but if we aren't dealing with negative integers, then we can use uint16.

so to recapitulate, our current set so far is this:

$${...,-1,0,1,...}$$

and our current operations are addition, represented by +, and subtraction, represented by -

counting is the action of doing the set above operations on our current set of numbers

$${+,-}$$

what if we want to represent multiple additions in a more succinct way?

```lua
print(1+1+1+1+1+1+1+1+1+1)
```

imagine i wanted to type the above code, but instead of printing 10 by doing 10 operations, i wanted to do it in 1 operation.

2022-05-28 17:47

lets define a function that does that

$$f(num) = num+num+num+num+num$$

```ruby

def multipleAddition(num)
  puts num.times { |i| print i, " "}
end

multipleAddition(5)
```

what is num? it stands for number. its a variable.  a variable may represent a [number](https://en.wikipedia.org/wiki/Number "Number"), a [vector](https://en.wikipedia.org/wiki/Vector_(mathematics) "Vector (mathematics)"), a [matrix](https://en.wikipedia.org/wiki/Matrix_(mathematics) "Matrix (mathematics)"), a [function](https://en.wikipedia.org/wiki/Function_(mathematics) "Function (mathematics)"), the [argument of a function](https://en.wikipedia.org/wiki/Argument_of_a_function "Argument of a function"), a [set](https://en.wikipedia.org/wiki/Set_(mathematics) "Set (mathematics)"), or an [element](https://en.wikipedia.org/wiki/Element_(mathematics) "Element (mathematics)") of a set. in this case its the argument of a function.

in programming, variables represent a value that is in memory

```text

ourMemory = 00000000
num = 5

ourMemory = num

print(ourMemory) //returns 00000101
```

lets create a new operation and represent it by the symbol * and call it multiplication

$$ variable1 * variable2 = (variable1 + variable1 + ...)  variable2 times$$

whats the inverse of multiplication? division

so now our current operators look like this:

$${-,+,*,/}$$

what happens if we do 1/2? we cant compute the result as an integer. what can we do? well, there's a solution: create a new data type

Floats!

Let's create the specifications of a float:

![[notes/images/Pasted image 20220528174638.png]]]

now that we have our new data type, we can expand our numbers set:

$${-1,-0.65345346,0,1,3.1415}$$

now then, what if we want to represent multiple multiplications in a more succinct way?

```lua
print(2*2*2*2*2*2)
```

imagine i wanted to type the above code, but instead of printing 64 by doing 5 operations, i wanted to do it in 1 operation.

let's define a function that does that:

$$g(num2) = f(num1) * f(num1) * ... num2 times$$

```cpp
#include <iostream>

int multipleMultiplication(int num,int exponent){
  int accumulator = 1;
	for (int i = 0;i <= exponent;i++){
		accumulator = accumulator * num;
	}
	return accumulator;
}

int main() {
  int result = multipleMultiplication(2,5);
  std::cout << result; //prints 64
}

```

 $$ f(num,exponent)=\prod_{i=0}^{exponent} num$$
 
 what happens if the exponent isn't an integer but instead a float?
 
 meaning, what if we do $$64^{0.5}$$?
 
 well, that is the same as the square root notation:
 
$$\sqrt[2]{64} = 8$$

whats the inverse of exponentiation? logarithms

what if we know the base number, and the number we want to reach, but we dont know the exponent we need? thats what logarithms can be useful for. example:

suppose we have the number 10, and we want to reach the number 1000, what exponent do we need? 3, because 10 times 10 times 10 is 1000.

$$\log_{10}{1000} = 3$$

 so now we can do quite a bunch of things, but there are two questions that still remain...
 
 1. what if we want to represent multiple exponentiations in a more succint way?
 2. what if the number is negative in the square root?
 
lets start with the first question: what if we want to represent multiple exponentiation in a more succinct way?

we can already represent quite big and small numbers with exponentiation, but there is also an alternative way to write really small or big numbers: scientific notation

$$m × 10^n$$

or m times ten raised to the power of n, where _n_ is an [integer](https://en.wikipedia.org/wiki/Integer "Integer"), and the [coefficient](https://en.wikipedia.org/wiki/Coefficient "Coefficient") m is a nonzero [real number](https://en.wikipedia.org/wiki/Real_number "Real number") (usually between 1 and 10 in absolute value, and nearly always written as a [terminating decimal](https://en.wikipedia.org/wiki/Decimal "Decimal")). The integer n is called the [exponent](https://en.wikipedia.org/wiki/Exponent "Exponent") and the real number m is called the [significand](https://en.wikipedia.org/wiki/Significand "Significand")or mantissa_.[[1]](https://en.wikipedia.org/wiki/Scientific_notation#cite_note-Calio2017-1) The term "mantissa" can be ambiguous where logarithms are involved, because it is also the traditional name of the [fractional part](https://en.wikipedia.org/wiki/Fractional_part "Fractional part") of the [common logarithm](https://en.wikipedia.org/wiki/Common_logarithm "Common logarithm"). If the number is negative then a minus sign precedes m, as in ordinary decimal notation. In [normalized notation](https://en.wikipedia.org/wiki/Scientific_notation#Normalized_notation), the exponent is chosen so that the [absolute value](https://en.wikipedia.org/wiki/Absolute_value "Absolute value") (modulus) of the significand m is at least 1 but less than 10.
 
 so for example, the number 1024, which in binary is ```10000000000```, which in hexadecimal is ```0x400```, which can be a uint16 or int16 datatype, which is $$2^{10}$$; can also be expressed as $$1.024*10^3$$.
 
 but some may ask: we have + for addition, \* for multiplication and ^ for exponentiation, aren't we missing a symbol (*i.e*, + and \* and ^) and the action it would represent (*i.e*, addition, multiplication and exponentiation) ?
 
 enter arrow notation:
 
$$2\uparrow4 = 2^4 = 16$$

one arrow is exponentiation (iterated multiplication), two arrows is tetration (iterated exponentiation)

$$2\uparrow\uparrow4 = 2^{2^{2^{2}}} = 2^{16} = 65536 = 0x10000 = 0b10000000000000000$$

tetration: (tetra comes from four, the same way penta comes from five). now we found a pattern: hexa means six, that means hexation would be whats after pentation, and so on. but lets just stick with explaining tetration for now.

```javascript

function multipleExponentiation(num, arrows, num2){
  let accumulator = num;
	for (let i = 0;i <= arrows;i++){
		for (let j = 0;j <= num2;j++){
			accumulator *=  num;
		}
	}
	return accumulator;
}

console.log(multipleExponentiation(2,2,4))

```
 
let's answer the second question: what if the number is negative in the square root?

$$\sqrt[2]{-2}$$

we can't multiply something times itself and get a negative number, see:

2 times 2, 4. -2 times -2, 4.

but why is -2 times -2 equal to 4?

lets review our current set of numbers:

$${-1,-0.65345346,0,1,3.1415}$$

if we multiply positive with positive, we go to the right of the number line

if we multiply positive with negative, we go to the left of number line, because the negative changes direction.

if we multiply negative with negative, you change direction twice, so you end up going as the same direction of multiplying two positive numbers.

or explained in another way, multiplying by negative is a 180 degrees rotation, which is also 1pi radian

if u do 180 twice u do a full rotation, and thus, go in the same direction. a 360degrees rotation, or 2pi radian

![[notes/images/Pasted image 20220528204454.png]]

so far our numbers can be drawn on a line that goes from right to left, or left to right, meaning that we are dealing with one dimensional numbers, and the rotations we do can only be by 180. what happens if we create a line thats orthogonal to our current line? meaning, a vertical line. we want a number system that goes right to left, left to right, but also... up or down!

$$ourNumberSystem = \{right-left,up-down\}$$

lets call the right-left part the x part, the real numbers. 

and the up-down part, the y part.

now we are dealing with two dimensional numbers!

what happens if instead of wanting to do 180 rotations by changing the signs of a number, we want to do rotations of any degree, by changing the signs but also, the y part?

we are getting close, lets review our current problem:

$$\sqrt[2]{-1} = 1*x$$

that x has to be something in the up-down direction...

we need to do a 90 degree rotation.

$$ourNeededNumber = \{1,up-down\}$$

let's define the unit in the up-down direction as i. and lets call it imaginary number.

$$\sqrt[2]{-1} = 1i$$

and thus we created the complex plane

![[notes/images/Pasted image 20220528211430.png]]


$$i^2 = -1$$

so, real numbers are one-dimensional, and the complex numbers are two-dimensional... what are three dimensional numbers? 

In our C++ and JavaScript programs, we see that loops iterator variables go from i,j,k, and so on

so we need a j unit? well...

we actually need 4 dimensional numbers.

notice how in positions of for example video-game objects, those are defined as 
```text
sword = new Sword("Excalibur");
sword.position = new Vector3(x,y,z);
```

where position is our variable (which is a property of an instance of the Sword class, which we are accessing with the dot operator), assigned the value (```=```) of an instance(```new```) of a vector3 class(```Vector3```) with arguments x y z (*e.g*, ```10.4,50.3,40.5```)

so, imagine x as i, y as j and z as... k!

4 dimensional numbers would be something called [quaternions](https://youtu.be/3BR8tK-LuB0?t=287) (quadra meaning four, the same way tetra means four, but from a different language origin, find out which one is greek and which one is latin!), and it introduces 2 more types of numbers: j and k. 

(notice how at the [6:20 mark](https://youtu.be/3BR8tK-LuB0?t=380) is related to the concept of [diffuse mode](https://www.theodinproject.com/lessons/foundations-motivation-and-mindset#the-learning-process))

but what if we want to [go even further beyond](https://www.youtube.com/watch?v=8TGalu36BHA) quaternions, the same way we went from exponentiation to then tetra/penta/hexa-tion with an arbitrary number of arrows?

fortunately, we can use something called the Cayley-Dickson construction

now, dont be intimated by what that exactly means, just know that for now it allows us to create 2^N dimensional algebras. meaning that we can go from two-dimensional to 4-dimensional to 8-dimensional and so on.

octonions (octo meaning eight) come after quaternions, and so on.

the further u go on these algebraic structures, the more odd things can get, see:

Passing from the reals to the complex numbers, we lose order; going from the complexes to the quaternions, we lose commutativity of multiplication. If we keep going, we lose associativity of multiplication, in increasing degrees: the sedenions are even less associative than the octonions, etc.

interesting, isn't it?

# Sources

own notes

https://www.geeksforgeeks.org/ruby-integer-times-function-with-example/

https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/

https://en.wikipedia.org/wiki/Variable_(mathematics)

https://en.wikipedia.org/wiki/Single-precision_floating-point_format

https://es.overleaf.com/learn/latex/Subscripts_and_superscripts

https://en.wikipedia.org/wiki/Logarithm

https://en.wikipedia.org/wiki/Tetration

https://math.stackexchange.com/questions/1784166/why-are-there-no-triernions-3-dimensional-analogue-of-complex-numbers-quate