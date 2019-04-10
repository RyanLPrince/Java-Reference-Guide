# Conditionals

## if

~~~
if (x>10){
  System.out.println("x is over 10");
}
else if (x<10){
  System.out.println("x is under 10");
}
else{
  System.out.println("x is equal to 10");
}
~~~

## Switch Cases

* Unlike if-then and if-then-else statements, the switch statement can have a number of possible execution paths. 
* A switch works with the byte, short, char, and int primitive data types, enums, Strings, (primitive wrapper types) Character, Byte, Short, and Integer.

~~~
String day = "Saturday"

switch (day){
  case "Monday": System.out.println("Mondays are the worst!");
                 break;
  case "Tuesday": 
  case "Wednesday":
  case "Thursday": System.out.println("Weekdays are okay!");
                   break;
  case "Friday"  : System.out.println ("Fridays are great!");
  case "Saturday":
  case "Sunday": System.out.println("Weekends are the best!");
                 break;
  default: System.out.println(day + " Is not a day!");  
}
~~~
* Break statements terminate the enclosing switch statement.
* Without the break statements the switch block falls through i.e without the break on Monday, the Tuesday, Wednesday, Thursday  blocks will excecute.
* Can optionally include  default case which excecutes if no other cases exceute or if the matching cases above do not break. 

* Switch statments can also have multiple cases and if-else blocks

~~~
class SwitchDemo2 {
    public static void main(String[] args) {

        int month = 2;
        int year = 2000;
        int numDays = 0;

        switch (month) {
            case 1: case 3: case 5:
            case 7: case 8: case 10:
            case 12:
                numDays = 31;
                break;
            case 4: case 6:
            case 9: case 11:
                numDays = 30;
                break;
            case 2:
                if (((year % 4 == 0) && 
                     !(year % 100 == 0))
                     || (year % 400 == 0))
                    numDays = 29;
                else
                    numDays = 28;
                break;
            default:
                System.out.println("Invalid month.");
                break;
        }
        System.out.println("Number of Days = "
                           + numDays);
    }
}
~~~
