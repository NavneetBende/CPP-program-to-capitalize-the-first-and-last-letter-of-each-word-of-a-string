Capitalizing first and last letter of each word of a string.
In this article we will learn how to code a C++ program to capitalize the first and last letter of each word of a string. First we  will convert first and last character present in the string to uppercase.Then we have to find out words present in the string.

Group of letters separated by a space is considered as a word , so we will have have to find out the space and then we can convert the letters present before and after space to upper case. To convert the letters to upper case we will be using a function “toupper()”. The “toupper()” function is present in “ctype.h” header file so we also need to include the same.

Capitalize The First and Last Letter in java
We need to chaptalize the first and last letter of each word of a string, we can either use toupper() function or we can do the same by typecasting.

Example
Lets take example to understand this if the input string is :- "Prep insta" we need to capitalize first and last letter of each word of a string. The output here will be "PreP InstA"
Algorithm:
Initialize the variables.
Accept the input.
Calculate the length of input.
Initialize a for loop. 
Convert first and last index of the string to uppercase using toupper() function.
Check for space.
If space found convert the element present at index before space and after space to uppercase using the same function.
Terminate for loop
Print result.
C++ programming code to capitalize the first and last letter of each word of a string
Run
#include <iostream>
#include <ctype.h>
#include <string.h>
using namespace std;

int main()
{

//Initializing variables.
char str[100]="Prep insta";
int length = 0;
//Calculating length.
length = strlen(str);

for(int i=0;i<length;i++)
{
if(i==0||i==(length-1)) //Converting character at first and last index to uppercase.
{
str[i]=toupper(str[i]);
}
else if(str[i]==' ')//Converting characters present before and after space to uppercase.
{
str[i-1]=toupper(str[i-1]);
str[i+1]=toupper(str[i+1]);
}
}

cout<<"String after capitalizing first and last letter of each word:\n"<<str;
return 0;
}
Output:
String after capitalizing first and last letter of each word: 
PreP InstA
Note
The time complexity of above method is o(n) as we are iterating over the string once in the for loop
Method 2
Run
#include<bits/stdc++.h>
using namespace std;

string FirstAndLast(string str)
{
    // Create an equivalent string of the given string
    string ch = str;
    for (int i = 0; i < ch.length(); i++)
    {
        // k stores index of first character and i is going to store index of last character.
        int k = i;
        while (i < ch.length() && ch[i] != ' ')            i++;        // Check if the character is a small letter If yes, then Capitalise        ch[k] = (char)(ch[k] >= 'a' && ch[k] <= 'z'                        ? ((int)ch[k] - 32)                        : (int)ch[k]);        ch[i - 1] = (char)(ch[i - 1] >= 'a' && ch[i - 1] <= 'z'
                            ? ((int)ch[i - 1] - 32)
                            : (int)ch[i - 1]);
    }
    return ch;
}

// Main code
int main()
{
    string str = "prep insta";
    cout << "Input string : " << str << "\n";
    cout <<"String after capitalize the first and last letter of each word: "<<FirstAndLast(str);
}
Output
Input string : prep insta
String after capitalize the first and last letter of each word: PreP InstA
