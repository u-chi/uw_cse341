Video: [ML Variable Bindings and Expressions].

Code:
```sml
(* val is a keyword
   x is a variable name
   = is used as a keyword here (has different meaning in expressions)
   34 is a very simple expression (and value)
   ; is used as a keyword here (has different meaning in expressions)
 *)
val x = 34;
(* static environment: x-->int *)
(* dynamic environment: x-->34 *)

val y = 17;
(* static environment: y-->int, x-->int *)
(* dynamic environment: y-->17, x-->34 *)

(* to evaluate an addition, evaluate the subexpressions and add *)
(* to evaluate a variable, lookup its value in the environment  *)

val z = (x + y) + (y + 2);
(* static environment: z-->int, y-->int, x-->int *)
(* dynamic environment: z-->70, y-->17, x-->34 *)

val q = z+1;
(* static environment: q-->int, z-->int, y-->int, x-->int *)
(* dynamic environment: q-->71, z-->70, y-->17, x-->34 *)
 
val abs_of_z = if z < 0 then 0 - z else  z;
(* static environment: abs_of_z-->int, q-->int, z-->int, y-->int, x-->int *)
(* dynamic environment: abs_of_z-->70, q-->71, z-->70, y-->17, x-->34 *)
 
val abs_of_z_simpler = abs z;

```

A variable binding:
```sml
 val x = e; 
```

**Syntax** is just how you write something.\
**Semantics** is what that something means
 - Type-checking (before program runs)
 - Evaluation (as program runs)

For variable bindings:
 - Type-check expression and extend **static environment**
 - Evaluate expression and extend **dynamic environment** 

Video: [Rules for Expressions]

Exppressions.
```sml
34 true false x e1+e2 e1<e2
if e1 then e2 else e3 
```
sub-expressions, recursive.

Every kind of expression has
1. Syntax
2. Type-checking rules
3. Evaluation rules (used only on things that type-check) 

[ML Variable Bindings and Expressions]: https://courses.cs.washington.edu/courses/cse341/16sp/videos/unit1/
[Rules for Expressions]: https://courses.cs.washington.edu/courses/cse341/13wi/videos/unit1/4_rules_for_expressions.mp4

