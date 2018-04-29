---
layout: post
title: Dealing with Overflow
---

Recently my experiment had a big problem and the even bigger problem was I never knew there was a problem. My assumption was that it just need more time than usual to run since some debugging printings were working fine.

After staring at the code for several minutes, Professor quickly spotted one line and said there might be an overflow in this line. After inserting a print

```
if (val == Double.Infinity) Console.Write("*");
```
Console started to print a lot of `*`s. Oops! My experiment was actually running blankly outputing random numbers.

So, what's next? `BigInteger` could be used but this would significantly increase the running time. "Or maybe we could try logarithm", Professor quickly began his calculation.

```
x = logX
y = logY
Z = X + Y
z = logZ = log(X+Y) = log(X(1+Y/X)) = logX + log(1+Y/X)
```

Nice trick! I could never think of transforming additon in this way.

The next question is coding! Thankfully, `C#` provides operator overloading so that we could transform "+" quickly. The code is like:

```
class CustomDouble
	double contents = 0.0;
	
	CustomDouble(double n)
	{
		contents = n;
	}
	public static implicit operator CustomDouble(double n)
	{
		return new CustomDouble(n);
	}
	
	public static double getOriginal(CustomDouble a)
	{
		return Math.Pow(10, a.contents);
	}
	
	public static double getContents(CustomDouble a)
	{
		return a.contents;
	}
	
	public static CustomDouble operator +(CustomDouble a, CustomDouble b)
	{
	...
	}
```

It is a little tricky to implement the add operation concerning all the edge cases. Also, I forgot those operators like `>`, `*`, `+=` at first.

Although this is a nice trick, I haven't got my results yet. Hopefully it could finish running before my finals.
