## Chapter 2 - Sorting

### Selection Sort
 - First, find the smallest item in the array and exchange it with the first entry.
 - Then, find the next smallest item and exchange it with the second entry.
 - Continue until the array is sorted.

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

