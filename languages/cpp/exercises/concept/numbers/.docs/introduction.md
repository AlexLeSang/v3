There are two different types of numbers in C++: integers and floats.

## Integer numbers

Basic integer type is `int`, e.g. `0`, `1000`. This type can be extended with sign and length modifiers. The keyword `int` can be omitted if one of the length modifiers is present. The actual width in bits depends on the data model (computer architecture).

Modifiers can be mixed in any order. Only one of each group can be present in type name.

Signedness:
- `signed` - target type will have signed representation (this is the default if omitted)
- `unsigned` - target type will have unsigned representation

Size:
- `short` - target type will be optimized for space and will have width of at least 16 bits.
- `long` - target type will have width of at least 32 bits.
- `long long` - target type will have width of at least 64 bits.

**Note**: integer arithmetic is defined differently for the signed and unsigned integer types. See arithmetic operators, in particular integer overflows.

**Note**: integers are used in boolean expression context, `0` is `false`, everything else is `true`.

### Arithmetic operators

Arithmetic is done using the standard [arithmetic operators][arithmetic-operators] (`+`, `-`, `*`, etc.). Numbers can be compared using the standard [comparison and equality operators][comparison-operators] (`<`, `>=`, etc.) and the equality-operator (`==`) and inequality operator (`!=`).


### Fixed width integer types

By including `<cstdint>`, programmer gains access to integer types with fixed width. This provides data-model independent way of representing integer numbers and ensures consistent results of arithmetic operations across all platforms.

## Floating-point numbers

Floating point numbers in C++ are represented with 3 types:
- `float` - single precision floating point type. Usually IEEE-754 32 bit floating point type
- `double` - double precision floating point type. Usually IEEE-754 64 bit floating point type
- `long double** - extended precision floating point type. Does not necessarily map to types mandated by IEEE-754. Usually 80-bit x87 floating point type on x86 and x86-64 architectures.

**Note**: for floating-point numbers operators `==` and `!=` perform **bit-by-bit** comparison! Use `-Wfloat-equal` flag for GCC/Clang to get warning about this.


### Special values

There are some special values defined for floating point types, such as:
- infinity (positive and negative), see INFINITY
- the negative zero, -0.0. It compares equal to the positive zero, but is meaningful in some arithmetic operations
- not-a-number (`NaN`), which does not compare equal with anything (including itself)

Real floating-point numbers may be used with arithmetic operators `+ - / *` and various mathematical functions from `cmath`.


## Working with numbers

```cpp

// Integer numbers
short s = 4;
int a = 5;
unsigned long = 44;

// Floating-point numbers
float f = 12e4;
double d = 55.85;

```


## Conversions

Implicit conversions are defined between real floating types and integer types.

Compilation flags, such as `-Warith-conversion`, `-Wconversio`, `-Wfloat-conversion` and `-Wsign-conversion` for GCC/Clang, warn about possible unsafe numerical type conversions.

[integer-overflow]: https://en.cppreference.com/w/cpp/language/operator_arithmetic#Overflows
[fixed-width-integer-types]: https://en.cppreference.com/w/cpp/types/integer
[fundamental-types]: https://en.cppreference.com/w/cpp/language/types
[numeric-limits]: https://en.cppreference.com/w/cpp/types/numeric_limits
[arithmetic-operators]: https://en.cppreference.com/w/cpp/language/operator_arithmetic
[comparison-operators]: https://en.cppreference.com/w/cpp/language/default_comparisons