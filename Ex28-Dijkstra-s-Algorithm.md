# Ex28 Dijkstra’s Algorithm
## DATE:
## AIM:
To write a C Program to implement Dijkstra's Algorithm to find the shortest path

## Algorithm
1. Input: Read the number of vertices n, the adjacency matrix G, and the starting node u.
2. Setup: Create the cost matrix by copying G and replacing 0s with infinity (except diagonals), and initialize distance, predecessor, and visited arrays.
3. Main Loop: While there are unvisited nodes, select the unvisited node with the smallest distance, mark it visited, and update distances and predecessors of its unvisited neighbors.
4. Completion: Repeat until all nodes are visited.
5. Output: Print the shortest distances from the start node to each node along with the paths taken.

## Program:
```
/*
Program to implement Dijkstra's Algorithm 
Developed by: Varadaram SK
RegisterNumber:  212223040232
*/

#include<stdio.h>
#defineINFINITY9999
#define MAX10
voiddijkstra(int G[MAX][MAX],int n,intstartnode);
int main()
{
int G[MAX][MAX],i,j,n,u;
scanf("%d",&n);
for(i=0;i<n;i++)
for(j=0;j<n;j++)
scanf("%d",&G[i][j]);
scanf("%d",&u);
dijkstra(G,n,u);
return 0;
}
void dijkstra(int G[MAX][MAX],int n,intstartnode)
{
int cost[MAX][MAX],distance[MAX],pred[MAX];
int visited[MAX],count,mindistance,nextnode,i,j;
//pred[]storesthe predecessor ofeach node
//count givesthe number ofnodesseenso far
//createthecost matrix
for(i=0;i<n;i++)
for(j=0;j<n;j++)
if(G[i][j]==0)
cost[i][j]=INFINITY;
else
cost[i][j]=G[i][j];
//initializepred[],distance[] andvisited[]
for(i=0;i<n;i++)
{
distance[i]=cost[startnode][i];
pred[i]=startnode;
visited[i]=0;
}
distance[startnode]=0;
visited[startnode]=1;
count=1;
while(count<n-1)
{
mindistance=INFINITY;
//nextnode givesthe nodeat minimumdistance
for(i=0;i<n;i++)
if(distance[i]<mindistance&&!visited[i])
{
mindistance=distance[i];
nextnode=i;
}
//check ifa better pathexiststhroughnextnode
visited[nextnode]=1;
for(i=0;i<n;i++)
if(!visited[i])
if(mindistance+cost[nextnode][i]<distance[i])
{
distance[i]=mindistance+cost[nextnode][i];
pred[i]=nextnode;
}
count++;
}
//print the pathand distanceofeachnode
for(i=0;i<n;i++)
if(i!=startnode)
{
printf("Distanceofnode%d=%d\n",i,distance[i]);
printf("Path=%d",i);
j=i;
do{
j=pred[j];
printf("<-%d",j);
}while(j!=startnode);
}
}

```

## Output:


![image](https://github.com/user-attachments/assets/b9e8af83-ac78-4c69-8dd1-4b2ea8099284)


## Result:
Thus, the Program to implement Dijkstra's Algorithm to find the shortest path is implemented successfully.
