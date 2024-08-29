# Experiment-8
### AIM
To create a matrix by taking inputs from user and doing operations on it.

### Software Used
VS Code

### Problem Statement
1.) To make a matrix by taking number of rows and column from user.

2.) To make a matrix by taking number of rows and column from user and do their addition and multiplication.

3.) To add the diagonal elements of the matrix.

4.) To make the transpose of a matrix.

## Theory
Arrays are a way to store a list of items of the same type in a single structure. Imagine them as a row of boxes, where each box holds a value. These boxes are stored next to each other in memory, which allows us to quickly access any item by its position (or index). Arrays can be simple, with just one row (one-dimensional), or more complex, with multiple rows and columns (multidimensional).Matrices are a specific kind of two-dimensional array, like a grid or table, where numbers are arranged in rows and columns. 

### Matrix Addition
You can add two matrices if they have the same dimensions. To add them, you add the corresponding elements.

### Matrix Multiplication
To multiply two matrices, the number of columns in the first matrix must be equal to the number of rows in the second matrix. Each element of the result is calculated as the sum of products of corresponding elements from the rows of the first matrix and columns of the second matrix.

### Diagonal Elements
In a square matrix (same number of rows and columns), the main diagonal runs from the top-left to bottom-right (e.g., 1, 5, 9 in the matrix above). The secondary diagonal runs from the top-right to bottom-left.

### Transpose of a Matrix
The transpose of a matrix is obtained by swapping rows with columns.

## Program Codes
1. USER DEFINED MATRIX
``` javascript
//Mohit Singh Rawat
//23070123086
#include<iostream>
using namespace std;
int main()
{
    int r,c , i , j;
    cout<< " Enter number of rows: ";
    cin>> r ;
    cout<<" Enter number of columns: ";
    cin>> c;
    int arr[r][c];
    for (i=0 ; i < r ; i++)
    {
        for(j = 0 ; j < c ; j++)
        {
            cout<< "Enter elements ("<<i<< "," <<j<<"): "  ;
            cin>>arr[i][j];
        }
    }
for (i=0 ; i<r ; i++)
{
    for(j = 0; j< c ; j++ )
    { 
        cout<< " "<< arr[i][j];
    }
    cout<<endl;
}

}
```

2.MATRIX OPERATIONS
``` javascript
//Mohit Singh Rawat
//23070123086
#include<iostream>
using namespace std;
int main()
{
    int a,b,c,d , i , j ,k , e, f;
    cout<< " Enter matrix-1 rows: ";
    cin>> a ;
    cout<<" Enter matrix-1 columns: ";
    cin>> b;
    cout<< " Enter matrix-2 rows: ";
    cin>> c ;
    cout<<" Enter matrix-2 columns: ";
    cin>> d;

    int mat1[a][b];
    int mat2[c][d];
    int add [a][b];
    int mul [a][d];
    
 if ( a !=c || b!=d)
    {
        cout<< "Matrix cannot be added as dimension do not match."<<endl;
    }
    else
{for (i=0 ; i < a ; i++)
    {
        for(j = 0 ; j < b ; j++)
        {
            cout<< "Enter elements ("<<i<< "," <<j<<"): "  ;
            cin>>mat1[i][j];
        }
    }


    for (i=0 ; i < c ; i++)
    {
        for(j = 0 ; j < d ; j++)
        {
            cout<< "Enter elements ("<<i<< "," <<j<<"): "  ;
            cin>>mat2[i][j];
        }
    }

for (i=0 ; i < a ; i++)
    {
        for(j = 0 ; j < b ; j++)
        {
            add[i][j] = mat1[i][j] + mat2 [i][j];

        }
    }
cout<<"SUM OF MATRIX: "<<endl;
for (i=0 ; i< a ; i++)
{
    for(j = 0; j< b ; j++ )
    { 
        cout<< " " <<add[i][j];
    }
    cout<<endl;
}}

    if( b != c)
{
    cout<< "Matrices cannot be multiplied as dimensions do not match." <<endl;
    return 1;
}
for(i = 0; i<a ; i++)
{
    for( j = 0; j<d ; j++)
    {
        mul[i][j] = 0;
        for( k=0; k<b ; k++)
        {
            mul[i][j] += mat1[i][k] * mat2[k][j];
        }
    }
}
cout << "PRODUCT OF MATRIX: "<<endl;
for (i=0 ; i< a ; i++)
{
    for(j = 0; j< b ; j++ )
    { 
        cout<< " " <<mul[i][j];
    }
    cout<<endl;
}
}
```

