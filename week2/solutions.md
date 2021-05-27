## Solution 1

#### Code

```
// CPP program for painter's partition problem
#include <iostream>
#include <climits>
using namespace std;

// return the maximum element from the array
int getMax(int arr[], int n)
{
    int max = INT_MIN;
    for (int i = 0; i < n; i++)
        if (arr[i] > max)
            max = arr[i];
    return max;
}

// return the sum of the elements in the array
int getSum(int arr[], int n)
{
    int total = 0;
    for (int i = 0; i < n; i++)
        total += arr[i];
    return total;
}

// find minimum required painters for given maxlen
// which is the maximum length a painter can paint
int numberOfPainters(int arr[], int n, int maxLen)
{
    int total = 0, numPainters = 1;

    for (int i = 0; i < n; i++)
    {
        total += arr[i];

        if (total > maxLen)
        {

            // for next count
            total = arr[i];
            numPainters++;
        }
    }

    return numPainters;
}

int partition(int arr[], int n, int k)
{
    int lo = getMax(arr, n);
    int hi = getSum(arr, n);

    while (lo < hi)
    {
        int mid = lo + (hi - lo) / 2;
        int requiredPainters = numberOfPainters(arr, n, mid);

        // find better optimum in lower half
        // here mid is included because we
        // may not get anything better
        if (requiredPainters <= k)
            hi = mid;

        // find better optimum in upper half
        // here mid is excluded because it gives
        // required Painters > k, which is invalid
        else
            lo = mid + 1;
    }

    // required
    return lo;
}

// driver function
int main()
{
    int arr[] = {1, 2, 3, 4, 5, 6, 7, 8, 9};
    int n = sizeof(arr) / sizeof(arr[0]);
    int k = 3;
    cout << partition(arr, n, k) << endl;
    return 0;
}

```

## Solution 2

#### Code

```
#include <stdio.h>

int main()
{
    int i, j, k, a[1000], b[1000], temp, temp1;
    scanf("%d\n", &i);
    for (j = 0; j < i; j++)
    {
        scanf("%d", &a[j]);

        for (j = 0; j < i; j++)
        {
            if (a[j] < a[j + 1])
            {
                temp = a[j];
                a[j] = a[j + 1];
                a[j + 1] = temp;
            }
        }
    }

    for (k = 0; k < i; k++)
        scanf("%d", &b[k]);

    for (k = 0; k < i; k++)
    {
        if (b[k] < b[k + 1])
        {
            temp1 = b[k];
            b[k] = b[k + 1];
            b[k + 1] = temp1;
        }
    }

    int flag = 0;

    for (int k = 0; k < i; k++)
    {
        if (b[k] > a[k])
        {
            printf("No");
            flag = 1;
            break;
        }

        if (flag)
            printf("Yes");
    }
}
```

## Solution 3

#### Code

```
#include <stdio.h>
#include <cstdlib>

int main()
{

    int t, n, *a, i, j, m, temp, sum, dif;
    scanf("%d", &t);

    while (t--)
    {
        sum = 0;
        dif = 0;
        scanf("%d %d", &n, &m);

        a = (int *)malloc(n * sizeof(int));

        for (i = 0; i < n; i++)
            scanf("%d", &a[i]);

        for (i = 0; i < n - 1; i++)
        {
            for (j = 0; j < n - i - 1; j++)
            {
                if (a[j] > a[j + 1])
                {
                    temp = a[j];
                    a[j] = a[j + 1];
                    a[j + 1] = temp;
                }
            }
        }

        for (i = 0; i < n - m; i++)
            sum = sum + a[i];

        for (i = m; i < n; i++)
            dif = dif + a[i];

        printf("%d\n", dif - sum);
    }
}

```

## Solution 4

#### Code

```
#include <bits/stdc++.h>
using namespace std;

int main()
{

    int arr[8];

    for (int i = 0; i < 8; i++)
        cin >> arr[i];

    int p;

    cin >> p;

    vector<pair<int, int>> v;

    for (int i = 0; i < p; i++)
    {
        int x, y;
        cin >> x >> y;
        v.push_back(make_pair(x, y));
    }

    int maxmoney = -9999;

    for (int i = 0; i < (1 << 9); i++)
    {
        int flag = 0;

        for (pair<int, int> j : v)
        {
            if ((i & (1 << (j.first - 1))) && (i & ((1 << j.second - 1))))
            {
                flag = 1;
                break;
            }
        }

        if (flag == 0)
        {
            // cout<<bitconfig(i)<<"-----"<<endl;
            int sum = 0;
            for (int k = 0; k <= 7; k++)
            {
                if (i & (1 << k))
                    sum += arr[k];
            }

            if (sum > maxmoney)
            {
                maxmoney = sum;
                sum = 0;
            }
        }
    }

    cout << maxmoney << endl;
}
```

## Solution 5

#### Code

```
#include <bits/stdc++.h>
using namespace std;
typedef long long int lli;

int main()
{

    int t;
    cin >> t;

    while (t)
    {

        lli n;
        cin >> n;

        lli a[n];

        lli x = 0;

        for (lli i = 0; i < n; i++)
        {
            cin >> a[i];
            x = x ^ a[i];
        }

        cout << 2 * x << endl;

        t--;
    }
}
```

## Solution 6

#### Code

```
#include <bits/stdc++.h>
using namespace std;

void findNumbers(int arr[], int n)
{
    int num[n];

    int b_minus_a = arr[n - 1] - arr[1];

    num[1] = (arr[0] + b_minus_a) / 2;

    num[0] = arr[0] - num[1];

    for (int i = 1; i <= (n - 2); i++)
        num[i + 1] = arr[i] - num[0];

    cout << "Numbers are: ";
    for (int i = 0; i < n; i++)
        cout << num[i] << " ";
}
//Driver program
int main()
{
    int arr[] = {13, 10, 14, 9, 17, 21, 16, 18, 13, 17};
    int n = 5;
    findNumbers(arr, n);
    return 0;
}
```
