## Selection Sort
- Swap the largest item position in the list to the largest index value.
The smallest element is selected from the unsorted array and swapped with the leftmost element, and that element becomes a part of the sorted array. This process continues moving unsorted array boundary by one element to the right.
Worst case complexities are of Ο(n2), where n is the number of items.
  ![screenshot 2019-01-28 at 17 23 47](https://user-images.githubusercontent.com/8224798/51842778-b3911200-2322-11e9-87a1-96f964f5ed23.png)
```
def selectionSort(alist):
   for fillslot in range(len(alist)-1,0,-1):
       positionOfMax=0
       for location in range(1,fillslot+1):
           if alist[location]>alist[positionOfMax]:
               positionOfMax = location

       temp = alist[fillslot]
       alist[fillslot] = alist[positionOfMax]
       alist[positionOfMax] = temp
```

