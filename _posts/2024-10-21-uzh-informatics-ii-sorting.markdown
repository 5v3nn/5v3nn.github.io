---
layout: post
title:  "Informatics II - Sorting"
date:   2024-10-21 20:20:00 -0400
categories: uzh informatics-ii algorithms sorting
---

Sorting is a fundamental problem and is often the key subroutine or bottleneck
for algorithms. Here are some examples which will be discussed during the
course. They all requires **random access**, i.e., that each element in the
array can be accessed directly, and **sort in place**, i.e., rearranging the
elements within the array with at most a constant number stored outside the
array at any time.

- $$ n^2 $$ comparisons, usually **incremental**: Bubble Sort, Selection Sort,
  Insertion Sort
- $$ n\log n $$ comparisons, usually **divide and conquer**: Merge Sort, Heap
  Sort, Quick Sort


# Note on Asymptotic Complexities and Loop Invariants 

You may note that for the number of comparisons and moves I already use the
**asymptotic complexity**, here the Big-O notation. This is for revisiting
students. If you are not familiar with that notation, do not worry, it will be
discussed later.

Same goes for **loop invariants**, this will also be discussed later. 


# Bubble Sort

- Swap every unsorted adjecent elements
- As we can see in the image below, it basically "bubbles" with each iteration
  the largest element to the end
- Thus, when we would look at the loop invariant (discussed later), the
  subarray $$ A[i..n] $$ (red characters) is always sorted with the largest $$
  n-i+1 $$ elements

![Bubble Sort visualization](/assets/uzh/info2/1_bubble_sort_vis.png)

- Number of comparisons is independent of original order: $$ O(n^2) $$
- Number of moves:
  - Best case if array already sorted: $$ O(1) $$ (because $$ 0 \in O(1) $$
    (constant))
  - Worst case if array reversed sorted, then switch always: $$ O(n^2) $$
  
Note the color codes where the summations and numbers come from. 

![Bubble Sort calculations for number of comparisons and moves](/assets/uzh/info2/1_bubble_sort_comparisons_and_moves.png)


# Selection Sort

- Select smallest element and swap it with the 1st element
- With each iteration (outer for loop), the algorithm goes through the
  remaining (black characters) elements, and selects the largest one (inner for
  loop)
  - Once it has reached the end of the array, it swaps the "selected" largest
    element to the front (end of the red characters)
- Thus, when we look at the loop invariant, the subarray $$ A[0..i] $$ (red
  characters) contains always the sorted $$ i $$ elements

![Selection Sort visualization](/assets/uzh/info2/1_selection_sort_vis.png)

- Number of comparisons is independent of original order: $$ O(n^2) $$
- Number of moves has every iteration exactly one exchange (even with itself):
  $$ O(n) $$

Note again the color codes where the summations and numbers come from. 

![Selection Sort calculations for number of comparisons and moves](/assets/uzh/info2/1_selection_sort_comparisons_and_moves.png)


# Insertion Sort

- Takes an element ($$ t=A[i] $$) and inserts it into the right place in the
  sorted subarray
- Note that here we have the variable `t` which stores the smallest element 
- Classical example of how most people sort a hand of cards 
- When we look at the loop invariant, the subarray $$ A[0..i] $$ (red
  characters) contains the $$ i $$ smallest elements in a sorted order


For the example below, we analyze the algorithm in the following way. 
1. Store the next character (here `'i'`) in the variable `t` (such that we do
   not loose it)
2. Copy (here even overwrite) all elements in the ordered subarray from the
   right to left which are greater than `t=A[i]='i'`, one by one
   - Important to note that the running variabl eof the `for` loop is not the
     same as the `'i'` which is the elment we are looking at right now)
3. Once we found the spot where `t` should go, we overwrite it at the position
   `j+1`


A good exercise is to ask yourself, why do we need a `while` loop here, and not
a `for` loop.

Another good exercise is to explain why we have to store `t` at index `j+1` and
not `j`.


![Insertion Sort visualization](/assets/uzh/info2/1_insertion_sort_vis.png)

- Number of comparisons:
  - Best case if already sorted (no, or constant, inner `while` loop): $$ O(n)
    $$
  - Worst case if sorted in reverse: $$ O(n^2) $$ 
- Number of moves:
  - Best case if already sorted (element `t=A[i]` is the greatest and stays,
    thus no inner `while` loop): $$ O(n) $$
  - Worst case if sorted in reverse (element `t=A[i]` is the smallest, and needs to go at the beginning of the sorted subarray $$ A[0..i] $$): $$ O(n^2) $$

Note again the color codes where the summations and numbers come from. 

![Insertion Sort calculations for number of comparisons and moves](/assets/uzh/info2/1_insertion_sort_comparisons_and_moves.png)


# Exercises

True or false?
- The bubble sort algorithm can be implemented using two nested `while` loops.
- The insertion sort algorithm can be implemented using two nested `for` loops.
- Given the same input, all three sorting algorithms always need the same
  number of comparisons.
- All three sorting algorithms only compare two adjacent elements in an array.


Solutions in the source text of this website.

<!-- Solutions: -->
<!-- - *True, True, False, False* -->


# Sources

- [Prof. Böhlen's Slides](https://www.ifi.uzh.ch/en/dbtg/teaching/courses/infoII.html "Prof. Böhlen's Slides")
- [Christoph Vogel](https://www.physik.uzh.ch/~vogelch/algodat/index.html "Christoph Vogel")
- Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford
  Stein. 2009. Introduction to Algorithms, Third Edition (3rd. ed.). The MIT
  Press.

