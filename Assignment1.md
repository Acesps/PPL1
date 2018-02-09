Principles of Programming Languages: Assignment 1 

BNF for C++/CLI language

Syntax implemented for the following:
 sequential statements,
 loop (while) , 
 conditional statement (if) ,
 function (function declaration, function definition and function call),
 Arithmetic , logical and relational operators - according to precedence and associativity of all operators invlolved.

========================================================================================================================
Team Members:

2015A7PS0030H : Sachet Shandilya
2015A7PS0119H : Afroz Ahamad Siddiqui
2015A7PS0168H : Shubham Singal
2015A7PS0179H : Nikhil Joshi


===================================== C++/CLI BNF ========================================


<program> :=   <header> using namespace System; <main>
			|  <header> using namespace System; <external-declaration> <main>
			|  <header> using namespace System; <external-declaration> <main> <function-definitions>

<external-declaration> := <function-definition><external-declaration>
						 | <function-declaration><external-declaration>
                         | <declaration><external-declaration>
                         | ɛ  
### ɛ is null                   	

<function-declaration> := <type-specifier> <identifier>(<parameter-declarations>);

<function-definitions> := <function-definition><function-defintions>
						| <function-definition>

<function-definition> := <type-specifier> <identifier>(<parameter-declaration>) { <statements> }

<declaration> := <type-specifier> <identifier> ; 

<parameter-declarations> := <parameter-declaration>, <parameter-declarations> 
						  | <parameter-declaration> 

<parameter-declaration> := <type-specifier> <identifier>

<type-specifier> := void
                   | char
                   | short		
                   | int
                   | long
                   | float
                   | double
                   | signed
                   | unsigned

<main> := int main() { <statements> return 0; }

<statements> :=  <statement>;<statements> 
			   | <statement>;

<statement> := <conditional-statement> | <loop-statement> | <assignment-statement> | <function_call> | <logical-expression>

<function-call> := <identifier> = <function> | <function>

<function> := <identifier>(<parameter-list>) 

<parameter-list> := <identifier>, <parameter-list> | <identifier>

<conditional-statement> := <if-statememt> 

<if-statememt> := if ( <expression> ) { <statements> }
                | if ( <expression> ) { <statements> } else { <statements> }

<loop-statement> := while ( <expression> ) { <statements> } 

<assignment-expression> :=  <identifier> = <logical-expression>

<logical-expression> := 
	  <logical-expression> && <relational-expression>
	| <logical-expression> || <relational-expression>
	| <relational-expression>

<relational-expression> := 
	  <relational-expression> <= <h-relational-expression> 
	| <relational-expression> < <h-relational-expression> 
	| <relational-expression> >= <h-relational-expression> 
	| <relational-expression> > <h-relational-expression>  
	| <h-relational-expression>

<h-relational-expression> := 
	  <h-relational-expression> == <arithmetic-expression> 
	| <h-relational-expression> != <arithmetic-expression> 
	| <arithmetic-expression>


<arithmetic-expression> := <arithmetic-expression> + <term> 
						| <arithmetic-expression> - <term> 
						| <term>

<term> := <term> * <factor>
		| <term> / <factor>
		| <term> % <factor>
		| <factor>

<factor> := <id>

<id> := <digits>
	| <variables>

<variables> := ! <boolean-variable> 
			| <identifier>

<boolean-variable> := true | false

<digits> := <digit><digits> | <digit>

<digit> := 0 | 1 | 2 | 3 | 4  | 5 | 6 | 7 | 8 | 9

<alphabets> := <alphabet><alphabets> | <alphabet>

<alphabet> := (A-Za-z_)

<identifier> : = <alphabet><identifier-with-digit>

<identifier-with-digit> := <alphabets><digits> | <digits><alphabets> | <digits> 