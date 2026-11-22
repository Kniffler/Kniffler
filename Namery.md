# Specification for my own c naming convention
I feel like my code has been annoyingly hard to follow due to the naming convention and lack of comments.
Therefore, this file will server as a guide for myself to name things consistently and add criteria for comments as well as other explanations.
Without further ado, here it goes.

### lowercase/uppercase snake_case `lowercase_snake_case UPPERCASE_SNAKE_CASE`
All words written in lowercase/uppercase respectively, separated by an underscore (_).

### Modified snake_case `Modified_snake_case mODIFIED_SNAKE_CASE`
Almost the same as the former snake_cases, except the first letter is opposite the common case.

### camelCase `camelCase`
Conjunction of all words, where each word is written in lowercase starting with one uppercase letter, except the first word which starts with a lowercase one.

### PascalCase `PascalCase`
Same as camelCase, except the first word starts with an uppercase letter as well.

## Tolerances
Names should exclude natural language whenever possible while also summarising the usage of the respective code.
They may include decimal or roman numbers, but only when relevant.
> [!WARNING]
> Any other number bases such as hexadecimal or octal should be avoided unless the variable usage or context heavily implies them.


# Values/variables
Any value/variable may meet one or more criteria, please prioritize the criteria in order of their listing (e.g. 1st criteria is to be followed even if it violates the 2nd).

## Pointers - Inherited
Pointers are a bit of an odd ball, but they generally inherit the naming convention of their value or that which their value would have if it were a variable.
In a lot of situations the pointer's usage is already different enough for a new name, however if this isn't the case, then add:
- `p_` for camelCase;
- `p` for PascalCase;
- `P_` for snake_case.

*These are to be added at the beginning.

## Single computation holders - Modified_snake_case
A piece, or container, of data, that is computed once during runtime or already given by the user at compile-time. Importantly, if it is given at compile-time, the value cannot be function impeding (alter execution flow of the code). Examples include image and sound data as well as perlin noise.

## Constant values - UPPERCASE_SNAKE_CASE
Any variable defined with the `const` or `enum` keywords or made with the `#define`'d macro - independently of scope.

## Temporary values - camelCase
Any value/variable that is not used consistently throughout its scope or is used once, e.g. a `temp` variable for swapping two values or an intermediate value in a long calculation.

## Permanent values - PascalCase
These are values/variables that are either:
- declared/defined using the `static` or `struct` keyword,
- defined/declared in `main`,
- directly affected (created/modified) by `main` via pointers or functions*,
- fundamental to the functionality of the program as a whole (e.g. a data signal for a display),
- otherwise relevant in a manner the other criteria cannot cover.

*Directly affected by `main`, in this context, means that the value/variable must be affected directly via a mathematical or otherwise unconditional method.
This also signifies that any dependency on a non-permanent value for controlling this value/variable may invalidate it as a permanent value.

## Semi-permanent values (parameters) - camelCase
Variables that are used throughout their scope, but do not exert function nor control over other related/associated parts of the code.
A good example of this is function parameters, they are used entirely within their scope but do not affect functions with similar or related appliances.

## Object member - camelCase/lowercase_snake_case
Any member of a structure or union.

## Acting values - lowercase_snake_case
Any value/variable that exists **only** to act or influence the value of others.

# Functions
## 

# TODO:
- [ ] Add function naming conventions;
- [X] Add object (struct, union, enum and typedef) naming conventions;
- [ ] Cover library scenario;
- [ ] Cover other scenarios.
