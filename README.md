# ft_printf

A custom implementation of the C standard library `printf` function, built as a static library for the 1337/42 cursus.

## Overview

`ft_printf` replicates the core behavior of `printf`, parsing a format string and printing arguments to standard output. It returns the total number of characters printed, or `-1` on a write error.

## Supported conversions

| Specifier | Description |
|-----------|-------------|
| `%c` | Single character |
| `%s` | String |
| `%p` | Pointer address in hexadecimal (`0x...`) |
| `%d` | Signed decimal integer |
| `%i` | Signed integer in base 10 |
| `%u` | Unsigned decimal integer |
| `%x` | Unsigned hexadecimal (lowercase) |
| `%X` | Unsigned hexadecimal (uppercase) |
| `%%` | Literal percent sign |

## Project structure

```
ft_printf/
├── ft_printf.c          # Entry point and format parser
├── src/
│   ├── put_char.c       # %c handler
│   ├── put_str.c        # %s handler
│   ├── put_nbr.c        # %d, %i, %u handler
│   └── put_hex.c        # %x, %X, %p handler
├── include/
│   └── libftprintf.h    # Header
└── Makefile
```

## Usage

### Build the library

```bash
make
```

This produces `libftprintf.a`.

### Link in your project

```c
#include "include/libftprintf.h"

int main(void)
{
    ft_printf("Hello, %s! Number: %d, Hex: %x\n", "world", 42, 255);
    return (0);
}
```

```bash
cc -Wall -Wextra -Werror main.c libftprintf.a -o program
```

### Makefile targets

| Target | Action |
|--------|--------|
| `make` / `make all` | Build `libftprintf.a` |
| `make clean` | Remove object files |
| `make fclean` | Remove object files and `libftprintf.a` |
| `make re` | Full rebuild |

## Compilation flags

```
cc -Wall -Wextra -Werror
```

## Author

**aaitelka** — 1337 (42 Network)
