# A beautiful matrix is defined as a square matrix in which the sum of elements in every row and every column is equal. Given a square matrix mat[][], your task is to determine the minimum number of operations required to make the matrix beautiful.In one operation, you are allowed to increment the value of any single cell by 1.

## Java Code:
class Solution {
    public static int balanceSums(int[][] mat) {
          int Total = 0;
        int maxrsum = 0;
        int maxcsum = 0;
        int len = mat.length;
        for(int i = 0;i<len;i++){
            int rsum = 0;
            int csum = 0;
            for(int j=0;j<len;j++){
                rsum+=mat[i][j];
                csum+=mat[j][i];
                Total+=mat[i][j];
            }
            maxrsum = Math.max(rsum,maxrsum);
            maxcsum = Math.max(csum,maxcsum);
        }
        int max = Math.max(maxrsum,maxcsum);
        return (max*len)-Total;
    }
}
