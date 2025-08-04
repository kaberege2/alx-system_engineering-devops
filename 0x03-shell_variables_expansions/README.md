# 0x03. Shell, init files, variables and expansions

This project covers basic Bash scripting with a focus on shell initialization files, environment and local variables, shell arithmetic, and expansions.

## Files and Descriptions

- **0-alias** - Creates an alias `ls` that deletes all files in the current directory.
- **1-hello_you** - Prints `hello` followed by the current Linux username.
- **2-path** - Adds `/action` to the `PATH` variable.
- **3-paths** - Counts the number of directories listed in the current `PATH`.
- **4-global_variables** - Prints all environment (global) variables.
- **5-local_variables** - Prints all local and global variables, including shell functions.
- **6-create_local_variable** - Creates a local variable `BEST` with value `School`.
- **7-create_global_variable** - Creates a global variable `BEST` with value `School`.
- **8-true_knowledge** - Prints the result of `128 + $TRUEKNOWLEDGE`.
- **9-divide_and_rule** - Prints the result of `POWER / DIVIDE` using env variables.
- **10-love_exponent_breath** - Prints the result of `BREATH` raised to the power of `LOVE`.
- **11-binary_to_decimal** - Converts a binary number (env var `BINARY`) to decimal.
- **12-combinations** - Prints all possible 2-letter lowercase combinations except `oo`.
- **13-print_float** - Prints the `NUM` variable rounded to two decimal places.

## Usage

To execute each script:

```bash
source ./<script_name>
```

...

## Advanced Tasks

- **100-decimal_to_hexadecimal** - Converts a base-10 number stored in `$DECIMAL` to hexadecimal and prints it.
- **101-rot13** - Encodes and decodes text using the ROT13 cipher (assumes ASCII input).
- **102-odd** - Prints every other line from the input, starting with the first line.
- **103-water_and_stir** - Adds two environment variable values in custom bases (`water` and `stir`) and prints the result in base `bestchol`.

### Example Usage

```bash
export DECIMAL=1337
./100-decimal_to_hexadecimal   # Output: 539

echo "Hello ROT13!" | ./101-rot13   # Output: Uryyb EBG13!

ls -1 | ./102-odd   # Every other line of directory listing

export WATER=321
export STIR=14
./103-water_and_stir  # Custom base arithmetic output
```
