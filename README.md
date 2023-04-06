# Dragon

during my second year of study, I had to learn the recursive algorithm.
To do this we made fractals, and one of them was the 'dragon curve'.
It was really challenging since teachers let us find by our self at first.
And I love challenges.

So I put my self to it, and then the magic of math and programming added to the equation.
So MANY ways to abstract the fractal, and many more to program it without take all variations into account.
Then a passion was born.

Later in the year because of 2 years of pandemic I was close to give up my studies.
I had a lot of lessons to make up.
I had to find the motivation to make it all up.
So, I took the 'dragon curve', and decided to program it in all the languages I needed to learn.
Need to learn PHP ? Let's make a PHP dragon curve.
Need to learn C ? Let's make a C dragon curve.
And so on...

Then my class started challenging me on other languages in a humorous tone.
But, remember ? I LOVE challenges.
So I made my mind. I have to code it in all langages I could encounter.

So that's where we are.
I hadn't done it in so many langages since I had to study, 
but it's already something. And I'm still working on it.

So in this repo I will post what I have done since my studies.

There will be :
A lot of java
Some PHP
A lot of C
Some python
Some TI-Basic (that was a hard one)
Some Bash
And even Minecraft (with the mod 'scarpet', not with command blocks) 

I should also explain some of the logic behind these production.
Mainly the logic to turn it from a recursive form to a iterative form and then the binary optimisation.

```c
//recursive
dragon(int n, ...){
    if(n>0){
        dragon(n-1, ...);
        dragon(n-1, ...);
    }
}
//iterative
dragon(int n){
    n = 1<<n; //n = pow(2,n);
    for(int i=1; i<=n; i++){
        int j=1;
        while( i%(j*2) == 0) j = j*2;
        if( ((i-j)/(j*2)) % 2 == 0 ) {...}
        else {...}
    }
}

//iterative x binary
dragon(int n){
    n = 1<<n;
    for(int i = 1; i <= n; i++){
        int j = 1;
        while(!(i&j)) j<<=1; //j=j*2
        if( i&j<<1 ){...}
        else {...}
    }
}

//iterative fuckingly optimised
dragon(int n){
    n = 1<<n;
    for(int i = 1; i <= n; i++){
        if( -i & i & (i>>1) ){...}
        else {...}
    }
}

```
