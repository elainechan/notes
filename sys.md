# Computer Systems

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

