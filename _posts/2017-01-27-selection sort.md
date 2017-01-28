---
layout: post
title:  "Selection sort"
date:   2017-01-27
excerpt: "Let's learn about selection sort."
sorts: true
tag:
comments: false
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

### Let's see pesudo code
```{.no-highlight}
selectionSort (A[],n){  			// sort A[1...n]
    for last <- n down to 2 {
		k <-> theLargest(A,last); 	// find the biggest element A[k] in A[1...last]
		A[k] <-> A[last];
	}
}
theLargest(A[],last){ 				// return the biggest element's index in A[1...last]
	largest <- 1;
	for i <- 2 to last
		if(A[i]>A[largest]) then largest -> i;
	return largest;
}
```