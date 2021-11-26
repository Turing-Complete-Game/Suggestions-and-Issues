# Changelog

This will not be complete. This attempts to capture most changes, but because of rapid devlopment, that might be hard.

### 0.334 Beta
- Fix for saves containing a 64bit Program crashing when being loaded.

### 0.333 Beta

- New 64bit Program Component, has 4 64bit outputs
- The 64bit Program has a 16bit address pin for a total of 512kiB of addressable memory
- Other Program components got reverted back to only being able to address 256 bytes
- Assembler got an upgrade:
  - For 64bit Program labels and constants are now able to handle 64bit
  - Math operations now respect order (e.g. `1 + 2 * 3` is `7`, not `9`)
  - Parentheses also work (e.g. `(1 + 2) * 3` is `9`)
  - Hex (`0xFF`) and Binary (`0b1011`) now work
  - Binary is only highlighted for full 8bits, but works for any length
  - Hex is highlighted for any length up to 4, but only works for length 2
  - Other features that have syntax highlighting already (strings and function calls) still have no effect
