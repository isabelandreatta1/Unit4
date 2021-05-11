# Quizzes 

### Quiz 28
Mirrored time number is a number of two digits x and y which if we write like xy:xy or xy:yx we get a valid time in hh:mm.
Your task is to print the valid combinations separated by spaces. If no such combination exists print 'NONE'.

**Example**
mirroredTime(n=11) → 11:11
mirroredTime(n=12) → 12:12, 12:21
mirroredTime(n=99) → NONE

[HL] Use OOP in your solution.
```py
class Solution:
# create class for the solution, only attribute needed is input
    def __init__(self,input):
        self.input: int = input

    def mirroredTime(self):
        input = self.input
        #make input into a string so that we can concatenate and get index 
        input = str(input)
        #if the input is two digits long and they are not the duplicated digits 
        if len(input) ==2 and (input[0] != input[1]):
          #the minute is the reverse order of the digits/index
            minutes = input[1] + input[0]
            #must validate that the hour and minutes are correct
            #if the input is less than 24 hours and the minutes less than 60
            if int(input)< 24 and int(minutes) < 60:
                return(f"{input}:{input}, {input}:{minutes}")
        #if the input has one digit or has duplicate digits, and if it is less than 24 hours
        #and hence below 60, then print 
        elif int(input) < 24:
            return f"{input}:{input}"
        else:
            return

print(Solution(11).mirroredTime())
print(Solution(12).mirroredTime())
print(Solution(99).mirroredTime())
print(Solution(9).mirroredTime())
```

**Test Screenshot**

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz28image.png)


### Quiz 29

You are trying to repair an LED strip made of N LEDs. You test M sections of the strip. For each one (inclusive range) write down the LEDs that were tested, and the result. Using your test results, output a string representing the condition of your LED strip. First LED is 0.
Use V:working, X:dead ?:not have enough information

[HL] Use OOP in your solution.

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/quiz29testcases.png)

### Quiz 30

Find the number of divisors of the number that are divisible by 2.

findTwoDivisors(8) -> 3
findTwoDivisors(9) -> 0
findTwoDivisors(158260522) -> 8
findTwoDivisors(861648772) -> 16
findTwoDivisors(569097293) -> 0

[HL] Use OOP in your solution.

```py
class SolutionToQuiz:
    def __init__(self, N):
        #create attribute for the input or N
        self.N: int = N


    def DividedByTwo(self):
        N = self.N
        #create variable to count the number of even divisors
        counterofdivisors = 0
        #iterate through numbers until N by two so all numbers are even
        for numbers in range(2,N+1,2):
            #if the module of the number is 0
            if N % numbers == 0:
                #then add one to the number of divisors
                counterofdivisors += 1
        return counterofdivisors

print(SolutionToQuiz(N = 8).DividedByTwo())
print(SolutionToQuiz(N = 9).DividedByTwo())
print(SolutionToQuiz(N=158260522).DividedByTwo())
print(SolutionToQuiz(N=861648772).DividedByTwo())
```
**Test Screenshot** 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz30image.png)

### Quiz 31

There is a saboteur on the ship! An emergency meeting is called. Each crewmember may vote for who they believe is the guilty party. At the end of the meeting, if one crewmember receives more votes than any other, and more than the number of votes skipped, that person is ejected from the ship

**Input as a list of strings**

Green voted for Black
Black voted for Blue
Brown voted for Blue
Blue voted for Black
Cyan skipped voting
Lime voted for Black

**Output** 
Black was ejected.

[HL] Solve and test the program in Javascript

```js
function guiltyparty() {
    var input = "Green voted for Black,Black voted for Blue,Brown voted for Blue,Blue voted for Black,Cyan skipped voting,Lime voted for Black";
    // splits the input for each vote
    var newinput = input.split(",");
    // create empty list for the number of sailors
    var sailors = [];
    // create empty list for all the sailors which are voted
    var sailorsVoted = [];
    var largestcount = 0;
    var kickedout = "";
    var count = 0;
    var skippedCounter = 0;

    // loop through to find the first word (the sailor who voted) and the last (the sailor who got voted) 
    for (votes = 0; votes < newinput.length; votes++) {
        var words = newinput[votes].split(" ");
        // add them to the lists
        sailors.push(words[0]);
        sailorsVoted.push(words[words.length - 1]);
    }
    // iterate through every sailor
    for (counts = 0; counts < sailors.length; counts++) {
        // iterate through every sailor voted
        for (allvotes = 0; allvotes < sailorsVoted.length; allvotes++) {
            // if the sailor is the same as the sailor voted
            if (sailors[counts] === sailorsVoted[allvotes]) {
                // then the counter for the number of votes increase
                count++;
            } else if ("voting" === sailorsVoted[allvotes]) {
                skippedCounter++;
            }
        }
        // if  function to find the max value for counter 
        console.log(sailors[counts], count);
        // if the counter for the sailor is larger than the previous counter, 
        if (count > largestcount) {
            // then it becomes the largest 
            largestcount = count;
            count = 0;
            kickedout = sailors[counts];
        }
    }
}
```

