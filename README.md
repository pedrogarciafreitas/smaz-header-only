**smaz**: compression for very small strings
-----------------------------------------

This repository contains a header-only version of **smaz**, a C library to compress and decompress short strings. For more information about **smaz**, see the original project at [https://github.com/antirez/smaz.git](https://github.com/antirez/smaz.git). Smaz is suitable for compressing very short strings. 

## Quick Start

`shoco_header_only.hpp` is the single required file. All you need is to add it on your project:

```#include "smaz_header_only"```

## Example

The file `test_header_only_smaz.cpp` serves as a test and an example on how to use `smaz_header_only.hpp`.


## Usage

The lib consists of just two functions:

    int smaz_compress(char *in, int inlen, char *out, int outlen);

Compress the buffer 'in' of length 'inlen' and put the compressed data into
'out' of max length 'outlen' bytes. If the output buffer is too short to hold
the whole compressed string, outlen+1 is returned. Otherwise the length of the
compressed string (less then or equal to outlen) is returned.

    int smaz_decompress(char *in, int inlen, char *out, int outlen);

Decompress the buffer 'in' of length 'inlen' and put the decompressed data into
'out' of max length 'outlen' bytes. If the output buffer is too short to hold
the whole decompressed string, outlen+1 is returned. Otherwise the length of the
compressed string (less then or equal to outlen) is returned. This function will
not automatically put a nul-term at the end of the string if the original
compressed string didn't included a nulterm.


## Credits

Small was writte by **Salvatore Sanfilippo** and is released under the BSD license. Check the COPYING file for more information.
