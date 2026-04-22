# Stack-Overflow-X86-Project

# Description
Demonstrates passing parameters using registers and stack, performing arithmetic operations and running a loop to keep
a running sum.

68K Source Code
This program:
Runs a loop 3 times
Each time:
  Prompts the user for two numbers
  Adds them using a subroutine (REGISTER_ADDER)
  Adds the result to a running total
After the loop, prints the final sum

# Vulnerability 1
If the string at PROMPT, RESULT, FINAL_RESULT, CRLF, ERR_MSG is not properly terminated, the TRAP will continue reading past the intended data.
Creating a VALIDATE_A1 to check if the address register has been tampered with.

# Vulnerability 2
No input Validation
It accepts anything. No check for: Overflow, negative numbers, non-numeric input

# Vulnerability 3
Arithmetic Overflow
No overflow detection and could wrap around silently

# Vulnerability 4
No Stack Protection
Return address is pushed to stack
RTS Pops it
