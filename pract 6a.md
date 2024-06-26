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
| 3 | x | y | Non numeric 1st and 2nd number | Error Message, program exit |
| 4 | 30 | 31 | 1st number is smaller than the second | Output: `1st number is bigger`<br>This behaviour is also true for decimals and negative numbers. |
| 5 | 31 | 30 | 2nd number is smaller than the first | Output: `2nd number is bigger`<br>This behaviour is also true for decimals and negative numbers. |
| 6 | 30 | 30 | both numbers are equal | Output: `Both numbers are equal!`<br>This behaviour is also true for decimals and negative numbers. |
| 7 | "1" | 30 | Non numeric 1st number | Error Message, program exit |
| 8 | 2 | "1" | Non numeric 2nd number | Error Message, program exit |
| 9 | "1" | "1" | Non numeric 1st and 2nd number | Error Message, program exit |

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
part a
```
const input = require("readline-sync");
function checkIncrement(serviceYrs, salary) {
	// not checking if the numbers are float of integers since the question never said anything about it
	if(serviceYrs <= 0 || salary <= 0 || isNaN(serviceYrs) || isNaN(salary) || serviceYrs >= 10 && salary < 1000) return console.log("Sorry invalid input(s). Please try again. Good bye! ");
	if(salary < 1000) return console.log("Congratulation, your increment is : $100");
	if(salary < 2000) return console.log("Congratulation, your increment is : $200");
	return console.log("Congratulation, your increment is : $300");
}

let yrsOfService = parseFloat(input.question("Please enter you year(s) of service: "));
let salaryAmt = parseFloat(input.question("Please enter your salary: "));
checkIncrement(yrsOfService, salaryAmt);
```
<br><br>part b
```
const input = require("readline-sync");
function checkIncrement(serviceYrs, salary) {
	// not checking if the numbers are float of integers since the question never said anything about it
	if(serviceYrs <= 0 || salary <= 0 || isNaN(serviceYrs) || isNaN(salary)) return console.log("Sorry invalid input(s). Please try again. Good bye! ");
	let sum = 100;
	if(serviceYrs >= 10) sum += 100;
	if(salary < 2000 && salary >= 1000) sum += 100;
	if(salary >= 2000) sum += 200;
	return console.log(sum);
}

let yrsOfService = parseFloat(input.question("Please enter you year(s) of service: "));
let salaryAmt = parseFloat(input.question("Please enter your salary: "));
checkIncrement(yrsOfService, salaryAmt);
```
<br>

## Question 7
```
const input = require("readline-sync");

function checkNUmber(numberFromUserInput) {
	if(numberFromUserInput % 1 !== 0) return "THIS IS NOT AN INTEGER BRO 💀!";
	let divisiblyBySix =  numberFromUserInput % 6 == 0;
	let divisiblyByFive = numberFromUserInput % 5 == 0;
	if(divisiblyByFive && divisiblyBySix) return `${numberFromUserInput} is divisible by both 5 and 6.`; 
	if(divisiblyByFive || divisiblyBySix) return `${numberFromUserInput} is divisible by 5 or 6, but not both.`; 
	return `${numberFromUserInput} is not divisible by either 5 or 6.`;
}

let numberFromUserInput = parseInt(input.question("Enter an integer: "));
console.log(checkNUmber(numberFromUserInput));
```

## Question 8
```
const input = require("readline-sync");
const askRank = input.question("Please enter your rank: ");

function PrizeMoney(rank) {
	// not required but added for fun
	if(isNaN(rank) || rank % 1 !== 0 || rank <= 0) return "BRO WHAT THE HELLLLLL PLS VALID RANK BRO 💀!"
	switch(rank){
		case "1":
			return "Your prize money is $1000;";
		case "2":
			return "Your prize money is $800;";
		case "3":
			return "Your prize money is $700;";
		case "4":
			return "Your prize money is $400;";
		case "5":
			return "Your prize money is $300;";
		default:
			return "Your prize money is $20;";
	}
}

console.log(PrizeMoney(askRank));
```