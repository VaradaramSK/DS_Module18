# Ex29 Travelling Salesman Problem
## DATE:
## AIM:
To write a C Program to implement Travelling Salesman Problem for finding shortest path.
## Algorithm
1. Input: Read the number of cities n and the adjacency matrix a representing distances.
2. Setup: Initialize the visited array and start the journey from city 0 (print it).
3. Route Selection: In the mincost function, repeatedly use the least function to find and move to the nearest unvisited city.
4. Completion: Once all cities are visited, return to city 0 and complete the tour.
5. Output: Print the minimum cost of visiting all cities.
## Program:
```
/*
Program to implement Travelling Salesman Problem for finding shortest path
Developed by: Varadaram SK
RegisterNumber: 212223040232
*/
#include<stdio.h>
int a[10][10],visited[10],n,cost=0;
voidget()
{
int i,j;
scanf("%d",&n);
for(i=0;i<n;i++)
{
for( j=0;j < n;j++)
scanf("%d",&a[i][j]);
visited[i]=0;
}
}
void mincost(int city)
{
int ncity;
int least(int);
visited[city]=1;
printf("%d-->",city+1);
ncity=least(city);
if(ncity==999)
{
ncity=0;
printf("%d",ncity+1);
cost+=a[city][ncity];
return;
}
mincost(ncity);
}
int least(int c)
{
int i,nc=999;
int min=999,kmin;
for(i=0;i< n;i++)
{
if((a[c][i]!=0)&&(visited[i]==0))
if(a[c][i] < min)
{
}
}
}
if(min!=999)
cost+=kmin;
return nc;
min=a[i][0]+a[c][i];
kmin=a[c][i];
nc=i;
voidput()
{
printf("\n\nMinimum cost:%d",cost);
}
int main()
{
get();
mincost(0);
put();
return 0;
}
```

## Output:


![image](https://github.com/user-attachments/assets/70ddf21c-2986-4d1b-ba35-cfa3c803ebd6)


## Result:
Thus, the C program to implement Travelling Salesman Problem for finding shortest path is implemented successfully.
