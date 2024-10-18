## Input Limitations

- All builds cap input length at 10 digits.
- Most builds allow non-numeric inputs (letters, emojis, special characters) but fail to handle them properly.

## Number Handling

- Most builds handle large numbers correctly, except Build 7 which consistently returns 0.
- Negative numbers are generally handled correctly, again with the exception of Build 7.
- Spaces within numbers cause errors across all builds.
- Empty inputs are incorrectly processed, returning 0 instead of an error.
- Commas in numbers are not allowed and cause errors.

## Decimal Handling

- Most builds have precision issues with decimal multiplication, returning results like 1.2000000000000002 instead of 1.2.
- Build 4 only handles integers, truncating decimal results.
- Recurring decimals from division are not handled ideally by any build.

## Rounding

- Rounding is inconsistent across builds, with a tendency to floor results rather than round properly.

## Zero Handling

- Multiplication by zero is correctly handled across all builds.
- Division by zero causes issues in most builds, with Build 6 returning "Infinity" and Build 8 incorrectly returning 0.

## Build-Specific Issues

- Build 7 has severe calculation issues, often returning 0 or incorrect results for basic operations.
- Build 2 concatenates string inputs instead of throwing an error in some cases.
- Builds have inconsistent error messages for invalid inputs.

## Error Handling

- Error messages are not standardized across builds.
- Some builds (like Build 1) attempt to calculate with invalid inputs, returning NaN.
- Others (Builds 2-8) provide error messages, but these are not always consistent or informative.

## Operator Handling

- Most builds handle basic arithmetic operators correctly, with the notable exception of Build 7.
- Build 7 seems to have a fundamental flaw in its calculation logic across all operations.