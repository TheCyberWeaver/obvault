#eth 

```java error:4
int x=15;
double y=0;
y=2.5;
x=x*y;
y=x+y+0.5;
System.out.println(x+"  "+y);
```
Compiler error
`{java icon title:corrected}x=(int)(x*y);`

```cpp hl:4
int x = 15;
double y = 0;
y = 2.5;
x = x * y;
y = x + y + 0.5;
cout << x << " " << y;
```
accepted in C++

