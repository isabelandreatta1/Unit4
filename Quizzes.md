# Quizzes 

### Quiz 28
Mirrored time number is a number of two digits x and y which if we write like xy:xy or xy:yx we get a valid time in hh:mm.
Your task is to print the valid combinations separated by spaces. If no such combination exists print 'NONE'.

**Example**
mirroredTime(n=11) → 11:11
mirroredTime(n=12) → 12:12, 12:21
mirroredTime(n=99) → NONE

[HL] Use OOP in your solution.


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

[HL] Solve and thest the program in Javascript


### Quiz 33

Over the centuries a language evolves, and not only do words appear or disappear, but some letters become more used or on the contrary less used.

In order to be able to quickly analyze many texts, create a program that calculates how many times a given letter is present in a text.

countLetter(text, letter)

[HL] Solve and thest the program in Javascript

### Quiz 34

There are N cities in a row, numbered from 0 to N-1. There are one-way roads going from left to right between cities. For each city, you know where the road starts, or if there is no road (-1). Output the number of cities that can be reached from city 0 using the roads. 

that means that city 0 has no roads incoming (of course, the road could only come from the left, but this is the first city), city 1 has one road incoming from city 0, city 2 has incoming roads from city 1, and city 3 doesn't have any roads incoming, so you have to output 2, because we don't count city 0, city 1 can be reached from city zero (0 -> 1), city 2 can also be reached (0 -> 1 -> 2), and city 3 can't be reached from city 0.
