# Two Pointer Psuedocode

## Overview of project concept

The two-pointer technique tracks two positions in a list or string and moves them according to a condition. The goal is to examine the relevant elements efficiently without checking every possible combination.

For the sorted-list pair-sum problem, you are trying to find two numbers whose sum equals a target:
- Start one pointer at the beginning and one at the end.
- Add the values at those positions.
- If the sum equals the target, you found a pair.
- If the sum is too small, move the left pointer right to increase it.
- If the sum is too large, move the right pointer left to decrease it.
- Continue until you find a pair or the pointers meet.

The pseudocode should describe how you initialize the pointers, compare the sum, decide which pointer to move, and stop.

## Inputs and expected results

- What information does your algorithm receive?
- What must already be true about the list for this approach to work?
- What should your algorithm return when it finds a matching pair—and when no pair exists?

### Inputs

The two-pointer function will recieve two arguments.

- An array in the form of a list as a data structure
- A target value, which is an integer

### Assumptions

- The list is a sorted list, so that the values are increasing from left to right.
- Can contain duplicate values.

### Return values

For a matching pair:
"The following pair of integers {value1} and {value2} within the provided array sum is {target value}."

For a non-solution, the function shall return a no matching pair statement:
"The provided array does not contain a pair of values that sums to {target value}."

## Initialize the pointers

- Where should each pointer start?
- Does each pointer hold an actual list value or the position of that value?
- How will you identify the last position for a list of any length?
Keep this part focused on the starting setup. We’ll tackle movement and stopping afterward.

### Pointer positions

- The left pointer will start at index list[0].
- The right pointer will start at index [len(list)-1]

### Pointer values

The pointer  is initialized by assigning an index to the left and to the right pointer.  The value held by the pointer is the index value, not the index. After evaluation, the pointers will move either left or right (list[x]+1 or list[y]-1) and evaluate the next value in the array.

### How does the function terminate

When list[x] == list [y] the indices have met and the function will terminate.


## Notes to correct the `Initialize the pointers` section

Your starting positions are right: the first position on the left and the last position on the right. The distinction between a position and its value needs a small correction.
- A pointer holds an index, such as position 0.
- Looking up that index in the list gives you the value stored there.
- Moving a pointer means changing its index—not adding or subtracting from the stored list value.
Your stopping condition also compares values, whereas you need to compare positions. Imagine a list containing two separate entries that both hold 6. Their values are equal, but the pointers haven’t necessarily met—and those two entries could form a valid pair for a target of 12.

Revise your Pointer values and How does the function terminate sections with that distinction in mind.

One question to work through: should the search continue if the left pointer has passed the right pointer? Your stopping rule should account for that as well as meeting.
