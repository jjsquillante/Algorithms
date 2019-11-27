# Chapter 2 - Sorting

## Selection Sort
 - First, find the smallest item in the array and exchange it with the first entry.
 - Then, find the next smallest item and exchange it with the second entry.
 - Continue until the array is sorted.
 
***Running time is insensitive to input.*** 
 The process of finding the smallest item on one
 pass through the array does not give much information about where the smallest item
 might be on the next pass. This property can be disadvantageous in some situations.
 For example, the person using the sort client might be surprised to realize that it takes
 about as long to run selection sort for an array that is already in order or for an array
 with all keys equal as it does for a randomly-ordered array!
 
 ***Data movement is minimal.*** 
  Each of the N exchanges changes the value of two array
  entries, so selection sort uses N exchanges—the number of array accesses is a linear
  function of the array size. None of the other sorting algorithms that we consider have
  this property (most involve linearithmic or quadratic growth).

```
function exch(arr, i, min) {
 var itemToSwitch = arr[i];
 arr[i] = arr[min];
	arr[min] = itemToSwitch;
}

function selectionSort(arr) {
  for (var i = 0; i < arr.length; i++) {
    var min = i;
    for (var j = i + 1; j < arr.length; j++) {
      if (arr[j] < arr[min]) {
        min = j;
      }
    }
    exch(arr, i, min);
  }
  return arr;
}

```

