# PigLatin-2
PigLatin In C
// C# program to encode a word to a 
// Pig Latin. 
using System; 

class GFG { 
	
	static bool isVowel(char c) 
	{ 
		return (c == 'A' || c == 'E' || 
				c == 'I' || c == 'O' || 
				c == 'U' || c == 'a' || 
				c == 'e' || c == 'i' || 
				c == 'o' || c == 'u'); 
	} 
	
	static string pigLatin(string s) 
	{ 
	
		// the index of the first 
		// vowel is stored. 
		int len = s.Length; 
		int index = -1; 
		for (int i = 0; i < len; i++) 
		{ 
			if (isVowel(s[i])) 
			{ 
				index = i; 
				break; 
			} 
		} 
	
		// Pig Latin is possible only 
		// if vowels is present 
		if (index == -1) 
			return "-1"; 
	
		// Take all characters after 
		// index (including index). 
		// Append all characters which 
		// are before index. Finally 
		// append "ay" 
		return s.Substring(index) + 
			s.Substring(0, index) 
							+ "ay"; 
	} 
	
	// Driver code 
	public static void Main() 
	{ 
		string str = pigLatin("graphic"); 
		
		if (str == "-1") 
			Console.WriteLine("No vowels"
					+ "found. Pig Latin"
					+ " not possible"); 
		else
			Console.WriteLine(str); 
	} 
} 

// This code is contributed by vt_m. 
