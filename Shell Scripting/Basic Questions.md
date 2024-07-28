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

## Factorial 

```
#!/bin/bash
# Script to calculate the factorial of a number

echo "Enter a number: "
read num

factorial=1

for (( i=1; i<=num; i++ ))
do
  factorial=$((factorial * i))
done

echo "The factorial of $num is: $factorial"


```

## Prime Number

```
#!/bin/bash
# Script to check if a number is prime

echo "Enter a number: "
read num

is_prime=1

if [ $num -lt 2 ]; then
  is_prime=0
else
  for (( i=2; i*i<=num; i++ ))
  do
    if [ $((num % i)) -eq 0 ]; then
      is_prime=0
      break
    fi
  done
fi

if [ $is_prime -eq 1 ]; then
  echo "$num is a prime number."
else
  echo "$num is not a prime number."
fi


```

## Fibonacci Series

```
#!/bin/bash
# Script to generate Fibonacci series up to n terms

echo "Enter the number of terms: "
read n

a=0
b=1

echo "Fibonacci series: "

for (( i=0; i<n; i++ ))
do
  echo -n "$a "
  fn=$((a + b))
  a=$b
  b=$fn
done

echo


```

## Sum of digits

```
#!/bin/bash
# Script to calculate the sum of digits of a number

echo "Enter a number: "
read num

sum=0
temp=$num

while [ $temp -ne 0 ]
do
  digit=$((temp % 10))
  sum=$((sum + digit))
  temp=$((temp / 10))
done

echo "The sum of the digits of $num is: $sum"


```

## Armstrong Number

```
#!/bin/bash
# Script to check if a number is an Armstrong number

echo "Enter a number: "
read num

sum=0
temp=$num
num_digits=${#num}

while [ $temp -ne 0 ]
do
  digit=$((temp % 10))
  sum=$((sum + digit**num_digits))
  temp=$((temp / 10))
done

if [ $sum -eq $num ]; then
  echo "$num is an Armstrong number."
else
  echo "$num is not an Armstrong number."
fi


```

## Greatest Common Divisor

```
#!/bin/bash
# Script to find the GCD of two numbers

echo "Enter first number: "
read a
echo "Enter second number: "
read b

while [ $b -ne 0 ]
do
  temp=$b
  b=$((a % b))
  a=$temp
done

echo "The GCD is: $a"


```

## Least Common Multiple

```
#!/bin/bash
# Script to find the LCM of two numbers

echo "Enter first number: "
read a
echo "Enter second number: "
read b

gcd() {
  local x=$1
  local y=$2
  while [ $y -ne 0 ]; do
    temp=$y
    y=$((x % y))
    x=$temp
  done
  echo $x
}

g=$(gcd $a $b)
lcm=$((a * b / g))

echo "The LCM is: $lcm"


```

## Reverse a string

```
#!/bin/bash
# Script to reverse a string

echo "Enter a string: "
read str

reverse=$(echo $str | rev)

echo "The reverse of the string is: $reverse"


```

## Check if a number is even or odd

```
#!/bin/bash
# Script to check if a number is even or odd

echo "Enter a number: "
read num

if [ $((num % 2)) -eq 0 ]; then
  echo "$num is an even number."
else
  echo "$num is an odd number."
fi


```