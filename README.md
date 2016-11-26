# ECS40
# ECS 40 Homework 3: From Infix to Postfix Expressions

## Early bird special

If you pass all the test cases by 2016-11-11T23:59:59-08:00, you will get 20% bonus points.

## Submission instructions

```
$ cargo new 3 --name your
$ cd 3
$ # Save your program in `src/lib.rs`
$ git add Cargo.toml src/lib.rs
$ git commit
$ git remote add origin metastasis@gradebot.org:user/{username}/3/3
$ git push origin master
```

Because postfix expressions are simpler and faster to evaluate, compilers transform infix expressions in source programs to postfix expressions in executable programs. You will implement this transformation.

## Infix expressions

An infix expression contains one or more of the following tokens:

* Operands: integers, such as `1`, `-23`.
* Operators: arithmetic operators `+`, `-`, `*`, and `/` with their normal association and precedence.
* Left and right parentheses.

A valid infix expression must satisfy all the following rules:

* An operand or left parenthesis cannot be preceded by an operand or right parenthesis.

* An operator or right parenthesis cannot
  * be the first token in the expression, or
  * be preceded by an operator or left parenthesis.

* An operator or left parenthesis cannot be the last token in the expression.

* Each left parenthesis must match a unique right parenthesis, and vice versa.

## Transform infix to postfix expression

1. Create a stack.
2. Scan the tokens in the infix expression.
  * If the token is an operand, output it.
  * If the token is a left parenthesis, push it onto the stack.
  * If the token is a right parenthesis, pop and output all the operators from the stack until encountering a left parenthesis. Pop and discard the left parenthesis.
  * If the token is an operator
	* If the stack is empty, push the token onto the stack.
	* Otherwise, if the top of the stack is an operator and its precedence is greater than or equal to the precedence of the token, pop and output the operator from the stack, and repeat this process. Finally, push the token in the infix expression onto the stack.
3. Pop and output all the remaining tokens on the stack.

## Test cases

* Test 0--10 are valid infix expressions.
* Test 11--24 are invalid infix expressions.

## Public API

Your program must provide the following public API.

```
#[derive(Clone, Copy, Debug, PartialEq)]
pub enum Operator {
    // `+`
    Add,
    // `-`
    Sub,
    // `*`
    Mul,
    // `/`
    Div,
}

#[derive(Debug, PartialEq)]
pub enum InfixToken {
    Operator(Operator),
    Operand(isize),
    LeftParen,
    RightParen,
}

#[derive(Debug, PartialEq)]
pub enum PostfixToken {
    Operator(Operator),
    Operand(isize),
}

/// Transforms an infix expression to a postfix expression.
///
/// If the infix expression is valid, outputs `Some(_)`; 
/// otherwise, outputs `None`.
pub fn infix_to_postfix(tokens: &[InfixToken]) -> Option<Vec<PostfixToken>> {
    unimplemented!();
}
```

Last updated: 2016-11-06
