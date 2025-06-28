
## Input/ Output

```c++
#include<iostream>
#include<math.h>
#include <string>

using namespace std;

int main(){
	std::cout<<"hello world"<<std::endl<<"asdas";
	int x;
	cout<<"type value of x \n";
	cin >>x;
	cout<<"value of x"<<x;
	return 0;
}


```


>  # include<bits/stdc++.h>

Includes all cpp modules


## Datatypes

```c++
//int
//10^9
int x=10;
//longer
//10^12
long y=1555425233;
//10^12
long long z=2214346547534534543;

//FLoat
float a=2.3
double b=2.23432423

//String/Char

string s1,s2;
cin>>s1>>s2;
cout <<s1<<" "<<s2; 

//taking in single string
string s3;
getLine(cin,s3);
cout<<str;

char ch='a';
cout<<ch;



```


## Conditionals

```cpp
if(){}
else if(){}
else{}

//uses &&

//Switch

switch (x){
case 1:
	cout<<"case1";
	break;
case2:
	cout<<"case2";
	break
	
}
default:
	cout<<"default";
	break;

//Continue and break
```

## Arrays and Strings

```cpp
int a[5]={1,2,3,3,4,7}

//2D
int a[2][3]={{1,2,3},{12,2,3}}


string s="abc";
cout<<s[1]<<s.size();

```


## For loops /While Loops

```cpp

#for loop
for (i=0;i<=500;i++){
cout<<i;

}
#while loop
i=0
while(i<2){
cout<<i;
i+=1;
}

```

# Functions

```cpp

//void,other datatype

void printname(){
cout<<"hello";
}
void printnameN(string name){
cout<<"hello";
}


//int

//pass  by value
int sum(int a){
return a*a;

}

//max-min fns



//pass by reference


int takeRef(string &s){
cout<<s;
return 0; 
}
a="asd"
takeRef(a);



```