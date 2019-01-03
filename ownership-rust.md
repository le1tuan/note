Stack: fixed size, fast
Heap: dynamic size, slow


Example:

let x = 5;
let y = x;

bind value 5 to x, then make a copy of x and bind it to y. We have 2 variables, because integer is fixed size, then two 5 values are pushed to stack.