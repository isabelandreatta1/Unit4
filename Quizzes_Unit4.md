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
        self.N: int = N

    def DividedByTwo(self):
        N = self.N
        counterofdivisors =0
        for numbers in range(2,N+1,2):
            if N % numbers == 0:
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

### Quiz 34

There are N cities in a row, numbered from 0 to N-1. There are one-way roads going from left to right between cities. For each city, you know where the road starts, or if there is no road (-1). Output the number of cities that can be reached from city 0 using the roads. 

that means that city 0 has no roads incoming (of course, the road could only come from the left, but this is the first city), city 1 has one road incoming from city 0, city 2 has incoming roads from city 1, and city 3 doesn't have any roads incoming, so you have to output 2, because we don't count city 0, city 1 can be reached from city zero (0 -> 1), city 2 can also be reached (0 -> 1 -> 2), and city 3 can't be reached from city 0.

## Quiz 35 

Given an angle in degrees, find the time h:mm at which the hour and minute hands on a 12-hour clock form this angle exactly.

For instance, if the angle required is 45, this occurs at 4:30, when the hour hand is halfway between the 4 and 5, and the minute hand is pointing straight down at the 6. An angle of -45 occurs at 7:30. Both of these angles also occur at other times, but not exactly on the minute mark.

Test Cases:
![](https://github.com/isabelandreatta1/Unit4/blob/main/images/Quiz35.png)

[HL] Solve and thest the program in Javascript

