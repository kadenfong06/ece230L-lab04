# Lab 04 - SOP/POS and KMaps

**Group 11:** Kaden Fong and Ethan Mix

In this lab, you’ve learned how to apply KMaps, Sum Of Products and Products of
sums to simplify digital logic equations. Then, you’ve proven out that they work
using an implemented design on your Basys3 boards.

## Rubric

| Item | Description | Value |
| ---- | ----------- | ----- |
| Summary Answers | Your writings about what you learned in this lab. | 25% |
| Question 1 | Your answers to the question | 25% |
| Question 2 | Your answers to the question | 25% |
| Question 3 | Your answers to the question | 25% |

## Lab Summary

In this lab, we learned how to use KMaps to simplify logic equations using Sum of Products and Products of Sums. We used the truth table to create a naive equation using all the rows that had an output of 1. Then we made a KMap in order to create simplified SOP and POS equations. We added the equations into Verilog and simulated them to make sure their outputs matched, which they did. Then we generated the bitstream and tested the design on the Basys3 board.

## Lab Questions

### Why are the groups of 1’s (or 0’s) that we select in the KMap able to go across edges?

The groups can go across edges because the KMAP is kind of like a cylinder where it can wrap around. The cells on the opposite edges are still adjacent since they differ by just one variable. That's what allows us to group them together and simplify the equation.

### Why are the names Sum of Products and Products of Sums?

SOP gets its name because the variables are all ANDed together to create the variables being products terms, and then they get ORed together to create a sum. POS is the opposite, where the variables are ORed together to create sum terms, and then those terms are ANDed together.

### Open the test.v file – how are we able to check that the signals match using XOR?

XOR allows us to check if the signals match because XOR outputs 0 when both inputs are the same and 1 when they're different. The test compares led[0] to led[1] and led[2]. If XOR returns something other than 0, the outputs don't match and the test would fail. The loop tests all 16 possible switch combinations to make sure all three implementations give the same output.