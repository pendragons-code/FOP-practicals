## practical 6 ADDITIONAL NOTES TO TEACHER
In this table, you see that the 3rd row, 1st column is blank, this means that it is the same as the one above.
| First Condition | Second Condition | Output |
|---|---|---|
| d is true | f > e | zebra |
| <br> | !(f > e) | Kangaroo |
| d is false | e > f | Tiger<br>Liger |
| <br> | !(e > f) | Giraffe<br>Liger |

## Question 1a:
```
let d = true, e = 0, f = 2;
d = false;
if (d) {
	if (f > e) {
		console.log("Zebra");
	} else {
		console.log("Kangaroo");
	}
} else {
	if (e > f) {
		console.log("Tiger");
	} else {
		console.log("Giraffe");
		console.log("Liger");
	}
}
```
answer: 
```
Giraffe
Liger
```
notes: In the practical document, it would seem that this actually had a missing closing } bracket, which would result in a syntax error, I am not sure if this is the expected answer.

## Question 1b
| First Condition | Second Condition | Output |
|---|---|---|
| d is true | f > e | zebra |
| <br> | !(f > e) | Kangaroo |
| d is false | e > f | Tiger<br>Liger |
| <br> | !(e > f) | Giraffe<br>Liger |

## Question 1c
i) What is the output if the user enters size 0 and order quantity 5500?
```
It gives an output of "Sorry invalid size."
```
ii) What is the output if the user enters size 17 and order quantity 1500?
```
It gives an output of "You are given 30% discount"
```
iii) What is the output if the user enters size 27 and order quantity 6500
```
It gives an output of "You are given 50% discount"
```
## Question 1c
| Size | Order Quantity | Discount |
|---|---|---|
| Less than or equal to 0 | Any Number | 0 |
| Less than or equal to 25 | 1000 to 2000 | 30 |
| <br> | more than 2000 | 40 |
| <br> | less than 1000 | 20 |
| More than 25 | more than 5000 | 50 |
| <br> | order less than 3000 | 15 |
| <br> | 3000 to 5000 | 40 |

## Question 2
a) `Value of w is 3`<br>
b) `Value of x is 5`<br>
c) `Value of z is 33`

## Question 3
```
// part a
const { question } = require("readline-sync");
let firstNumberFromUserInput = parseInt(question("Please enter 1st number: ")), secondNumberFromUserInput = parseInt(question("Please enter 2nd number: ")); // questionInt has validation of numerical values, but apparently they want it done differently
if(isNaN(firstNumberFromUserInput) || isNaN(secondNumberFromUserInput)) return console.log("Sorry wrong input. Please try again. Good bye!");
if(firstNumberFromUserInput > secondNumberFromUserInput) return console.log("1st number is bigger");
else if(secondNumberFromUserInput > firstNumberFromUserInput) return console.log("2nd number is bigger");
else return console.log("Both are equal!");
```
<br>part b:<br><br>
Notes: If there are 2 base values x and y that would mean 2 variables, if there is a 3rd one to determine the if the number is non numeric or numeric and 4th one to determine if the values are bigger or smaller, it would mean 2^4 possibilities, in turn 16 rows. However, we also know that some of the 16 would result in duplicate behaviour, for example test case: `if input first number is bigger than input second number and if 2nd number is non numeric number`. This test case would trigger the behaviour for 2nd number non-numeric. Knowing this, I'll ignore if the test cases are duplicate or will trigger another behaviour. That said, I know there are likely more than these test cases right here.

| Test Cases | Input 1st number | Input 2nd number | What to test? | Expected Results |
|---|---|---|---|---|
| 1 | x | 30 | Non numeric 1st number | Error Message, program exit |
| 2 | 30 | x | Non numeric 2nd number | Error Message, program exit |
| 3 and 4 | x | y | Non numeric 1st and 2nd number | Error Message, program exit |
| 5 | 30 | 31 | 1st number is smaller than the second | Output: `1st number is bigger`<br>This behaviour is also true for decimals and negative numbers. |
| 6 | 31 | 30 | 2nd number is smaller than the first | Output: `2nd number is bigger`<br>This behaviour is also true for decimals and negative numbers. |
| 7 | 30 | 30 | both numbers are equal | Output: `Both numbers are equal!`<br>This behaviour is also true for decimals and negative numbers. |
| "1" | 2 | 30 | Non numeric 1st number | Error Message, program exit |
| 2 | 2 | "1" | Non numeric 2nd number | Error Message, program exit |
| 3 and 4 | "1" | "1" | Non numeric 1st and 2nd number | Error Message, program exit |

## Question 4
part a<br>
```// wait like wth write a function called grade()?
const { questionFloat } = require("readline-sync");
function grade() {
	let score = questionFloat("Please enter score: ");
	if(score < 0 || score > 100) return console.log("Error: Bro broke the grading scale 💀! (Valid numbers between 0 to 100 pls)");
	let evaluatedScore = score < 50 && "E" || score <= 60 && "D" || score <= 70 && "C" || score <= 80 && "B" || "A"; // I was legit too lazy to write so many if else
	return console.log(`Your grade is ${evaluatedScore}`);
}
grade(); // I dun really understand what they want LMAO
```

<br><br>part b<br>
| Test Case | Expected Output |
|-------------|----------------------|
| score = 45 | Your grade is E |
| score = 55 | Your grade is D |
| score = 65 | Your grade is C |
| score = 75 | Your grade is B |
| score = 85 | Your grade is A |
| score =  | Your grade is A |
| score = 0 | Your grade is E |
| score = 50 | Your grade is D |
| score = 60 | Your grade is D |
| score = 70 | Your grade is C |
| score = 80 | Your grade is B |
| score = - | Error |
| score =  | Error |


## Question 5
part a<br>
<br><br>part b<br>