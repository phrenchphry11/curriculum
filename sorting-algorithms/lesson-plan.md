# Sorting Algorithms

### Projected Time
7 hours


### Prerequisites
Here are links to lessons that should be completed before this lesson.
- Recursion
- Searching (Particularly Binary Search)


### Objectives
**Students will be able to** 
- Understand what an algorithm is.
- Understanding what a sorting algorithm is.
- Understand the mechanics of a few sorting algorithms including Bubble Sort, Merge Sort, and Quick Sort.
- Understand the Runtime Complexity of these algorithms.

### Materials and Useful Videos

- [Sorting Algorithms Visualized](https://www.toptal.com/developers/sorting-algorithms/)
- [Bubble Sort With Hungarian Folk Dance](https://www.youtube.com/watch?v=lyZQPjUT5B4)
- [Merge Sort With German Folk Dance](https://www.youtube.com/watch?v=XaqR3G_NVoo)
- A Deck of Cards

### Pre-Lesson Warm Up and Game (30 minutes)
- Discussion topic: What is an algorithm?  Can you give us an example of an algorithm?
  - An algorithm is a way for describing automated processes
- Discussion topic: What is a Sorting Algorithm? Can you give us an example of something that we sort in our day-to-day lives?
  - A Sorting Algorithm orders items in a group according to a specificed attribute.  ie: Order a roster of students by name, Order cartons of milk by exiration date
- Discussion topic: Why do we need sorting algorithms in Computer Science?
  - Let's do a Card-Sorting activity.  Partner up in groups of two or three, and order cards from lowest to highest (all of the suite).  Give student groups a deck of cards and give them each a suite of cards to sort.
  - After 10 minutes of sorting, let's reflect on how we accomplished it.  Did we sort the cards differently from the people in our partner groups?  Did we compare a few at a time?  Did we look for the lowest first and then go from there?  Do you think we could sort in fewer "moves"?
  - After this Card-Sorting activity, it's clear there are a lot of different ways to sort cards!  This translates right over to how computer scientists sort Lists.  As Computer Scientists, we have lots of different algorithms to use that allow us to sort - from BubbleSort, to MergeSort, to QuickSort!  Some algorithms aren't as fast as others (Obama knows not to use the BubbleSort: https://www.youtube.com/watch?v=k4RRi_ntQc8), but there are many tradeoffs to different algorithms!
  - Why is sorting important?  Remember Binary Search last lesson?  Well, we need a sorted list to do Binary Searching!  

### Lesson (3 hours)

So, remember how we can sort cards lots of different ways? Let's talk about all the ways computers sort Lists.

Let's start with a Bad Way To Sort:

####BogoSort (10 minutes)

Say we want to sort a deck of cards:

1. Toss them in the air!
2. Pick them up one by one.
3. Are they sorted?
4. If not, repeat lines 1 - 3

Let's talk about the Complexity of BogoSort.  Here's the pseudocode:

```python
def bogo_sort(L):
 while not is_sorted(L):
 	random.shuffle(L)
```

*The best case?*

O(n) where n is the length of the list, because we have to check the list is sorted.

*The worst case?*

O(????) because this could NEVER END if we get really unlucky.  

Hopefully you can see why we never want to use this algorithm again.

#### BubbleSort (30 minutes)

[Thanks, Obama]( https://www.youtube.com/watch?v=k4RRi_ntQc8)

How does it work?

1. Compare consecutive pairs of elements.
2. Swap elements in the pair so that the smaller one is first.
3. When we reach the end of the list, start over!
4. Stop when no more swaps have been made.

Demonstation video: https://www.youtube.com/watch?v=Cq7SMsQBEUw (useful in slo-mo)

Let's watch a folk dance interpretation of Bubble Sort: https://www.youtube.com/watch?v=lyZQPjUT5B4

Let's break into groups again and try out the sorting algorithm on our own decks of cards!

What's the Complexity of BubbleSort?

```Python
def bubble_sort(L):
    swap = False
    while not swap:
        print('bubble sort: ' + str(L))
        swap = True
        for j in range(1, len(L)):
            if L[j-1] > L[j]:
                swap = False
                temp = L[j]
                L[j] = L[j-1]
                L[j-1] = temp
```

We have nested loops: the while-loop and the for-loop!  The outer loop does passes until there are no more swaps.  Thus, the runtime is O(n^2).

Group question:  what state would the list be in for Bubble Sort to have the worst possible performance? 

* If the smallest element of the list is at the back, Bubble Sort will perform at the absolute worst. Because in each iteration only the largest unsorted element gets put in its proper location, when the smallest element is at the end, it will have to be swapped each time through the list, and it wont get to the front of the list until all n iterations have occurred.

#### SelectionSort (15 minutes)

How does it work?

1. First step:
   1. Extract the smallest element
   2. Swap it with the element at index 0
2. Next step:
   1. In the remaining unsorted sublist, extract the smallest element.
   2. Swap it with the element at index 1
3. At the i'th step, the first i elements of the list are guaranteed to be sorted.

Demonstration video: https://www.youtube.com/watch?v=92BfuxHn2XE

What's the Complexity of SelectionSort?

```python
def selection_sort(L):
    suffixSt = 0
    while suffixSt != len(L):
        print('selection sort: ' + str(L))
        for i in range(suffixSt, len(L)):
            if L[i] < L[suffixSt]:
                L[suffixSt], L[i] = L[i], L[suffixSt]
        suffixSt += 1
```

Again, there's a nested loop, so worst-case runtime is O(n^2)!

#### Can we do better than O(n^2)?????

#### MergeSort








### Independent Practice

Class does this thing themselves with specific additional items.


### Challenge

Implement Bubble Sort, Selection Sort, and Merge Sort on your own!

