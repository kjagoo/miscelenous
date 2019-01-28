# Graphs
### Breath First Search
### Depth First Search
### A* Search

## Sorting 
### Selection Sort
>repeatedly selects the next-smallest element and swaps it into place
- Find the smallest card. Swap it with the first card.
- Find the second-smallest card. Swap it with the second card.
- Find the third-smallest card. Swap it with the third card.
- Repeat finding the next-smallest card, and swapping it into the correct position until the array is sorted.
### Insertion Sort
- Call insert to insert the element that starts at index 1 into the sorted subarray in index 0.
- Call insert to insert the element that starts at index 2 into the sorted subarray in indices 0 through 1.
- Call insert to insert the element that starts at index 3 into the sorted subarray in indices 0 through 2.
…
- Finally, call insert to insert the element that starts at index n-1 n−1 into the sorted subarray in indices 0 through n-2 n−2.
### Merge Sort
 ![screenshot 2019-01-28 at 11 14 36](https://user-images.githubusercontent.com/8224798/51822951-e3262700-22ee-11e9-89b5-3710948902c6.png)
- Divide by finding the number q q of the position midway between p p and r r. Do this step the same way we found the midpoint in binary search: add p p and r r, divide by 2, and round down.
- Conquer by recursively sorting the subarrays in each of the two subproblems created by the divide step. That is, recursively sort the subarray array[p..q] and recursively sort the subarray array[q+1..r].
- Combine by merging the two sorted subarrays back into the single sorted subarray array[p..r].

### Quick Sort
- Divide by choosing any element in the subarray array[p..r]. Call this element the pivot. Rearrange the elements in array[p..r] so that all elements in array[p..r] that are less than or equal to the pivot are to its left and all elements that are greater than the pivot are to its right. We call this procedure partitioning. At this point, it doesn't matter what order the elements to the left of the pivot are in relation to each other, and the same holds for the elements to the right of the pivot. We just care that each element is somewhere on the correct side of the pivot.
As a matter of practice, we'll always choose the rightmost element in the subarray, array[r], as the pivot. So, for example, if the subarray consists of [9, 7, 5, 11, 12, 2, 14, 3, 10, 6], then we choose 6 as the pivot. After partitioning, the subarray might look like [5, 2, 3, 6, 12, 7, 14, 9, 10, 11]. Let q be the index of where the pivot ends up.
- Conquer by recursively sorting the subarrays array[p..q-1] (all elements to the left of the pivot, which must be less than or equal to the pivot) and array[q+1..r] (all elements to the right of the pivot, which must be greater than the pivot).
- Combine by doing nothing. Once the conquer step recursively sorts, we are done. Why? All elements to the left of the pivot, in array[p..q-1], are less than or equal to the pivot and are sorted, and all elements to the right of the pivot, in array[q+1..r], are greater than the pivot and are sorted. The elements in array[p..r] can't help but be sorted!
Think about our example. After recursively sorting the subarrays to the left and right of the pivot, the subarray to the left of the pivot is [2, 3, 5], and the subarray to the right of the pivot is [7, 9, 10, 11, 12, 14]. So the subarray has [2, 3, 5], followed by 6, followed by [7, 9, 10, 11, 12, 14]. The subarray is sorted.

## Hashing
### MD5
### Linear Probing
### Collisions# miscelenous
