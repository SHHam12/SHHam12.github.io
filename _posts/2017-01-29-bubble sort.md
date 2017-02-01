---
layout: post
title:  "Bubble sort"
date:   2017-01-27
excerpt: "Let's learn about bubble sort."
sorts: true
tag:
- Algorithm
- sort
- O(n^2)
comments: true
---
## What is Bubble sort?
* Bubble sort is the one of the simplest sorting algorithms.
* Bubble sort is similar to selection sort because it moves the biggest element to last index of A[1...n], but the way to move the biggest element to right.

### Let's see image to understand easily.
![bubble sort image image](http://www.programiz.com/sites/tutorial2program/files/Bubble-sort-algorithm-programming.jpg)

* When you process bubble sort, you can find the smallest element and replace the location to the first just like selection sort.
* However, I prefer to find the largest element, so I will go through with finding the largest element.

### Let's see pseudo code
```{.no-highlight}
bubbleSort (A[],n){  // sort A[1...n]
    for last <- n down to 2 {              //# 1
		sorted <- TRUE;
		for i <- to last -1 {              //# 2
			if(A[i] > A[i + 1]) then {
				A[i] <-> A[i + 1];        
				// # 3 exchanging elements
				sorted <- FALSE;
			}
		}
		if(sorted = TRUE) then return;     
	}
}
```

### What about time complexity?
* #1 for loop circulate n - 1 times just like selection sort.
* #2 for loop circulate last - 1 times.
* last is decreased by 1 until it starts n to 2, so the total circulation time is  (n-1)+(n-2)+...+2+1 = n(n-1)/2 (by arithmatic sequence).
* #3 takes constant time to process, so the time complexity is O(n^2).

### Let's see Java
```{.java}
public static void bubbleSort(int [] array){
	int max = 0;
	for( int i = 0; i < array.length; i ++){
		for( int j = 1; j < array.length - i; j ++ ){
			if( array[j] < array[j - 1]){
				max = array[j - 1];
				array[j - 1] = array[j];
				array[j] = max;
			}
		}
	}
	for( int i = 0; i < array.length; i ++){
		System.out.print(array[i] + " ");
	}
}
```