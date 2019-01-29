## Insertion Sort
Perform sorting one item at a time from index 0.
0=n^2

![screenshot 2019-01-28 at 17 23 47](https://user-images.githubusercontent.com/8224798/51842778-b3911200-2322-11e9-87a1-96f964f5ed23.png)

```
def insertionSort(arr): 
  
    # Traverse through 1 to len(arr) 
    for i in range(1, len(arr)): 
  
        key = arr[i] 
  
        # Move elements of arr[0..i-1], that are 
        # greater than key, to one position ahead 
        # of their current position 
        j = i-1
        while j >=0 and key < arr[j] : 
                arr[j+1] = arr[j] 
                j -= 1
        arr[j+1] = key 
```
