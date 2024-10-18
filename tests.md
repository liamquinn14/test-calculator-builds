# Test Calculator

## To test with every build
- Max length to input box?
- Can you enter letters/special chars?
- Large numbers
- Negative numbers
- Spaces in input box
- Empty strings
- Decimals
- Numbers with commas
- Minus number minus minus number
- Using zero

## Test Case 1: Max length to input box

Expected outcome: limited length to input box

All 8 builds capped at 10. 

Should now test a 10 digit by 10 digit

## Test Case 2: Entering letter, emoji and special characters

Expected outcome: doesn't allow letters, emojis or special chars

All 8 builds allow letters, emojis and special chars to be inputted

## Test Case 3: Large numbers - 32769 squared

Expected outcome: 1073807361

All builds apart from build 7 return the correct 1073807361. Build 7 returns 0.



## Test Case 4: Large numbers - 1 000 000 squared

Expected outcome: 1000000000000

All builds apart from build 7 return the correct 1000000000000. Build 7 returns 0.

## Test Case 5: Negative numbers

-5 x -3

Expected outcome: 15

All builds apart from build 7 return the correct 15. Build 7 returns 0.

## Test Case 6: Space within number input

1 000 x 1 000

Expected outcome: doesn't allow spaces, or 1000000

Build 1 outcome: Tries to calculate, returns NaN
Builds 2,3,4,5,6,8 outcome: Doesn't calculate. Error 'Number 1 is not a number'
Build 7 outcome: Doesn't calculate. Error 'Number 2 is not a number'

Same error as other string input errors.

## Test Case 7: Empty number input

"" x 5 

Expected outcome: doesn't attempt to calculate with empty input

All 8 builds attempt to calculate. Then return 0.

## Test Case 8: Decimals - multiplication

1.5 x 0.8

Expected outcome: 1.2

Build 1 outcome: 1.2000000000000002
Build 2 outcome: 1.2000000000000002
Build 3 outcome: 1.2000000000000002
Build 4 outcome: 1, integers only
Build 5 outcome: 1.2000000000000002
Build 6 outcome: 1.2000000000000002
Build 7 outcome: 0
Build 8 outcome: 1.2000000000000002

All wrong.

## Test Case 9: Decimals - recurring from division

10 / 3

Expected outcome: 3.33333333...

Build 1 outcome: 3.3333333333333335
Build 2 outcome: 3.3333333333333335
Build 3 outcome: 3.3333333333333335
Build 4 outcome: 3
Build 5 outcome: 3.3333333333333335
Build 6 outcome: 3.3333333333333335
Build 7 outcome: 0
Build 8 outcome: 0.3

## Test Case 10: Commas in number

1,000 x 1,000
Expected outcome: Doesn't allow commas, or 1,000,000
Build 1 outcome: NaN
Build 2,3,4,5,6,8: Number 1 is not a number
Build 7 outcome: Number 2 is not a number

Surprised Build 2 didn't concatenate 1,000 and 1,000 to '1,0001,000'

## Test Case 11: Minus number minus minus number

- 5 - -12

Expected outcome: 7

Build 1-6 outcome: 7
Build 7 outcome: 12
Build 8 outcome: -7

## Test Case 13: Using zero - multiplication

12 * 0

Expected outcome: 0

All 8 builds return the expected 0.

## Test Case 14: Using zero - division

40 / 0

Expected outcome: cannot divide by zero error, or doesn't allow to calculate

Builds 1,2,3,4,5,7 outcome: Zero division error. Calculating spinner infinitely spins. Cannot press clear. Cannot attempt another calculation.
Build 6 outcome: 'Infinity'
Build 8 outcome: 0


## Test Case 15: Rounding < .5

1.2 * 2 = 2.4

Expected outcome: 2

Builds 1,2,3,4,5,6,8 outcome: 2
Build 7 outcome: 4

## Test Case 16: Rounding > .5

1.2 * 4 = 4.8

Expected outcome: 5

Builds 1,2,3,4,5,6,8 outcome: 4
Build 7 outcome: 19

All incorrect. It floors answer rather than rounding upwards.

# Test Case 17: Inputting letters and special characters

Nine add six

Expected outcome: fifteen

Build 1 outcome: Tries to calculate, returns NaN
Build 2 outcome: Returns 'ninesix'
Builds 3,4,5,6,8 outcome: Doesn't calculate. Error 'Number 1 is not a number'
Build 7 outcome: Doesn't calculate. Error 'Number 2 is not a number'

Bizarre range of outcomes. None of them notice that both inputs aren't numbers.
Test with special characters shows the same pattern. NaN in build 1, a concatenation in Build 2, and the same exact error messages as in the above example. 

Same results as before with emojis

# Test Case 18: Build 2 with non-numbers, other operators

Expected outcome: ! x !! = !!, or !!! / ! = !!! or !!! - ! = !!

Build 2 has a 'Number 1 is not a number' error when you try to use other operators on strings. Only concatenation works

# Test Case 19: Build 7 multiplication

Build 7 cannot even multiply 4 by 1. It cannot multiply at all.

# Test Case 20: Build 7 addition

Build 7 always returns the answer box + second number. This is applied to every operator. Meaning it often starts with second number and 0.





