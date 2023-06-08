Leetcode- https://leetcode.com/problems/set-matrix-zeroes/

***Brute Force- T(n)=(n*m)*(n+m)+(n*m)=>O(n^3)***
markRow(i)
{
  for(j=0 to m)
  {
    if(matrix[i][j]!=0)
      matrix[i][j]=-1;
  }
}
markCol(j)
{
  for(i=0 to n)
  {
    if(matrix[i][j]!=0)
      matrix[i][j]=-1;
  }
}
for(i=0 to n)
{
  for(j=0 to m)
  {
    if(matrix[i][j]==0)
    {
      markRow(i);
      markCol(j);
    }
  }
}
for(i=0 to n)
{
  for(j=0 to m)
  { if(matrix[i][j]==-1)
      matrix[i][j]=0;
  }
}
***Better - T(n)=(n*m)=>O(n^2)***
using 2 new array (rowArr,colArr)
initially filled with 0 if we see 0 in mtrix then we convert that 2 newly created array ith and jth index to 0=>1;
if(rowArr[i]||colArr[j])
  matrix[i][j]=0
