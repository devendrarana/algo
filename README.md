#include <stdio.h>
#include<bits/stdc++.h>
using namespace std;
void print(int** edges,int n,int j,bool* visited)
{
    std::cout << j << std::endl;
    visited[j]=true;
    for(int i=0;i<n;i++)
    {
        if(i==j)
        continue;
        if(visited[i])
            continue;
        if(edges[j][i])
        print(edges,n,i,visited);
    }
}
int main() {
	//code
	int n,e;
	cin>>n>>e;
	int **edges=new int*[n];
	for(int i=0;i<n;i++)
	{
	    edges[i]=new int[n];
	    for(int j=0;j<n;j++)
	    {
	        edges[i][j]=0;
	    }
	}
	for(int i=0;i<e;i++)
	{
	    int v1,v2;
	    cin>>v1>>v2;
	    edges[v1][v2]=1;
	    edges[v2][v1]=1;
	}
	bool *visited=new bool[n];
	for(int i=0;i<n;i++)
	visited[i]=false;
	print(edges,n,0,visited);
	return 0;
	
}
