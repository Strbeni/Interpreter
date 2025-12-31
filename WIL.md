prev - Lexical Grammar

## Context Free Grammar
In the Syntaxtic grammar now each "letter"in alphabet is entire token and "string" is sequence of tokens or expression.

Example - "let x = 5" is sequence of tokens "let", "x", "=", "5".
        - "eggs are tasty for breakfast" would be grammar
        - "tasty breakfast for eggs" is not.

`Derivation` - string generated with rules that are in the grammar is called derivation. here rules are called `productions` as it produces strings in grammar.

Teminologies -> Terminal        - Literal Values
                Non-Terminal    - Variables
                production      - Rules

Grammar -> 
```
expression     → literal
               | unary
               | binary
               | grouping ;

literal        → NUMBER | STRING | "true" | "false" | "nil" ;
grouping       → "(" expression ")" ;
unary          → ( "-" | "!" ) expression ;
binary         → expression operator expression ;
operator       → "==" | "!=" | "<" | "<=" | ">" | ">="
               | "+"  | "-"  | "*" | "/" ;
```
## Abstract Syntax Tree

Every Single grammar production(rule) becomes node in the tree.

Do - For each production under expression create subclass tha has fields for variable specific to production(rule).

Do - Automate the process of creating subclasses for each production. It should have description of each tree type, its name and fields.

## Trees 
Problem with expression tree is that it is not easy to evaluate. We need specific implementation for each type of tree.
```
          Interpret()     Resolve()       analyze()
Binary        -             -             -
Grouping      -             -             -
Literal       -             -             -
Unary         -             -             -
```
Each cell represents unique peice of implementtion on that type.

Imagine we create classes with methods for each cell.

pattern matching helps to define another function that matches patter on all of the types.

expression problem.

## The Visitor pattern
Is a design patter,the pattern doest no have anything to do with traversing trees or visiting.

We'll use it on set of classes that are tree-like.
It solves the expression problem and lets us add new columns (operations) easily.

We can definal all of the behaviour o fnew operation on a set of types in one place.

How we gonna do it?
We'll define a separate interface. for example

```
interface Visitor {
        void visitBinary(Binary binary);
}
```


## pretty printing

Converting Tree to a string is known as pretty printing.

## Parsing Expressions