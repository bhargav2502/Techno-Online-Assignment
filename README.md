# Techno-Online-Assignment
//Program 1
#include <iostream>
#include <cmath>

void simplify_fraction(int num, int denom);

using namespace std;

int main()
{
 double number;
 cout << "Enter Number: ";
 cin >> number;

 double fractional_part = number - floor(number);

 for (double i = 0.1, j = 10;  ; i/=10, j*=10)
 {
  if ( fractional_part >= i )
  {
   simplify_fraction(number * j, j);
   break;
  }
 }
 return 0;
}


void simplify_fraction(int num, int denom)
{
 for (int i = denom; i>=2; i--)
 {
  if (num % i == 0 && denom % i == 0)
  {
   num = num/i;
   denom = denom/i;
  }
 }
 cout << "Fraction: ";
 if (denom == 1)
  cout << num;
 else
  cout << denom << "/" << num;
 cout << endl;
}

Program 2

 #include<iostream>
    using namespace std;

    void calculate_transpose(int matrix[5][5], int rows, int cols);
     void calculate_trace(int matrix[5][5], int rows, int cols);
    int main()
    {

    int matrix[5][5];
    int i,j,rows,cols;
    // Taking Input In Array

      cout<<"Enter Number of ROWS :";
      cin>>rows;

      cout<<"Enter Number Of COLS  :";
      cin>>cols;
       for( i=0;i<rows;i++){
           for( j=0;j<cols;j++)
           {
               cin>>matrix[i][j];
           }
          }

          cout<<"\n Matrix You Entered\n";

       for( i=0;i<rows;i++){
           for( j=0;j<cols;j++)
           {
               cout<<matrix[i][j]<<"     ";
           }
           cout<<endl;
          }
calculate_transpose(matrix,rows,cols);
calculate_trace(matrix,rows,cols);
   return 0;
    }

 void calculate_transpose(int matrix[5][5], int rows, int cols)
{   
    int i,j;
    int transpose_matrix[5][5];
    cout<<"\n\n\nTranspose of Entered Matrix\n";
       for(i=0;i<rows;i++){
           for( j=0;j<cols;j++)
           {
               transpose_matrix[j][i]=matrix[i][j];
           }
           cout<<endl;
          }

       for(i=0;i<cols;i++){
           for( j=0;j<rows;j++)
           {
               cout<<transpose_matrix[i][j]<<"   ";
           }
           cout<<endl;
          }
}
 void calculate_trace(int matrix[5][5], int rows, int cols)
{   
    int i,j,s=0;
    int transpose_matrix[5][5];
       for(i=0;i<rows;i++){
           for( j=0;j<cols;j++)
           {
               if(i==j)
               {
                   s=s+matrix[i][j];
               }
           }
           cout<<endl;
          }
cout<<"Trace Of Matrix is "<<s;
}
