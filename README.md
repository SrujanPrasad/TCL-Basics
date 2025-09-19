# Basics of TCL Scripting

## Printing functions
```tcl
puts "Hi TCL";   # this is also correct
puts "Hello, World!";  # my first program
#puts "Hello World!"   # comment this is wrong
puts "Hello TCL";
puts "Welcome to new programming language";
# when we are using multiple puts statements then it is necessary to put a semicolon
```

## Variables and Strings

```tcl
set x 5;                     # declare variable
puts "$x";                   # print variable

set name "ABCDE";            # declare string
puts "$name";                # print string

set y 15;
set str "The value of y is : $y";   # embed variable in string
puts "$str";

set a 10;
set b $a;                    # assign a to b
puts "$b";

puts {hi my name is absc};   # another way of printing strings

set str "Today is a good day";
puts "$str";                 # prints str value
puts {Today is a good day};  # prints text as it is
puts {$str};                 # prints text as it is (no substitution)
```

## Arithmetic Operations

```tcl
set a 10;
set b 5;
set c [expr {$a + $b}];   # addition
puts "$c";
puts "[expr {$a + $b}]";  # addition
puts "[expr {$a - $b}]";  # subtraction
puts "[expr {$a * $b}]";  # multiplication
puts "[expr {$a / $b}]";  # division
puts "[expr {$a % $b}]";  # modulus
```

## Logical Operators

```tcl
set p 0;
set q 1;
puts "[expr {$p && $q}]";   # logical and
puts "[expr {$p || $q}]";   # logical or
puts "[expr {!$p}]";        # logical not
```

# Bitwise Operators
```tcl
set w 15;
set v 10;
puts "[expr {$w & $v}]";    # bitwise and
puts "[expr {$w | $v}]";    # bitwise or
puts "[expr {$w ^ $v}]";    # bitwise xor
```

## Nested set example
```tcl
set a "[set x {VLSI Academy}]"
puts "$x and $a";           # both x and a will be "VLSI Academy"
```
## If-Else
```tcl
set c 18;
if {$c == 18} {
  puts "Your age is $c, you can vote"
} else {
  puts "Sorry"
}
```
## User Input
```tcl
set name [gets stdin];    # get input from user
puts "Hi $name";
```

## While Loop
```tcl
set n 0;
while {$n < 10} {
  puts "n is : $n";
  set n [expr {$n + 1}];
}
```

## For Loop
```tcl
for {set i 0} {$i < 5} {incr i} {
  puts "i is: $i";
}
```

## Arrays
```tcl
set employee(0) Name;
set employee(1) id;
set employee(2) salary;

puts $employee(0);
puts $employee(1);
puts $employee(2);

# print array elements
for {set index 0} {$index < [array size employee]} {incr index} {
  puts "employee($index) : $employee($index)";
}

# Alternative (foreach)
# foreach index [array names employee] {
#   puts "employee($index) : $employee($index)";
# }
```
## String functions
```tcl
set x a<b;
puts "$x"

puts [string compare "Hello" "World"];   # compare strings
puts [string index "Hello World" 6];     # character at index
puts [string length "Helloworld"];       # length of string
puts [string toupper "helloworld"];      # uppercase version 
puts [string tolower "HELLOWORLD"];      # lowercase version

set s1 "Hello World today";
append s1 " is friday";                  # append to string
puts $s1;
```
## Weight converter program 
```tcl
set weight 72;
set choice [gets stdin];
puts "l(lbs) or k(kgs) : $choice";

if {$choice == "l"} {
  puts "Weight in pounds is : [expr {$weight * 2.2}] lbs";
} elseif {$choice == "k"} {
  puts "Weight in kg is : [expr {$weight / 2.2}] kg";
} else {
  puts "Enter a valid choice";
}
```
## Functions 
```tcl
#functions - proc function_name {} 
proc first_proc {} {
  puts "This is the first proc";
}
first_proc;      #function call

proc sum {t s} {
  return [expr $t+$s];
}
puts "The sum is :[sum 10 20]"; #function call
```
