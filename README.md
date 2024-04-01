Program to Count the Number of vowels
Program to Count the Number of vowels we’re going to check how many vowels are present in a given String . There are five vowels in English vocabulary, they are – ‘a’, ‘e’, ‘i’, ‘o’, ‘u’.

A String is entered in this case is “s” variable So, we need to check how many vowels are present in given string

For Example, in the string prepinsta then in that case then vowesl are 3 (a,e,i)

Program count the number of vowels in a string
Algorithm
Take a String input from user store in variable called “s” 
Convert String to char array using toCharArray() 
Start for loop from i=0 to i<s.length()
Check condition if s.charAt(i)==’a’ or s.charAt(i)==’e’ or s.charAt(i)==’i’ or s.charAt(i)==’o’ or s.charAt(i)==’o’ to increment vowel++
Take else if part s.charAt(i)>=’a’ && s.charAt(i)<=’z’ to increment consonant ++
Take another else if part s.charAt(i)>=’1′ && s.charAt(i)<=’9′ to increment digit++
Take another else if part s.charAt(i)==’ ‘ to increment whitespaces++
Take else part to increment symbols++
Code in Java
Run
// Write a program to calculate the number of vowels present in the string in java
import java.util.Scanner;

public class  Main{

	public static void main(String[] args) {
		String s = "prepinsta";
		char[] c = s.toCharArray();
		int vowel=0;
		
		for (int i = 0; i < s.length(); i++) { 
            if(s.charAt(i)=='a' || s.charAt(i)=='e' || s.charAt(i)=='i' || s.charAt(i)=='o' || s.charAt(i)=='u') 
                vowel++; 
		}
  
	System.out.println("Vowels: " + vowel);
    }
}
Output
Vowels: 3
Note
The time complexity of above code in O(n) as in the code we are looping over the sting once
Method 2
First take the string input in a string variable and make a function countVowels(str,str.length())
if the value of n that is (length of string) is 1 then we will return . (This is the base case)
if the size of the string is not 1 then countVowels(str, n-1) + isVowel(str[n-1])
Here isVowel(str[n-1]) will be called if the character is vowel then this will return 1 otherwise 0
Run
public class Main {
    static int isVowel(char ch) {
        ch = Character.toUpperCase(ch);
        if (ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U')
            return 1;
        else
            return 0;
    }
    // to count total number of vowel from 0 to n
    static int countVowels(String str, int n) {
        if (n == 1) return isVowel(str.charAt(n - 1));
        return countVowels(str, n - 1) + isVowel(str.charAt(n - 1));
    }
    // Main Calling Function
    public
    static void main(String args[]) {
        // string object
        String str = "prepinsta";

    // Total numbers of Vowel
    System.out.print("Total number of Vowel = ");
    System.out.println(countVowels(str, str.length()));
  }
}
Output
Total number of Vowel = 3
