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
