# Computer Systems
- [Zurich Tech Computer architecture](https://safari.ethz.ch/architecture/fall2017/doku.php?id=schedule)
- [CMU Computer sys 2018](http://www.cs.cmu.edu/~213/schedule.html)
- [CMU video links](http://www.cs.cmu.edu/afs/cs/academic/class/15213-f17/www/schedule.html)

## Representation in Machine-level Programs

### Bytes
* 1 `byte` === 8 `bits`
* Memory is viewed as a large array of *bytes* or *virtual memory*.
* Each *byte* is identified by an *address*.
* The set of all possible *addresses* is the *virtual address space*.
* Each program object is treated as a block of bytes.
* The program itself is treated as a sequence of bytes.
* A *pointer* points to the address of the first byte of a block (program object).

### Ordering of Bytes
* A number starting with `0x` or `0X` are interpreted as hexadecimal (base-16). 
* Example: a variable `x` of type `int` has address `Ox100`
    * value of the address expression `&x` is `Ox100`
    * assuming data type `int` has 32-bit representation
    * the 4 bytes of `x` are stored in memory locations `Ox100`, `Ox101`, `0x102`, and `Ox103`.
* *Little endian* (ascending order) - store object in memory ordered from least significant byte to most
* *Big endian* (descending order)
* Byte ordering becomes important when: 
    * *little endian* machines communicate with *big endian* machines.
    * looking at byte sequences representing integer data
    * programs circumvent the normal type system

### Boolean
* `~` NOT
* `&` AND
* `|` OR
* `^` XOR

### Range Limits of Data Size
* `<limits.h>` defines implementation-specific with the #define directive
* `<stdint.h>`
* `typedef signed T A`
* `typedef unsigned T B`
* Two's-Complement Encodings

### Data Types
| C Declaration | Intel Data Type | Assembly suffix | Size (bytes)
|  --- | --- | --- | --- |
| `char` | Byte | b | 1 |
| `short` | Word | w | 2 |
| `int`  | Double word | l | 4 |
| `long` | Quad word | q | 8 |
| `char *` | Quad word | q | 8 |
| `float`| Single precision | s | 4|
| `double` | Double precision | l | 8 |

## Pointers
### Dereferencing
* `long x = *xp;`
    - read the _value_ stored in location _designated_ by `*xp`
    - store it as a local variable named `x`
    - `*` performs pointer defererencing
* `*xp = y;`
    - writes _value_ of _parameter_ `y` at location _designated_ by `*xp`
    - indicates a _write_ operation since `*xp` is on the left

## Locality and Caching
* Temporal Locality: If you just did something, it is very likely that you will do the same thing again soon
    - Classroom analogy: "since you are here today, there is a good chance you will be here again and again regularly"
    - Bookshelf analogy: "recently-used books tend to stay on desk"
        - Until the desk gets full 
    - A program tends to reference the same memory location many times and all within a small window of time
    - Recently accessed data will be again accessed in the near future 
* Spatial Locality: If you did something, it is very likely you will do something similar/related (in space)
    - Classroom analogy: "every time I find you in this room, you are probably sitting close to the same people"
    - Bookshelf analogy: "Adjacent books in the shelf needed around the same time
        - If I have organized/categorized my books well in the shelf"
    -  A program tends to reference a cluster of memory locations at a time
        - instruction memory references
        - array/data structure references
    - Nearby data in memory will be accessed in the near future
## Memory
### Manual vs. Automatic Memory Management
* [Memory management reference](http://www.memorymanagement.org/)
* [Manual](https://en.wikipedia.org/wiki/Manual_memory_management): Programmer manages data movement across levels
    - Examples: `malloc`
* [Automatic](https://en.wikipedia.org/wiki/Category:Automatic_memory_management): Hardware manages data movement across levels, transparently to the programmer
    - Examples: [tracing garbage collection](https://en.wikipedia.org/wiki/Tracing_garbage_collection)
* [Memory safety in Rust](http://willcrichton.net/notes/rust-memory-safety/)

### Memory Hierarchy
- [Slides](http://www.cs.cmu.edu/afs/cs/academic/class/15213-f17/www/lectures/11-memory-hierarchy.pdf)
- [Lecture vid](https://youtu.be/vusQa4pfTFU)
- CMU reading 6.1-6.3
