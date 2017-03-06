# Java Pro Tips & Interesting Quirks 

### Single vs Double Operators

Java provides the single amperand (&) and vertical bar (|) for an unconditional evalution of both operands. Therefore, **&** is referred as the *unconditional AND* operator, and **|** is referred as the *unconditional OR* operator. In some rare siutations when needed, one can use the single **&** or **|** to guarantee that the right-hand operand is evaluated regardless of whether the left-hand operand is **true** or **false**. 

On the other hand, the double amperand (&&) and vertical bar (||) are *short circuit* operators; that is, it won't necessarily evaluate all operands if the precedent operand returns false (for &&) or precedent operand returns true (for ||). 

> If possible, avoid using the **&** and **|** operators; the benefits of such opeartors are marginal. Furthermore, if one uses the single amerpand (&) and if the left operand returns false, it would result into a runtime error. 

