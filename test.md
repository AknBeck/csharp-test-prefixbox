# Test

## C# questions

- What is a namespace? What is it good for and how do you define a namespace?
It is the space where are your clases, objects, enums, ect.

- What is a constructor? When is it executed?
Constructor is necesarry for creating new object of entity where the constructor is.

- How do you implement inheritance in C#?
 for example public class World >: Universe<
 
- How do you prevent someone to inherit from a class?
by using private protected

- What is a readonly variable? Where you can assign value to readonly variables?
Variable where you are not allowed to set anything. Only through constructor.

- Specify the available access modifiers in C# and briefly explain them
private - it can use only the class for itself
protected - it can use the childs in inheritance

- Briefly explain the mechanism of exception handling
mechanism is Try catch/finaly/throw. you can solve it imidiatly by catch or you can throw it up and catch it later.

- What is the difference between an abstract class and an interface?
you can inherit only from 1 abstract clas and inherit from many interfaces.

- How does using (...) {...} block work? What is the relation to interfaces and why?
in () is parameter of that and it {} you have block of code which will dissapire after }.

- How IEnumerable<T> and IEnumerator<T> interfaces work? What properties and methods need to be implemented in classes that implements them? What are their relation to foreach loop?

## Programming tasks

You can write your solutions in any language, you can even write pseudo code or using only your own words.
The point is not to make a perfectly running application, the point is the way you think!
Don't worry if you miss a semicolon or some parantheses. You might use the LINQ library for your solutions but none of the exercises require them

### Palindrom

Write a function which decides whether a text is palindrom(It's the same whether you read it forwards or backwards). E.g.: abba, rotator, stats.
You might assume that the input string is not null, the length is greater than 1 and less than one million. **Strive for the low memory complexity!**

Example:

```csharp
public bool IsPalindrom(string input) {

}

IsPalindrom("alma"); //false
IsPalindrom("görög"); //true
```

public bool IsPalindrom(string input) 
{
	if(string.IsNullOrEmpty(input) || input.Lenght == 1 || input.Lenght < 1000000)
	{
		return false;
	}
	var count = 0;
	var reversedInput = string.Empty;
	for(i = input.Lenght - 1, i >= 0, i--)
	{
		reversedInput[count] = input[i].ToString();
	}
	if(input == reversedInput)
	{
		return true;
	}
	else
	{
		return false;
	}
}





### Find The Duplicate

You have an array that contains strings. Every item in the array is unique except one which is present in the array exactly twice.
Write a function which finds the string that is present twice in the array.
You might assume that the input array is not null, the length is greater or equal to 2 and less than one million. **Strive for the low time complexity!**

Example: 

```csharp
public string FindTheDuplicate(string[] input) { 
        
}

string[] fruitBasket = new string[] { "apple", "banana", "coconut", "durian", "banana", "elderberry", "fig", "grapefruit" };
FindTheDuplicate(fruitBasket); //should return banana
```

public string FindTheDuplicate(string[] input)
{
	if(input == null || input.GetLenght() 1) || input.Lenght < 1000000)
	{
		return string.Empty;
	}
	
	for(i = 0, i < input.GetLenght(), i++)
	{
		for(j = i, j < input.GetLenght() - 1, j++)
		{
			if(input[i] == input[j + 1])
			{
				return input[i];
			}
		}
	}
	return string.Empty;
]


### Count The Words

You have a long string that has some meaning on a real language. For example a whole novel in a single string.
Write a function that counts the occurence of each word inside the string and writes them to the output in the following format: `word: number of occurences`
You might assume that the input is not null and not empty. The order of the words on the ouput does not matter.
The solution might be case insensitive, you don't have to differentiate bwetween capital and non-capital letters.
The punctuation marks and line endings are not part of the words!

Example:

```csharp
public void CountTheWords(string crazyLongString) { 
        
}

string boci = "Boci, boci tarka, se füle, se farka.";
CountTheWords(boci);

//Output:
//boci:2
//tarka:1
//se:2
//füle:1
//farka:1
```

public void CountTheWords(string crazyLongString) 
{ 
	crazyLongString = crazyLongString.Split(","," ",".");
	var countWords = new Dictionary<string,int>();
	foreach(var word in crazyLongString)
	{
		if(countWords.ContainsKey(word))
		{
			countWords[word]++;
		}
		else
		{
			countWords.Add(word, 1);
		}
	}
	foreach(var KeyPairValue in countWords)
	{
		Console.WriteLine($"{KeyPairValue.Key}:{KeyPairValue.Value}");
	}
}



### What Is The Output

What is the output of the following C# application? Explain your solution!

```csharp
using System;

namespace ConsoleApp2
{
  public class Person
  {
    public string Firstname { get; set; }

    public string Lastname { get; set; }

    public override string ToString() => $"{Firstname} {Lastname}";
  }

  class Program {
    static void Main(string[] args) 
    {
        int i = 0;
        string s = "apple";
        Person p = new Person{ Firstname = "Jonh", Lastname = "Doe" };
        
        DoSomething(i, s, p);
        
        Console.WriteLine(i);
        Console.WriteLine(s);
        Console.WriteLine(p);
    }
    
    static void DoSomething(int i, string s, Person p)
    {
        i = 5;
        s += "banana";
        p.LastName = "Rambo";
    }
  }
}

```

Output is in Console as
0
apple
Jonh Doe

Method doSomething is void so it returns nothing
and property to String() is overriding.


## SQL

- What is the PRIMARY KEY?
- What is the difference between CLUSTERED INDEX and NONCLUSTERED INDEX?
- There is a table called `Employees`. Let's assume that the columns exist and they have the right data type.
What is going to happen if we execute the script and we destroy the database connection during the execution? What are the possible problems that might occure?

```sql
BEGIN TRANSACTION

UPDATE Employees
SET Salary = Salary * 1.1
WHERE 
	Salary < 250000
	AND IsActiveEmployee = 1
```

## Web and HTTP

- Specify the existing HTTP request methods and describe their usage!
- What are the groups of HTTP response status codes? Write an example for each group!
