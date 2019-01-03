Stack: fixed size, fast
Heap: dynamic size, slow


Example:

let x = 5;
let y = x;

bind value 5 to x, then make a copy of x and bind it to y. We have 2 variables, because integer is fixed size, then two 5 values are pushed to stack.

Example:
let s1 = String::from("hello");
let s2 = s1;

Image:
https://doc.rust-lang.org/book/img/trpl04-01.svg

Leftside: a pointer to memory that holds the contents of the string, a length and capacity. This group data is stored on the stack. On the right is the memory on the heap that holds the content
The length is how much memory, in bytes, the content of String is currently usin.g The capacity is the total of amount of memory, in bytes, that the string has recevied from the operating system.

When we assign s1 to s2, the String data is copied, meaning we copy the pointer, the length , and the capacity that are on the stack. We do not copy the data on the heap that the pointer refers to. In other words, the data representation in memory looks like
https://doc.rust-lang.org/book/img/trpl04-02.svg