**Test below** 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz31.png) 

### Quiz 32

Black box: create the algorithm that produces the output given the input.


![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz32input2.png)


![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz32input.png)

[HL] Solve and thest the program in Javascript


### Quiz 33

Over the centuries a language evolves, and not only do words appear or disappear, but some letters become more used or on the contrary less used.

In order to be able to quickly analyze many texts, create a program that calculates how many times a given letter is present in a text.

countLetter(text, letter)

[HL] Solve and thest the program in Javascript

**Html Code** 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Quiz33</title>
    <script src="quiz33java.js"></script>

</head>
<body>
<!--this creates a button so that every time i press it, it actives the function in the java file -->
<button onclick="countLetter()">Activate function</button>

</body>
</html>
```

**Javascript Code** 

```js
function countLetter(){
    var text = "hello this is a text to check how many letter 't' this has";
    var letter = "t";
    var counter = 0;
    var characters;
    // create loop which iterates through each character in text
    for (characters = 0; characters < text.length; characters++) {
        if (text[characters] === letter){
            // if the character is the same, then counter increases
            counter +=1;
        }
    }
    console.log(counter);

}
```

**Test**

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz33.png)
### Quiz 34

There are N cities in a row, numbered from 0 to N-1. There are one-way roads going from left to right between cities. For each city, you know where the road starts, or if there is no road (-1). Output the number of cities that can be reached from city 0 using the roads. 

that means that city 0 has no roads incoming (of course, the road could only come from the left, but this is the first city), city 1 has one road incoming from city 0, city 2 has incoming roads from city 1, and city 3 doesn't have any roads incoming, so you have to output 2, because we don't count city 0, city 1 can be reached from city zero (0 -> 1), city 2 can also be reached (0 -> 1 -> 2), and city 3 can't be reached from city 0.

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/quiz34tes.png)

## Quiz 35 

Given an angle in degrees, find the time h:mm at which the hour and minute hands on a 12-hour clock form this angle exactly.

For instance, if the angle required is 45, this occurs at 4:30, when the hour hand is halfway between the 4 and 5, and the minute hand is pointing straight down at the 6. An angle of -45 occurs at 7:30. Both of these angles also occur at other times, but not exactly on the minute mark.


**HTML** 

```html
<!DOCTYPE html>
<html lang="en-US">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>A Digital Analog Clock</title>
    <link rel="stylesheet" href="styleClock.css" type="text/css" media="all">
    <script src="ClockJava.js"defer></script>
</head>

<body>
<main class="main">
    <div class="clockbox">
        <svg id="clock" xmlns="http://www.w3.org/2000/svg" width="600" height="600" viewBox="0 0 600 600">
            <g id="face">
                <circle class="circle" cx="300" cy="300" r="253.9"/>
                <path class="hour-marks" d="M300.5 94V61M506 300.5h32M300.5 506v33M94 300.5H60M411.3 107.8l7.9-13.8M493 190.2l13-7.4M492.1 411.4l16.5 9.5M411 492.3l8.9 15.3M189 492.3l-9.2 15.9M107.7 411L93 419.5M107.5 189.3l-17.1-9.9M188.1 108.2l-9-15.6"/>
                <circle class="mid-circle" cx="300" cy="300" r="16.2"/>
            </g>
            <g id="hour">
                <path class="hour-arm" d="M300.5 298V142"/>
                <circle class="sizing-box" cx="300" cy="300" r="253.9"/>
            </g>
            <g id="minute">
                <path class="minute-arm" d="M300.5 298V67"/>
                <circle class="sizing-box" cx="300" cy="300" r="253.9"/>
            </g>
        </svg>

        <form class = "user-input">
            <input type = "input" id="angle" name="quantity" min="-180" max="180">
            <input type="button" value = "Submit" onClick = "AngleTime()">
        </form>
    </div>

</main>

</body>

</html>
```

**CSS** 
```css
.main {
    display: flex;
    padding: 2em;
    height: 90vh;
    justify-content: center;
}

.clockbox,
#clock {
    width: 100%;
}


.user-input{
    width: 400px;
    margin-left: auto;
    margin-right: auto;
}

.user-input input{
    width: 45%;
}

