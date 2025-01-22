# Dragon's Curve

For some reason, I was too invested in the Dragon's Curve fractal. 

At the beginning it was a school exercise, but it went a bit too far... And it would be a shame not to let it be seen anywhere.

It wents from a recurcive algorithm to a nicely optimised algorithm, that it even becomes rediculous how a so little algorithm can draw something so big and complex
```python
for i in range(2**N):
  if( -i & i & i>>1 == 0):
    left(90)
  else:
    right(90)
  forward(1)
```

But before ending up with this version it was a long journey
```c
//recursive (the exercice)
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

//iterative x binary nicely optimised
dragon(int n){
    n = 1<<n;
    for(int i = 1; i <= n; i++){
        if( -i & i & (i>>1) ){...}
        else {...}
    }
}

```