3.MATRIX DIAGONAL SUM
``` javascript
//Mohit Singh Rawat
//23070123086
#include<iostream>
using namespace std;
int main()

{ int i,j, r1, c1, sum=0, sum2=0;
 cout<<"Enter number of rows and cloumns of first matrix: ";
cin>>r1>>c1;
int mat1[r1][c1];

if(r1!=c1)
{
    cout<<"ONLY SQUARE MATRICES ARE TO BE ENTERED!"<<endl;
}
else
{
for(i=0; i<r1; i++)
{
    for (j=0 ; j<c1 ; j++)
    {
        cout<<"Enter elements ("<<i<< "," <<j<<"): ";
        cin>>mat1[i][j];
    }
}


for(i=0; i<r1; i++)
{
    for (j=0 ; j<c1 ; j++)
    { if(i==j)
    {
        sum +=mat1[i][j];
    }
    if (i+j == r1-1)
    sum2 += mat1[i][j];
    }
    }
    cout<< "Sum of diagoal elements is: "<<sum<<endl;
    cout<<"Sum of diagonal elements is: "<<sum2<<endl;
}

}
```

4. MATRIX TRANSPOSE
``` javascipt
//Mohit Singh Rawat
//23070123086
#include<iostream>
using namespace std;
int main()
{
    int r,c , i , j;
    cout<< " Enter number of rows: ";
    cin>> r;
    cout<<" Enter number of columns: ";
    cin>> c;
    int arr[r][c], arr2[c][r];
    for (i=0 ; i < r ; i++)
    {
        for(j = 0 ; j < c ; j++)
        {
            cout<< "Enter elements ("<<i<< "," <<j<<"): "  ;
            cin>>arr[i][j];
        }
    }
for (i=0 ; i<r ; i++)
{
    for(j = 0; j< c ; j++ )
    { 
        cout<< "  "<< arr[i][j];
    }
    cout<<endl;
}
for (i=0 ; i<c ; i++)
{
    for(j = 0; j< r ; j++ )
    { 
        arr2[i][j]= arr[j][i];
    }

    
}
cout<<endl;
for (i=0 ; i<c ; i++)
{
    for(j = 0; j< r ; j++ )
    { 
        cout<< " "<< arr2[i][j];
    }
    cout<<endl;
}

}
```

## Outputs
1. USER DEFINED MATRIX
   <img width="311" alt="Screenshot 2024-08-29 at 3 49 24 PM" src="https://github.com/user-attachments/assets/3227b17b-8d02-43a1-acd0-f529be97cf8c">
   
2. MATRIX OPERATIONS
   <img width="296" alt="Screenshot 2024-08-29 at 3 53 50 PM" src="https://github.com/user-attachments/assets/0b4e4547-d4a8-442a-8ab3-cf432c94170a">
   
3. MATRIX DIAGONAL SUM
   <img width="448" alt="Screenshot 2024-08-29 at 3 56 40 PM" src="https://github.com/user-attachments/assets/eac067f1-2202-4b30-b14a-ef1f8f89e6a8">

4. MATRIX TRANSPOSE
   <img width="315" alt="Screenshot 2024-08-29 at 3 58 31 PM" src="https://github.com/user-attachments/assets/d31bb7b0-bb95-46c2-8596-83a45d4ce2f1">
  

### Conclusion
Learnt How To:- 
Create a Matrix: Collects rows and columns of data from user input.
Add Matrices: Adds corresponding elements of two matrices.
Multiply Matrices: Computes the product of two matrices (when dimensions match).
Diagonal Sum: Calculates the sums of the main and secondary diagonals of a matrix.
Transpose Matrix: Swaps rows and columns of a matrix.