/* Clock styles */
.circle {
    fill: none;
    stroke: #000;
    stroke-width: 9;
    stroke-miterlimit: 10;
}

.mid-circle {
    fill: #000;
}
.hour-marks {
    fill: none;
    stroke: #000;
    stroke-width: 9;
    stroke-miterlimit: 10;
}

.hour-arm {
    fill: none;
    stroke: #000;
    stroke-width: 17;
    stroke-miterlimit: 10;
}

.minute-arm {
    fill: none;
    stroke: #000;
    stroke-width: 11;
    stroke-miterlimit: 10;
}

.second-arm {
    fill: none;
    stroke: #000;
    stroke-width: 4;
    stroke-miterlimit: 10;
}

/* Transparent box ensuring arms center properly. */
.sizing-box {
    fill: none;
}

/* Make all arms rotate around the same center point. */
/* Optional: Use transition for animation. */
#hour,
#minute,
#second {
    transform-origin: 300px 300px;
    /*transition: transform .5s ease-in-out;*/
}
```

**Javascript** 

```js
const HOURHAND = document.querySelector("#hour");
const MINUTEHAND = document.querySelector("#minute");
// call the hour and minute hand lines created in the html 

function AngleTime() {
    var input = document.getElementById("angle").value;
    // gets the value from the user using the id assigned to the form in html
    var minutes = 0;
    var hour = 0;
    var angle;
    // repeat or loop until 720, or every single possibility of time in a clock
    // because there are 60 minutes in one hour, we need to times this by 12 (the nuuber of hours)
    for (loop = 0; loop < 720; loop++) {
        // print out all the possible times to check if the clock works
        // to find hours, divide by 60 while to find minutes it is the mod of 60 because there are only
        // 59 minutes possible
        console.log( "Hour", parseInt(loop/60), "Minute", loop % 60);
        // to find the angle of the hour, get the hour and then times by 30
        // 30 because an hour hand moves 30 degrees for each hour or 360/12 = 30
        hour = parseInt(loop/60*30);
        // to find the angle of the minutes, get the minutes and then times by 6
        // 6 because each minute hand moves 6 degrees, or 360/60 = 6
        minutes = parseInt(loop%60*6);
        // to find the angle the hour and minute create, need to subtract the minutes from hours
        angle = (minutes - hour);
        console.log(angle, hour, loop);
        //if the angle found is the same as the user input
        if (angle == input) {
            console.log("Angle", angle, "Hour", hour, "Minute", minutes);
            //print the angle, hour and minutes
            let hrPosition = hour;
            //create variables for the positions of the hour and minute hands
            let minPosition = minutes;
            //use transform method to move the clock hands depending on their respective angles
            HOURHAND.style.transform = "rotate(" + hrPosition + "deg)";
            MINUTEHAND.style.transform = "rotate(" + minPosition + "deg)";
        }
    }
}
```
     
Test Cases:
![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz35.png)

**Test** 


![](https://github.com/isabelandreatta1/Unit4/blob/main/images/quiz35test.png) 


[HL] Solve and thest the program in Javascript

## Quiz 36 

Black Box 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/quiz36.png)

**HTML Code** 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Quiz36</title>
    <script src="quiz36java.js"></script>
</head>
<body>
<form class = "user-input">
    <input type = "input" id="input">
</form>
<button onclick="Average()">Activate function</button>
</body>
</html>
```


**Javascript** 
```js
function Average(){
    // call and create variable for the user input
    var input = document.getElementById("input").value;
    //because user input is a string, split to ignore commas
    input = input.split(',');
    var length = input.length;
    var output = 0;
    var sum = 0;
    var type = "";
    var middleOfAverage;
    var numbers;
    // if the length of input is even, or mod 2 is 0
    if (length % 2 == 0){
        // then use sort method to sort by numeric ascending order
        input = input.sort();
        // then find the middle index by dividing the length of input by two
        middleOfAverage = parseInt(length/2);
        // output then becomes the median, or the number in the middle 
        output = input[middleOfAverage];
        type = "even";
    }
    else{
        //else means that the length of the input is odd
        for (numbers = 0; numbers < length; numbers ++){
            // add each number to each other 
            sum += parseInt(input[numbers]);
            type = "odd";
        }
        //divide sum by the length of input 
        output = (sum/length);
    }
    console.log("The length of the input is", type, ". ", "The average of",input," is ", output);
}
```

**Test** 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/quiz36test.png)

### Quiz 37 

Create a program that prints the number corresponding to the position of the highest hill in the string. A hill is represented by a series of increasing and decreasing numbers. Its height is the value of the number at the top of the hill.
If there is no hill (as in "000", "1" or "666"), print 0.

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz37.png)

