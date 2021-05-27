# WEEK 6 - Time Complexity , Linked List and Greedy Approach to Problem Solving

### The Following topics where discussed in the 6<sup>th</sup> Session of CodeGarage

* Time Complexity and Big-O notation.
* Linked Lists and comparision with arrays.
* Greedy Algorithms.

## Time Complexity

<p> Time complexity deals with estimating the time taken by a program or function to complete execution. Time complexity is generally expressed in <b> Big-O </b> notation.
  
### The BIG-O notation
<p>This is a mathematical representation of the upper limit of the scaling factor for an algorithm and is written as <b>O(Nn)</b>, with "N" being the number of inputs and "n" being the number of looping expressions.</p>

For example , consider the following piece of C++ code
```
int arr [] = {1,2,3,4,5};

for(int i=0;i<arr.lenght;i++)
{
  for(int j=0;j<arr.length;j++)
   {  
       ----------
       statements. 
       ----------
   }
}      
```

In the above example , the input is five numbers and the for loop is repeated twice. Hence the Time Complexity of the above piece of code is <b>O(N<sup>2</sup>)</b>.

Further, as discussed in the second session, the Time Complexity of <i>Linear search</i> is <b>O(N)</b>.Whereas the Time Complexity of <i>Binary Search </i> is <b>O(log N)</b>.

#### Properties of BIG-O notation

* If f<sub>1</sub> = <b>O(g<sub>1</sub>)</b> and f<sub>2</sub> = <b>O(g<sub>2</sub>)</b> then , f<sub>1</sub>*f<sub>2</sub>= <b>O(g<sub>1</sub> g<sub>2</sub>)</b>.
* If f<sub>1</sub> = <b>O(g<sub>1</sub>)</b> and f<sub>2</sub> = <b>O(g<sub>2</sub>)</b> then , f<sub>1</sub> + f<sub>2</sub>= <b>O(g<sub>1</sub>) + O(g<sub>2</sub>)</b>.
*  If f<sub>1</sub> = <b>O(g<sub>1</sub>)</b> then , k * f<sub>1</sub> = <b>O(k * g<sub>1</sub>)</b> = <b>O(g<sub>1</sub>)</b>.
* Consider that the time complexity calculated for a particular algorithm turned out to be polynomial in nature i.e, 
f = a<sub>1</sub>x<sup>n</sup>+a<sub>2</sub>x<sup>n-1</sup>+....+a<sub>n-1</sub>x+a<sub>n</sub>, 
then O(f) = O(a<sub>1</sub>x<sup>n</sup>+a<sub>2</sub>x<sup>n-1</sup>+....+a<sub>n-1</sub>x+a<sub>n</sub>) = O(a<sub>1</sub>x<sup>n</sup>) = <b>O(x<sup>n</sup>)</b>.


## Strength Attended - 20

## Speakers

* Pavan Sai Kiran - 3rd Year - pavank1.be20@uceou.edu
* Snehish Dasari - 3rd Year - snehishd.be20@uceou.edu
