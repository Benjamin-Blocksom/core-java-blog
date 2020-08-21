---
title: 'Different folks: Local variables in loop constructs'
description: Local variables in loop constructs.
date: 2020-05-01
tags:
  - Java-OCA
layout: layouts/post.njk
---

## Different Folks

As always, I ask myself the following questions about any new Java code snippet:

1. Will it compile?
2. Will it throw an error or exception?
3. What will its output be?

This morning I was reviewing a test question on loop constructs. I came up with the following snippet: 

```java
public class DifferentFolks {
	private int folks;
	void seeFolks(){
		while(folks<=5){
		for(int folks=1; folks<=3;){
			System.out.print(folks + " ");
			folks++;
			}
		folks++;
		}

	}
	public static void main (String[]args) {
		new DifferentFolks().seeFolks();
	}
}
```

1. It compiles
2. No errors/exceptions are thrown.
3. It prints "1 2 3" six times.

What's the point? Pay attention to local variables and instance variables. Even if they have the same name, they may not be the same. They're different, folks. A big give away should be the fact that the iteration through the `for` loop doesn't increment the local variable `folks` in the assessment statement. (If you notice, it is just a empty statement.) The point here is to trick you into thinking you are incrementing its *tocayo* variable above. 

Other than this, it is a simple nested `if` loop inside a `while` loop. 