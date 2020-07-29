---
title: Ain't no no-args constructors in wrapper classes
description: 
date: 2018-08-24
tags:
  - data-types-tag
layout: layouts/post.njk
---

Here are two ways to distract you in a question about using wrapper classes: call a no-args constructor, or a non-static method with no instantiation of an object of that wrapper class. Example?

```java
public class WrapperDistractors {
	public static void main (String[]args){
		String foo = "42";
		long bar = Long.parseLong(foo);
//		long baz = (new Long()).parseLong(foo); // no suitable constructor
//		long qux = Long.longValue(foo); // non-static method
		long quux = new Long(foo);
		long corge = Long.valueOf(foo).longValue();	
		System.out.println(Long.valueOf(baz));
	
		
	}
}
```

So, *[why don't wrapper classes have no-args constructors?](https://stackoverflow.com/questions/874529/why-dont-java-wrapper-classes-have-no-arg-constructors)* Because they are immutable. Your one big chance at assigning a value is on construction. 

[Geeks for geeks](https://www.geeksforgeeks.org/wrapper-classes-java/) points out the following use cases for having wrapper classes:

1. In order to modify an argument passed to a method we need an object.  Wrapper classes can convert primitive data types, which are pass-by-value, into objects.
2. The `java.util` package only handles objects, so wrapper classes help here too.
3. 
