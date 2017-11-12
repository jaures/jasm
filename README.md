JASM GUIDE
===
___

### Overview
Welcome to the language of Jaures' Assembly or JASM for short. This language simply began as an experiement in different ways to implement a functional language that would not only be easier than assembly to read but be more expressive as well by obscuring some of the convoluted inner workings of assembly and while still allowing the user to fully express their ideas.

JASM is made up of two flavors of statements, equations and expressions. Expressions are statements that either return a value or interact with the program's stack or registers. They are made up of constants or other expressions. Equations are much like constants, but they also have a label component for allowing users to call that expression by itself or in the composition of another expression. 

There are no variables in JASM, everything is expressed as functions that are described in equation statements, hence why its labeled functional language. It however has a virtual stack and 8 registers that can store values or point to values that will be consumed in function equations.

## Syntax Overview
#
| Instruction |Symbol/Syntax | Functionalaity | Usage |
| :---------: | :----: | :------------- | :---- |
| __Stack-Based Instruction__ |
| Push      | <     | Pushes expression onto the Stack | |
| Pop       | >     | Pops expression from ontop the Stack | |
| Evaluate  | =     | Evaluates expression ontop of the Stack | |
| __Expression-Based Instruction__ |
| Evaluate Expression | ( ... ) | Evaluates the expression to it's literal value (or lvalue) rather than leaving it as a reference in the expression definition | |
| String Literal | $" ... " | Declare a constant String expression that evaluates to the content of the quotations |
| Numerical Literal (Decimal) | #d...# | Declares a constant Numerical expression that evaluates to the content of the '#d'-'#' block as a decimal value | |
| Numerical Literal (Hexadecimal) | #h...# | Declares a constant Numerical expression that evaluates to the content of the '#h'-'#' block as a decimal value | |
| Declare a String Expression | {$var}:( ... ) | Creates a String expression that can be referenced using $var, that has a length of 1 and a size of 1 byte |
| Declare a String Expression | {$var}{#varSize}:( ... ) | Creates a String expression that can be referenced using $var, that has a length equal to the numerical value that #varSize evaluates to |
| Declare a Numerical Expression | {#var}:( ... ) | Creates a String expression that can be referenced using $var, that has a length of 1 and a size of 1 byte |
| Declare a Numerical Expression | {#var}{#varSize}:( ... ) | Creates a String expression that can be referenced using $var, that has a length equal to the numerical value that #varSize evaluates to |
| __Conditional Control Structure__ |
| If-Equal Conditional Evaluate | (== VAL)[ ... ] | If the top of the Stack evaluates to the expression VAL, remove the value and evaluate the expression in the block |
| If-LessThan Conditional Evaluate  | (<< VAL)[ ... ] | If the top of the Stack evaluates to less than the expression VAL, remove the value and evaluate the expression in the block |
| If-LessThanOrEqual Conditional Evaluate  | (<= VAL)[ ... ] | If the top of the Stack evaluates to less than or equal to the expression VAL, remove the value and evaluate the expression in the block |
| If-GreaterThan Conditional Evaluate  | (>> VAL)[ ... ] | If the top of the Stack evaluates to greater than the expression VAL, remove the value and evaluate the expression in the block |
| If-GreaterThanOrEqual Conditional Evaluate  | (>= VAL)[ ... ] | If the top of the Stack evaluates to greater than or equal to the expression VAL, remove the value and evaluate the expression in the block |
| __Iterative Control Structure__ |
| While-Zero Evaluate  | (??)[ ... ] | While the top of the Stack evaluates to zero, keep evaluating the expression in the block |
| While-NotZero Evaluate  | (!?)[ ... ] | While the top of the Stack does not evaluate to zero, keep evaluating the expression in the block |
| __Conditional Control Structure__ |


| Declaration of Variables | Usage |
| :----------------------: | :----------------|
| `($var) = (exp1,exp2,...)` | Declare a String Expression |
| `(#var) = (exp1,exp2,...)` | Declare an Integer Expression |
| `(%var) = (exp1,exp2,...)` | Declare a Void Expression |

| Declaration of Array of Variables | Usage |
| :----------------------: | :----------------|
| `{[S]$var} = [exp1, exp2, ...]` | Declare an Array of String Expressions of length S
| `{[S]#var} = [exp1, exp2, ...]` | Declare an Array of Integer Expressions of length S
| `{[S]$var} = [exp1, exp2, ...]` | Declare an Array of Void Expressions of length S

| Stack-Based Operations | Usage|
| :----------------------: | :----------------|
| `(<$var)` | Push a String Expression onto the Stack
| `(<#var)` | Push an Integer Expression onto the Stack
| 
| `(=>)` | Evaluate Expression at the top of the Stack and puts the value onto Stack |
| `(=>N)` | Evaluate Expression at the top of the Stack and puts the value into register N |
| `(=>$var)` | Evaluate Expression at the top of the Stack and puts the literal value into String variable, $var. If the variable does not exist, one is created |
| `(=>#var)` | Evaluate Expression at the top of the Stack and puts the literal value into Integer variable, #var 
| `(== ...)` | If the top of the stack evaluates to the same value as the expression, then execute the following expression from the Stack |

| Expression-Based Operation | __Usage__ | __Example__|
| :----------------------: | :----------------|:---:|
| `""` | Use quotes to define String literal Expressions | `("LiteralString")`|
| `##` | Use pound/hashtag to define Integer literal Expression | `(#65#)` |    
| ? | Returns void if the top of the Stack also evaluates to void otherwise procede to the evaluate next expression |
|  |  |





### Syntax Layout
#### Statement
