# Assignment 2

## Question 1

You have to paint N boards of length {A<sub>0</sub>, A<sub>1</sub>, ... ,A<sub>n-1</sub>}.
There are K painters available and you are also given how much time a painter takes to paint
1 unit of board. You have to get this job done as soon as possible under the constrraints that
any painter will only paint contiguous sections of board.

* 2 painters cannot share a board to paint. That is to say, a board cannot be painted partially
by one painter and partially by another

* A painter will only paint contiguous boards, which means a configuration where painter 1 paints
board 1 and 3 but not 2 is invalid.

Return the ans % 10000003

### Input:

K : Number of Painters

T : Time taken by painter to paint 1 unit of board

L : A list which will represent length of each board

### Output:

Return the minimum time to paint all boards % 10000003

## Question 2

A new deadly virus has infected large population of a planet. A brilliant scientist has discovered
a new strain of virus which can cure this disease. Vaccine produced from this virus has various
strength depending on midichlorians count. A person is cured only if midichlorians count in vaccine
batch is more than the midichlorians count in the person. A doctor recieves a new set of report
which contains midichlorians count of each infected patient. Practo stores all vaccine doctor has
and their midichlorians count. You need to determine if doctor can save all patients with the
vaccine he has. The number of vaccines and patients are equal.

### Input:

First line contains the number of vaccines N. Second line contains N integers, which are strength
of vaccines. Third line contains N integers, which are midichlorians count of patients.

### Output:

Print a single line containing 'Yes' or 'No'.

### Contraints

* 1 &lt; N &lt; 10
* Strength of vaccines and midichlorians count of patients fit in integers

### Example

#### Input

```
5
123 146 454 542 456
100 328 248 689 200
```

#### Output

`No`

## Question 3

Coders here is a simple task for you, You are given an array <b> a </b> of size <b>N</b> and an integer 
<b>M</b>.

Your task is to calculate the difference between maximum sum and minimum sum of <b> N - M </b> 
elements of the given array.

### Constraints

* 1 &le; t &le; 10
* 1 &le; n &le; 1000
* 1 &le; a [ i ] &le; 1000

### Input

* First line contains an integer <b> T </b> denoting the number of test cases.
* First line of every test case contains two integers <b> N </b> and <b> M</b>.
* Next line contains <b> N </b> space separated integers denoting the elements of the array <b> a</b>.

### Output

For every test case print your answer in a new line.

### Example 

#### Input 

```
1
5 1
1 2 3 4 5
```

#### Output

`4`

### Explanation

<b> M </b> is 1 and <b> N </b> is 5, so you have to calculate maximum and minimum sum 
using  ( 5 - 1 ) = 4 elements.

Maximum sum using 4 elements would be ( 2 + 3 + 4 + 5) = 14

Minimum sum using the 4 elements would be ( 1 + 2 + 3 + 4 ) = 10

Difference will be 14 - 10 = 4

## Question 4

8 friends decided to plan a trip to Goa and agreed on pooling money together for whole trip expenses.
Now since every group has some internal politics going on, same applies here also - 2 Members that are
having a cold war between them won't go to the trip if the other one is going. But since thet want to enjoy 
a lavish party , they want to maximize the pooled money. So, for this task they've chosen a friend Bhaskar
to solve this problem ( He's good at money matters ). Your task is to help Bhaskar achieve the maximum pooled money.

### Input

* First Line will contain 8 space seperated integers denoting the money contributed by each member in order.
* The next line will contain the total number of pairs having a cold war in between them. Let us denote this by P.
* The next P lines will contain 2 numbers seperated by a space showing the members having a cold war.
Numbers used to denote members will be ( 1 - 8 ) for each 8 members.

### Output

Output will give the maximum amout of money that can be pooled.

### Example

#### Input

```
3 14 5 2 3 4 1 9 
4
1 2
2 3
4 5
7 8
```

#### Output

`30`

## Question 5

Given a sequence <b>A</b> with size <b>N</b>, generate a new sequence <b>B</b> with size <b>N<sup>2</sup></b>
using the following formula and calculate <b>XOR(B)</b>

<p align='center'><b>B<sub> iN + j + 1</sub> = ( A<sub>i + 1</sub> + A<sub>j + 1</sub> ) ∀ 0 ≤ i , j < N</b></p>
  
<p align='center'><b> XOR(a<sub>1..n</sub>) = a<sub>1</sub> ⊕ a<sub>2</sub> ⊕ ⋯ ⊕ a<sub>n</sub> </b></p>

### Input

* The first line of the input contains a single integer <b>T</b> denoting the number of test cases. The description of
<b>T</b> test cases follows.
* The first line of each test case contains a single integer <b>N</b>.
* The second line contains N space-separated integers  <b>A<sub>1</sub>, A<sub>2</sub>, … , A<sub>N</sub></b>

### Output

For each test case, print a single line containing one integer — the answer to the problem.

### Constraints

* 1 &le; <b>T</b> &le; 100
* 1 &le; <b>N</b> &le; 10<sup>5</sup>
* 2<sup>0</sup> &le; <b>A<sub>i</sub></b> &lt; 2<sup>30</sup> for each valid i

### Example

#### Input

```
1
2
1 2
```

#### Output

`6`

### Explanation

The sequence B is <b>{ A<sub>1</sub> + A<sub>1</sub> , A<sub>1</sub> + A<sub>2</sub> , A<sub>2</sub> + A<sub>1</sub> , 
A<sub>2</sub> + A<sub>2</sub> } = { 2, 3, 3, 4 }</b>.

The XOR of its elements is <b>B<sub>1</sub> ⊕ B<sub>2</sub> ⊕ B<sub>3</sub> ⊕ B<sub>4</sub> = 6</b>.

## Question 6

Given a pair-sum array and size of the original array (n), construct the original array.

A pair-sum array for an array is the array that contains sum of all pairs in ordered form.
For example pair-sum array for arr[] = {6, 8, 3, 4} is {14, 9, 10, 11, 12, 7}.

In general, pair-sum array for arr[0..n-1] is { arr[0]+arr[1], arr[0]+arr[2], ……., 
arr[1]+arr[2], arr[1]+arr[3], ……., arr[2]+arr[3], arr[2]+arr[4], …., arr[n-2]+arr[n-1] }.

### Input

* First line contains <b>T</b> denoting the number of Test cases.
* Next <b>T</b> lines each contains the size of original array <b>N</b> and an array of pair-sum vlaues respectively.

### Output

* For every test case output the original array of size <b>N</b>

### Example

#### Input

```
1
5 15 13 11 10 12 10 9 8 7 5
```

#### Output

```
8 7 5 3 2
```
