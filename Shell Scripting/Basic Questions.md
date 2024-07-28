## Addition

```
#!/bin/bash 
#Script to add two numbers 

echo "Enter first number: " 
read num1 

echo "Enter second number: " 
read num2 

sum=$((num1 + num2)) 
echo "The sum of $num1 and $num2 is: $sum"

```

## Subtraction

```
#!/bin/bash 
# Script to subtract two numbers 

echo "Enter first number: " 
read num1 

echo "Enter second number: " 
read num2 

difference=$((num1 - num2)) 
echo "The difference between $num1 and $num2 is: $difference"

```

## Multiplication

```
#!/bin/bash
# Script to multiply two numbers

echo "Enter first number: "
read num1

echo "Enter second number: "
read num2

product=$((num1 * num2))
echo "The product of $num1 and $num2 is: $product"


```

##  Division

```
#!/bin/bash
# Script to divide two numbers

echo "Enter first number: "
read num1

echo "Enter second number: "
read num2

if [ $num2 -ne 0 ]; then
  quotient=$((num1 / num2))
  echo "The quotient of $num1 divided by $num2 is: $quotient"
else
  echo "Division by zero is not allowed."
fi


```

## Modulus

```
#!/bin/bash
# Script to find the modulus of two numbers

echo "Enter first number: "
read num1

echo "Enter second number: "
read num2

remainder=$((num1 % num2))
echo "The remainder when $num1 is divided by $num2 is: $remainder"


```

## Power

```
#!/bin/bash
# Script to calculate the power of a number

echo "Enter base number: "
read base

echo "Enter exponent number: "
read exponent

power=$((base ** exponent))
echo "$base raised to the power of $exponent is: $power"


```

## Simple Interest

```
#!/bin/bash
# Script to calculate Simple Interest

echo "Enter Principal: "
read principal

echo "Enter Rate of Interest: "
read rate

echo "Enter Time (in years): "
read time

simple_interest=$(echo "scale=2; $principal * $rate * $time / 100" | bc)
echo "The Simple Interest is: $simple_interest"


```

## Compound Interest

```
#!/bin/bash
# Script to calculate Compound Interest

echo "Enter Principal: "
read principal

echo "Enter Rate of Interest: "
read rate

echo "Enter Time (in years): "
read time

echo "Enter Number of Times Interest is Compounded per Year: "
read n

compound_interest=$(echo "scale=2; $principal * (1 + $rate / (100 * $n))^($n * $time)" | bc -l)

echo "The Compound Interest is: $compound_interest"


```

## Palindrome Number

```
#!/bin/bash
# Script to check if a number is a palindrome

echo "Enter a number: "
read num

temp=$num
reverse=0

while [ $temp -ne 0 ]
do
  remainder=$((temp % 10))
  reverse=$((reverse * 10 + remainder))
  temp=$((temp / 10))
done

if [ $num -eq $reverse ]; then
  echo "$num is a palindrome."
else
  echo "$num is not a palindrome."
fi


```

## Palindrome String

```
#!/bin/bash
# Script to check if a string is a palindrome

echo "Enter a string: "
read str

reverse=$(echo $str | rev)

if [ "$str" == "$reverse" ]; then
  echo "$str is a palindrome."
else
  echo "$str is not a palindrome."
fi


```

## Trigonometric Values

```
#!/bin/bash
# Script to calculate sine, cosine, and tangent of an angle

echo "Enter an angle in degrees: "
read angle

# Convert angle to radians
radians=$(echo "$angle * 3.14159 / 180" | bc -l)

sin_val=$(echo "s($radians)" | bc -l)
cos_val=$(echo "c($radians)" | bc -l)
tan_val=$(echo "s($radians) / c($radians)" | bc -l)

echo "Sine($angle) = $sin_val"
echo "Cosine($angle) = $cos_val"
echo "Tangent($angle) = $tan_val"


```

## Pythagoras Theorem

```
#!/bin/bash
# Script to calculate the hypotenuse using Pythagorean theorem

echo "Enter length of side a: "
read a

echo "Enter length of side b: "
read b

a_squared=$(echo "$a * $a" | bc)
b_squared=$(echo "$b * $b" | bc)

hypotenuse=$(echo "scale=2; sqrt($a_squared + $b_squared)" | bc -l)
echo "The length of the hypotenuse is: $hypotenuse"


```