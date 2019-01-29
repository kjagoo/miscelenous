## Selection Sort
- Swap the largest element position in the list with a lower element on the rightmost side of the unsorted array.
The large element becomes a part of the sorted array. This process continues moving unsorted array boundary by one element to the right.
Worst case complexities are of Ο(n2), where n is the number of items.

![screenshot 2019-01-29 at 10 03 11](https://user-images.githubusercontent.com/8224798/51890452-1dee9480-23ad-11e9-951a-13f4795ba998.png)

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

