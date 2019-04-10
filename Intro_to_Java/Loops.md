# Loops
## While loop
* Continulally exceute while a condition is true
~~~
while(true){
   // infinite loop
}
~~~
~~~
int x = 0;
while (x<10){
  System.out.print(x++ + ", " );
}

$ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 
~~~

## Do While loop
* do-while loop evaluates at the end of the loop.
  - Guaranteed to excecute at least once.
~~~
int y = 0;
do {
  System.out.print(y++ + ", " );
}while(y<10);

$ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
~~~

## For Loop

~~~
for(initialization; termination; incremement){}
~~~
~~~
for (int i = 0, k=1; i<10 && k<20; i++, k++){} 
~~~

* `break`: terminates a loop
* unlabelled break statment terminates the innermost switch or loop
* Can break outer loops by labelling the loop ans specifying this label name after the break statement.

~~~
search :
  for(;;;)
    for(;;;)
      break search;
    }
  }
~~~

* `continue` skips current iteration of loop 
* Unlabelled and labelled forms function similarly to break statments.
