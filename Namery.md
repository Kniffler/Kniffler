# Specification for my own c naming convention
I feel like my code has been annoyingly hard to follow due to the naming convention and lack of comments.
Therefore, this file will server as a guide for myself to name things consistently and add criteria for comments as well as other explanations.
Without further ado, here it goes.

## Conventional conventions
Conventions mentioned in this document.
### SCREAMING_CASE
(Couldn't find a name for this one, made it up)

All words separated by an underscore (_) and written in uppercase exclusively.  
### camelCase
Conjunction of all words, where each word is written in lowercase starting with one uppercase letter, except the first word which can start with either uppercase or lowercase.
### lowercase/uppercase snake_case
All words written in lowercase/uppercase respectively, separated by an underscore (_).
### PascalCase
Same as camelCase, but the first word HAS to start with an uppercase letter.
## Tolerances
Names should exclude natural language whenever possible while also summarising the usage of the respective code.
They may include decimal or roman numbers, but only when they are relevant.
> [!WARNING]
> Any other number bases such as hexadecimal or octal are prohibited in order to avoid confusion.

# Variables
Any variable may meet one or more criteria, please prioritize the criteria in order of their listing.

E.g. 1st criteria is to be followed even if it violates the 2nd.

## Constant (non-changing)
Any variable defined with the `const` keyword or made with the `#define`'d macro - independently of scope.

**These are to be written in SCREAMING_CASE**

## Temporary (little inherent usage)
Any variable that is not used consistently throughout its scope, e.g. a `temp` variable for swapping two values or an intermediate value in a long calculation.

**These are to be written in camelCase**

## Semi-permanent (parameters)
Variables that are used throughout their scope, but do not exert function nor control over other related/associated parts of the code.
A good example of this is function parameters, they are used entirely within their scope but do not affect functions with similar or related appliances.
There are exceptions however, those being pointers and variables in `main`.

**These are to be written in camelCase**

## Pointers
Pointers are a bit of an odd ball, but they generally inherit the naming convention of their value or that which their value would have if it were a variable.
In a lot of situations the pointer's usage is already different enough for a new name, however if this isn't the case, then add:
- a `p_` for camelCase;
- a `p` for PascalCase;
- a `P_` for snake_case.

*These are to be added at the beginning.

## Permanent (high-function variables)
These are variables that are either:
- defined/declared in `main`;
- directly (NOT indirectly) affected by `main` via pointers or functions;
- fundamental to the functionality of the program as a whole (e.g. a data signal for a display);
- otherwise relevant in a manner the other criteria cannot cover.

Directly affected by `main`, in this context, means that the variable's value must be affected directly via a mathematical or otherwise unconditional method.
This also signifies that any dependency on a non-permanent variable for controlling the value of this variable may invalidate it as a permanent variable.

**These are ALWAYS written in PascalCase**


# TODO:
- [ ] Add function naming conventions;
- [ ] Add object (struct, union, enum and typedef) naming conventions;
- [ ] Cover library scenario;
- [ ] Cover other scenarios.