**HTML** 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Quiz37</title>
    <script src="quiz37java.js"></script>
</head>
<body>
<button onclick="MaxHeight()">Activate function</button>

</body>
</html>
```
**Javascript** 

```js
function MaxHeight(){
    var input = "384";
    console.log("input is:", input);
    var biggest_difference = 0;
    for (i = 0; i <= input.length -2; i++){
        // create loop which iterates through every number
        // minus 2 length because i will be comparing the first number with its succeeding one
        var difference = (parseInt(input[i+1])-parseInt(input[i]));
        // calculate the difference
        if (Math.abs(difference) > Math.abs(biggest_difference)){
            // if the absolute value of the difference is larger then update the variable
            biggest_difference = difference;
        }
    }
    // return what the biggest difference is after checking through each number
    console.log("Max difference is: ", biggest_difference);
}
```
**Test** 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/quiz37_A.png)

Test 1 


![](https://github.com/isabelandreatta1/Unit4/blob/main/images/quiz37_B.png)

Test 2 

### Quiz 38

Data structure alignment is the way data is arranged and accessed in computer memory. In C, a low level PL, a structure creates packs of one size. It takes the biggest size of object to be stored and chooses that to be the size of each pack. Each pack will take up that much memory even if the pack is not full. Then it takes objects in order and groups them into packs.

[HL] Solve and test the program in Javascript

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz28.png) 

**HTML**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Quiz38</title>
    <script src="quiz38.js"></script>
</head>
<body>
<button onclick="datastructure()">Activate function</button>

</body>
</html>
```
**Javascript** 
```js
function datastructure(){
    var input = [5,10,16,5,10];
    // use max function which will find largest number of input, or in this case, largest pack
    var biggestSize = Math.max.apply(0,input);
    // number of packs starts with 1, this will be counter of number of packs
    var numberOfPacks = 1;
    // adder keeps on adding each pack
    var adder = 0;
    var packs;
    // iterate through every pack in the input
    for (packs = 1; packs <= input.length; packs ++){
        // if the adder is equal to or smaller than the largest pack
        if (adder <= biggestSize){
            // then it means is not full,
            adder += input[packs];
        }
        // if the last pack has a remainder
        else if (packs == input.length -1){
            if (adder != 0) {
                //then add to counter
                numberOfPacks += 1;
            }
        }
        else {
            // if the adder is larger than the pack, then add to the counter
            numberOfPacks += 1;
            // add previous pack
            adder = input[packs-1];
        }
    }

    // print input and bytes to check if correct
    console.log("input is", input);
    console.log(numberOfPacks * biggestSize, "bytes");

        // example of how it works:
        // 8 bits one byte
        // find biggest piece of data of the same size, and then fit in chunk of sizes
        // e.g. 1,2,8,2,4
        // will create spaces in the ram that are 8 bits small and then put data inside
        // total is 3 packs of 8 bytes
        // must be in order

}
```

**Tests** 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz28_Test1.png) 

Test 1 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz28_Test2.png) 

### Quiz 39

Narcissistic Numbers 
A narcissistic number is a number that equals the sum of its own digits each raised to the power of the number of digits.

For example, 153 is a narcissistic number because 
1^3 + 5^3 + 3^3 = 153.
The first few narcissistic numbers are: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 153, 370, and 371.

Create a program to find the amount of narcissistic numbers between 2 given integers m and n (excluding m and n) and print them.

### Quiz 40 


Lily was crossing a thick forest when she realizes that there is a tiger ahead of her who has seen Lily. Lily quickly takes out a matchbox from her bag and burns a matchstick, because the tiger is afraid of fire. A matchstick takes 5 seconds to burn completely.
Given that the length of the forest that Lily needs to cross is l meters , and that Lily's speed is s centimeters per second, print the minimum number of matchsticks Lily needs to burn to cross the forest safely.

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz40.png)

**HTML** 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Quiz40</title>
    <script src="quiz40.js"></script>
</head>
<body>
<button onclick="TigerEscape()">Activate function</button>
</body>
</html>
```

**Javascript** 

```js
function TigerEscape(){
    // create variables for two inputs
    var l = 12345;
    var s = 123;
    // find time that takes to travel forest
    var seconds = (l * 100)/s;
    // then divide, rounding up, by the time it takes to burn a match 
    var output = Math.ceil(seconds/5);
    console.log(output, "matches");
}

```

**Tests** 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz40Test1.png)

**Test 1** 

In the test above, l is 12345, and s is 123. 

![](https://github.com/isabelandreatta1/Unit4/blob/main/images/QuizTest2.png)

**Test 2** 

In the test above, l is 100 and s is 100. 


      



