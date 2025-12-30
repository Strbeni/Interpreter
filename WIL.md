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