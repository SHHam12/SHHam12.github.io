---
layout: post
title:  "Insertion sort"
date:   2017-01-27
excerpt: "Let's learn about insertion sort."
sorts: true
tag:
comments: true
---
## What is Insertion sort?
* Insertion sort is adding a element to the sorted array A[1...i] to make sorted array A[1...i+1] repetitively.
* Selection sort and bubble sort is decreasing size from A[1...n], but insertion sort is adding elements from A[1] to A[1...n]

### Let's see image to understand easily.
![insertion sort image](http://www.w3resource.com/w3r_images/insertion-sort.png)


### Let's see pseudo code
```{.no-highlight}
insertionSort (A[],n){  // sort A[1...n]
    for i <- 2 to n {              //# 1
		loc <- i - 1;
		newItem <- A[i];
		//At this point, A[1...i-1]is already sorted.
		while (loc >= 1 and newItem < A[loc]){
			A[loc + 1] <- A[loc]
			loc--;
		}    
	}
}
```
### What about time complexity?
* #1 for loop circulate n - 1 times just like selection sort.
* while loop circulate at most i - 1 times.
* Worst case, A[i] goes to A[1], so needs i - 1 times circulate.
* Optimun case, A[i] stays its location, while loop dose not process.
* So, the time complexity is O(n^2).

### Let's see Java
```{.java}
public static void insertionSort(int [] array){
	for (int i = 1; i < array.length; i ++){
		int temp = a[i];
		for(int j = i - 1; j >=0 && temp < array[j]; j --)
			array[j + 1] = array[j];
		array[j + 1] = temp;
}
```