## Basics of TCL Scripting

```tcl
puts "Hi TCL";   # this is also correct
puts "Hello, World!";  # my first program
#puts "Hello World!"   # comment this is wrong
puts "Hello TCL";
puts "Welcome to new programming language";
# when we are using multiple puts statements then it is necessary to put a semicolon

# -----------------------------
# Variables and Strings
# -----------------------------
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

# -----------------------------
# Arithmetic Operations
# -----------------------------
set a 10;
set b 5;
set c [expr {$a + $b}];   # addition
puts "$c";
puts "[expr {$a + $b}]";  # addition
puts "[expr {$a - $b}]";  # subtraction
puts "[expr {$a * $b}]";  # multiplication
puts "[expr {$a / $b}]";  # division
puts "[expr {$a % $b}]";  # modulus

# -----------------------------
# Logical Operators
# -----------------------------
set p 0;
set q 1;
puts "[expr {$p && $q}]";   # logical and
puts "[expr {$p || $q}]";   # logical or
puts "[expr {!$p}]";        # logical not

# -----------------------------
# Bitwise Operators
# -----------------------------
set w 15;
set v 10;
puts "[expr {$w & $v}]";    # bitwise and
puts "[expr {$w | $v}]";    # bitwise or
puts "[expr {$w ^ $v}]";    # bitwise xor

# -----------------------------
# Nested set example
# -----------------------------
set a "[set x {VLSI Academy}]"
puts "$x and $a";           # both x and a will be "VLSI Academy"

# -----------------------------
# If-Else
# -----------------------------
set c 18;
if {$c == 18} {
  puts "Your age is $c, you can vote"
} else {
  puts "Sorry"
}

# -----------------------------
# User Input
# -----------------------------
set name [gets stdin];    # get input from user
puts "Hi $name";

# -----------------------------
# While Loop
# -----------------------------
set n 0;
while {$n < 10} {
  puts "n is : $n";
  set n [expr {$n + 1}];
}

# -----------------------------
# For Loop
# -----------------------------
for {set i 0} {$i < 5} {incr i} {
  puts "i is : $i";
}

# -----------------------------
# Arrays
# -----------------------------
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
