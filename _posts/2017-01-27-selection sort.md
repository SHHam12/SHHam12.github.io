---
layout: post
title:  "Selection sort"
date:   2017-01-27
excerpt: "Let's learn about selection sort."
sorts: true
tag:
comments: true
---
## What is selection sort?
* Selection sort is the on of the simplest sorting algorithms.
* Find the biggest element in A[1...n] and replace location to A[n]
* Find the next biggest element in A[1...n-1] and replace location to A[n-1]
* Keep find the element until the sorting is done.

### Let's see image to understand easily.
![selection sort image](http://interactivepython.org/runestone/static/pythonds/_images/selectionsortnew.png)

* When you process selection sort, you can find the smallest element and replace the location to the first.
* However, I prefer to find the largest element, so I will go through with finding the largest element.

### Let's see pseudo code
```{.no-highlight}
selectionSort (A[],n){  // sort A[1...n]
    for last <- n down to 2 {
		k <-> theLargest(A,last); // find the biggest element A[k] in A[1...last]
		A[k] <-> A[last];
	}
}
theLargest(A[],last){ // return the biggest element's index in A[1...last]
	largest <- 1;
	for i <- 2 to last
		if(A[i]>A[largest]) then largest -> i;
	return largest;
}
```

### What about time complexity?
* For selection sort, time complexity is O(n^2).
* When you see the pseudo code, selectionSort(A[],n)'s for loop circulate n-1 times.
* Changing the location of the elements takes constant time.
* For theLagest(A[],last) need to compare n-1 times to find out the biggest elements.
* While selectionSort(A[],n) is processing, sub array's size is decreasing n to 2 by for loop.
* Thus, the total times to compare the elements is (n - 1) + (n - 2) + ... + 2 + 1 = n(n - 1)/2 (by arithmatic sequence). And it is O(n^2)

### Let's see Java
```{.java}
public static void selectionSort(int [] array){
	int max = 0;
	for( int i = 0; i < array.length; i ++){
		for( int j = 0; j < array.length; j ++ ){
			if( array[j] < array[j + 1]){
				max = array[j + 1];
				array[j + 1] = array[j];
				array[j] = max;
			}
		}
	}
	for( int i = 0; i < array.length; i ++){
		System.out.print(array[i] + " ");
	}
}
```