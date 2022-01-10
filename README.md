# Creating_A_CustomizedComputerLanguageWithAgrammerToFollow-Preetree
Example run:
# Create three variables = x 10
= y 20
=z+xy
# Print some expressions
@
@ + 10 20
@ - 10 20
@ * 10 20
@ // 20 10
@z
@*x+yz
@ // * x + y 10 - y * 10 z

Sample Run:

The interpreter is run by providing the source code file as a command line argument:
        $ python3 pretree.py prog1.pre
When run, the three stages of interpretation occur:
1. Parsing: The source code is compiled into a sequential collection of parse trees.
2. Emitting: The parse trees are traversed inorder to generate infix strings of the state-
ments.
3. Evaluating: The parse trees are executed and any printed output is generated.
Here is the full interpretation output for prog1.pre: PRETEE: Compiling prog1.pre...
        PRETEE: Infix source...
        x = 10
        y = 20
        z = (x + y)
        print
        print (10 + 20)
        print (10 - 20)
        print (10 * 20)
        print (20 // 10)
        print z
        print (x * (y + z))
        print ((x * (y + 10)) // (y - (10 * z)))
        PRETEE: Executing...
        30
        -10
        200
        2
        30
        500
        -2
        
        Syntax Errors:
        =           # Incomplete statement
        = 10 10     # Bad assignment to non-variable
        = x @.      # Bad assignment 
        ^           # Invalid token ^
        
       Runtime Errors:
       @ a            # Unrecognized variable a
       @ // 5 0       # Division by zero error
