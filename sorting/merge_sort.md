## Merge Sort
- Merge sort is a sorting technique based on divide and conquer technique. With worst-case time complexity being Ο(n log n),
Merge sort first divides the array into equal halves and then combines them in a sorted manner.
  ![screenshot 2019-01-28 at 11 14 36](https://user-images.githubusercontent.com/8224798/51822951-e3262700-22ee-11e9-89b5-3710948902c6.png)

```
def mergeSort(alist):
    print("Splitting ",alist)
    if len(alist)>1:
        mid = len(alist)//2
        lefthalf = alist[:mid]
        righthalf = alist[mid:]

        mergeSort(lefthalf)
        mergeSort(righthalf)

        i=0
        j=0
        k=0
        while i < len(lefthalf) and j < len(righthalf):
            if lefthalf[i] < righthalf[j]:
                alist[k]=lefthalf[i]
                i=i+1
            else:
                alist[k]=righthalf[j]
                j=j+1
            k=k+1

        while i < len(lefthalf):
            alist[k]=lefthalf[i]
            i=i+1
            k=k+1

        while j < len(righthalf):
            alist[k]=righthalf[j]
            j=j+1
            k=k+1
    print("Merging ",alist)
```
