# To-calculate-power-of-number#include<iostream> 
using namespace std; 
class Number {
  private:
    double base;
    int power;
  public:
    Number(double b, int p) {
      base = b;
      power = p;
    }
    friend double Power(Number n);
    friend double Recurse(Number n);
};
double Power(Number n) 
{ 
  double ans=1; 
  if(n.power==0) 
    return ans; 
  else 
  {   
    for(int i=1;i<=n.power;i++) 
    { 
      ans=ans*n.base; 
    } 
    return ans; 
  } 
} 
double Recurse(Number n) 
{ 
  if(n.power==0) 
  { 
    return 1; 
  } 
  if(n.power==1) 
  { 
    return n.base; 
  } 
  else 
  { 
    return (n.base*Recurse(Number(n.base,n.power-1))); 
  } 
} 

int main() 
{ 
  double n; 
  int p; 
  cout<<"Enter the base value (power is default set to 2) :"; 
  cin>>n; 
  Number num1(n,2);
  cout<<"Power of number is : "<<Power(num1)<<endl; 
  cout<<"\nEnter the base value and power :"; 
  cin>>n>>p; 
  Number num2(n,p);
  cout<<"Power of number is : "<<Power(num2)<<endl; 
  cout<<"\nEnter the base value and power :"; 
  cin>>n>>p; 
  Number num3(n,p);
  cout<<"Using Recursion, Power of number is : "<<Recurse(num3)<<endl; 
  return 0; 
} 
