# WEEK 2 - Search and Sort Techniques

### This week we discussed the following key points

* Previous week Assignment discussion
* Search Techniques - Linear, Binary, Ternary
* Sort Techniques - Insertion, Merge, Quick
* Ad-hoc Problems

## Search Techniques

### 1. Linear Search

* In this search technique, each element of the array or list is compared with the key to find a match.
* Considering the worst case scenario where the key is present at the end of the array of size 'n', one has to iterate over the
entire array to find the key. This will take too much time if n is a large value.
* Hence, to speed up the process of finding a value in a given array or list binary search technique is introduced.

#### Implementation
  
  Pseudo Code is as follows 
  
  ```
  for(start to end of array)
{
    if (current_element equals to 5)  
    {
        print (current_index);
    }
}
  ```
#### Time Complexity

The time complexity of Linear Search is <b> O(n) </b> as each element is compared only once.

#### Applications

* Even when binary search is faster than linear search in most cases, while working with data structures such as linked lists linear
search excels over binary search.

### 2. Binary Search

* In this search technique, one half of the sorted array is skipped in every iteration until we find the key to be searched.
* This reduces the time for searching a key and hence increases the efficiency over linear search.
* Only disadvantage is that, the given array or list must be sorted.

#### Implementation 

```
int binary_search(int low ,int high ,int key)
{
  while( low <= high )
  {
    int mid = low + (high-low)/2;
    
    if ( ar[mid] == key )
    {
      return mid;
    }
    else if ( ar[mid] < key )
    {
     low = mid + 1 ;
    }
    else
    {
     high = mid - 1 ;
    }
  }
   return -1 ;              // key not found
} 
     
```

#### Time Complexity

The time complexity of Binary Search is <b> O (log<sub>2</sub>n) </b> as we dispose half of the search space in every iteration, which also includes one comparison per iteration.

#### Applications

* Binary search can be implemented when the problem domain can be compared to a sorted list of elements, in which
the answer is to be found

##### Examples

1. Finding floor of square root of a given number.
2. Finding whether a function is monotonic in a given interval.
3. Finding upper and lower bounds of a number in the given array.

### 3. Ternary Search

* In this search technique, we dispose two third of the array for each iteration.
* This technique further reduces the time taken for the search, when compared to binary search.
* The array again needs to be sorted to implement the ternary search.

#### Implementation

```
int ternary_search(int low ,int high , int x)
{
    if(high >= low)
    {
        int mid1 = low  + (high - low)/3;
        int mid2 = high -  (high -low)/3;
        
        if( ar[mid1] == x )
            return mid1;
            
        if( ar[mid2] == x )
            return mid2;
            
        if( x < ar[mid1] )
            return ternary_search(l,mid1-1,x);
        else if( x > ar[mid2] )
            return ternary_search(mid2+1,r,x);
        else
            return ternary_search(mid1+1,mid2-1,x);
    }
    return -1;                                        // key not found
}
```

#### Time Complexity

The time complexity of Ternary Search is <b> O (log<sub>3</sub>n) </b>

#### Applications

* This concept is used in unimodal functions to determine the maximum or minimum value of that function. Unimodal functions are functions that, have a single highest value.

## Sort Techniques

### 1. Insertion Sort

* In this sort technique, given array is divided into sorted and unsorted parts and each element from unsorted
array is transferred to sorted array in a way that the sorted array is always sorted.

#### Implementation

```
void insertion_sort ( int A[ ] , int n) 
{
     for( int i = 0 ;i < n ; i++ ) {
    /*storing current element whose left side is checked for its 
             correct position .*/

      int temp = A[ i ];    
      int j = i;

       /* check whether the adjacent element in left side is greater or
            less than the current element. */

          while(  j > 0  && temp < A[ j -1]) {

           // moving the left side element to one position forward.
                A[ j ] = A[ j-1];   
                j= j - 1;

           }
         // moving current element to its  correct position.
           A[ j ] = temp;       
     }  
}
```

#### Time Complexity

The time complexity of insertion sort is <b> O ( N<sup>2</sup> ) </b>

### 2. Merge Sort

Merge Sort follows Divide-and-conquer algorithm i.e.,
* Divide the unsorted list into <b>N</b> sublists each containing 1 element
* Take adjacent pairs of two singleton lists and merge them to form a list of 2 elements.
<b>N</b> will convert into <b>N / 2</b> lists of size 2
* Repeat the process until a single sorted list is obtained.

#### Implementation

```
 void merge(int A[ ] , int start, int mid, int end) {
 //stores the starting position of both parts in temporary variables.
int p = start ,q = mid+1;

int Arr[end-start+1] , k=0;

for(int i = start ;i <= end ;i++) {
    if(p > mid)      //checks if first part comes to an end or not .
       Arr[ k++ ] = A[ q++] ;

   else if ( q > end)   //checks if second part comes to an end or not
       Arr[ k++ ] = A[ p++ ];

   else if( A[ p ] < A[ q ])     //checks which part has smaller element.
      Arr[ k++ ] = A[ p++ ];

   else
      Arr[ k++ ] = A[ q++];
 }
  for (int p=0 ; p< k ;p ++) {
   /* Now the real array has elements in sorted manner including both 
        parts.*/
     A[ start++ ] = Arr[ p ] ;                          
  }
}
```

#### Time Complexity

The Time Complexity of this technique is <b> O (NLogN) </b>

### 3. Quick Sort

* Quick sort is also based on the divide-and-conquer approach based on the idea of choosing one element as a pivot
element and partitioning the array around it such that: Left side of pivot contains all the elements that are
less than the pivot element Right side contains all elements greater than the pivot
* It reduces the space complexity and removes the use of the auxiliary array that is used in merge sort.
Selecting a random pivot in an array results in an improved time complexity in most of the cases.

#### Implementation

##### Partition

```
int partition ( int A[],int start ,int end) {
    int i = start + 1;
    int piv = A[start] ;            //make the first element as pivot element.
    for(int j =start + 1; j <= end ; j++ )  {
    /*rearrange the array by putting elements which are less than pivot
       on one side and which are greater that on other. */

          if ( A[ j ] < piv) {
                 swap (A[ i ],A [ j ]);
            i += 1;
        }
   }
   swap ( A[ start ] ,A[ i-1 ] ) ;  //put the pivot element in its proper place.
   return i-1;                      //return the position of the pivot
}
```

##### Quick Sort

```
void quick_sort ( int A[ ] ,int start , int end ) {
   if( start < end ) {
        //stores the position of pivot element
         int piv_pos = partition (A,start , end ) ;     
         quick_sort (A,start , piv_pos -1);    //sorts the left side of pivot.
         quick_sort ( A,piv_pos +1 , end) ; //sorts the right side of pivot.
   }
}
```

#### Time Complexity

The time complexity of this algorithm is <b> O (N<sup>2</sup>) </b>

## Resources

[Hacker Earth](https://www.hackerearth.com/practice/algorithms)

## Strength Attended - 42

## Speakers

* Rashed Mohammed - 3rd Year - rashedm.be20@uceou.edu
* Aghamarsh Varanasi - 3rd Year - aghamarshv.be20@uceou.edu
* K S K Vamsi - 3rd Year - vamsik.be20@uceou.edu
* Pavan Sai Kiran - 3rd Year - pavank1.be20@uceou.edu
