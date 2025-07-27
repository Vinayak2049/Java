# You are given a 2D matrix mat[][] of size n x m. The task is to modify the matrix such that if mat[i][j] is 0, all the elements in the i-th row and j-th column are set to 0.

## Java Code:

class Solution {
    public void setMatrixZeroes(int[][] mat) {
        // code here
        int n = mat.length;
        int m = mat[0].length;
        boolean row[] = new boolean[n];
        boolean col[] = new boolean[m];
        for(int i = 0;i<n;i++){
            for(int j = 0; j<m;j++){
                if(mat[i][j]==0){
                    row[i]= true;
                    col[j]=true;
                }
            }
        }
        for(int i =0;i<n;i++){
            if(row[i]){
                for(int j=0;j<m;j++){
                    mat[i][j]=0;
                }
            }
        }
        for(int i = 0;i<m;i++){
            if(col[i]){
                for(int j= 0;j<n;j++){
                    mat[j][i]=0;
                }
            }
        }
    }
}
