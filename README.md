# Algorithms-Analysis
here are the codes for algo analysis 
//String matching function
#include <iostream>
#include<algorithm>
using namespace std;

int stringm(string t, string pattern) {
	bool flag;
	for (int i = 1; i <= t.length() - pattern.length() + 1; i++) { //external for for the sentence looping
		flag = true;
		for (int j = 1; j <= pattern.length() && flag == true; j++) { //inner for for pattern looping and comparing
			if ( pattern[j]!= t[j+i - 1])
				flag = false;
		}
		if (flag == true)
			return i;
	}	
	return 0;
}

int main(){
	string n = "hi my name is maya";
	string f = "maya";
	cout << stringm(n, f); //returns 15 here, the position of first letter in the right match
}
