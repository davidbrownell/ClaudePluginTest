---
name: math-tens
description: Performs basic arithmetic (add, subtract, multiply, divide) and rounds results to the nearest multiple of 10. Use for calculations that need clean multiples of 10.
argument-hint: [operation] [number1] [number2]
---

# Arithmetic with Multiples of 10

Perform basic arithmetic operations and round the result to the nearest multiple of 10.

## Input

The operation and numbers are provided as: `$ARGUMENTS`

Expected format: `[operation] [number1] [number2]`

## Supported Operations

| Operation | Aliases | Example |
|-----------|---------|---------|
| Addition | `add`, `+` | `add 15 27` |
| Subtraction | `subtract`, `sub`, `-` | `subtract 100 55` |
| Multiplication | `multiply`, `mul`, `*` | `multiply 6 7` |
| Division | `divide`, `div`, `/` | `divide 100 3` |

## Rounding Logic

Results are rounded to the nearest multiple of 10 using standard rounding:
- 0-5 rounds down (44 → 40)
- 6-9 rounds up (45 → 50, 47 → 50)

Formula: `round(result / 10) * 10`

## Output Format

Show both the raw calculation and the rounded result:

```
Operation: [operation] [num1] [num2]
Raw result: [exact result]
Rounded to nearest 10: [multiple of 10]
```

## Examples

| Input | Raw Result | Rounded Result |
|-------|------------|----------------|
| `add 23 19` | 42 | 40 |
| `subtract 100 55` | 45 | 50 |
| `multiply 7 8` | 56 | 60 |
| `divide 100 3` | 33.33... | 30 |
| `add 5 0` | 5 | 10 |
| `multiply 10 10` | 100 | 100 |

## Edge Cases

- **Division by zero**: Return an error message explaining division by zero is undefined
- **Missing arguments**: Ask the user for the complete operation (operation, number1, number2)
- **Invalid operation**: List the supported operations and ask user to try again
- **Non-numeric input**: Ask the user to provide valid numbers
- **Negative results**: Round toward zero for negative numbers (-44 → -40, -45 → -50)
