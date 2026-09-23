---
inclusion: always
---

# UoPeople CS 1101 — Verified Answer Bank

Answers below are **confirmed by graded attempts**, not inferred, unless marked otherwise.

## Attempt log

| Attempt | Type | Score | Notes |
|---|---|---|---|
| 1 | Unit quiz (5 q) | 5/5 (100%) | All confirmed correct by user |

## Attempt 1 — question-by-question results

| # | Question (topic) | Answer given | Result |
|---|---|---|---|
| 1 | Which of the following is a Boolean value? (10 / True / 3.5 / "True") | True | CONFIRMED CORRECT |
| 2 | Float values do not contain decimals. (True/False) | False | CONFIRMED CORRECT |
| 3 | Programming is only used for developing web applications. (True/False) | False | CONFIRMED CORRECT |
| 4 | Which assignment operator adds and assigns at the same time? (+= / => / =+ / =) | += | CONFIRMED CORRECT |
| 5 | Which function converts a number to a string in Python? (int() / float() / bool() / str()) | str() | CONFIRMED CORRECT |

## Notes

- Basic Python fundamentals (data types, Boolean values, float vs int, assignment operators, type-conversion functions) — trust these directly if these exact questions/options reappear.
- Key distinctions to remember: `True`/`False` (bare, unquoted) = Boolean; `"True"` (quoted) = string. `+=` is the compound assignment operator for add-and-assign. `str()` converts numeric types to string; `int()`/`float()`/`bool()` convert to their respective types.


## Attempt 2 — Unit 2 quiz: Boolean logic & conditionals (5 q)

| # | Question (topic) | Answer given | Result |
|---|---|---|---|
| 1 | Which expression evaluates to True | `5 > 10 or 4 > 2` | CONFIRMED CORRECT |
| 2 | Output of `if x and y:` with x=5, y=0 | B | CONFIRMED CORRECT |
| 3 | Best check for number NOT between 10 and 20 inclusive | `not (num >= 10 and num <= 20)` | CONFIRMED CORRECT |
| 4 | Output of nested if/else with age=17 | Teenager | CONFIRMED CORRECT |
| 5 | Output of nested if with num=45, modulo checks | Valid Number | CONFIRMED CORRECT |

All 5/5 confirmed correct. Key reasoning:
- Short-circuit evaluation: `and`/`or` return one of the actual operands, not always `True`/`False` (e.g., `7 and 0` → `0`).
- `not (num >= 10 and num <= 20)` is the correct De Morgan's-style negation of an inclusive range check.
- Nested `if` statements evaluate outer condition first, then inner condition, printing based on the deepest matching branch.


## Attempt 3 — Unit 3 self-quiz: loops (5 q)

| # | Question (topic) | Answer given | Result |
|---|---|---|---|
| 1 | A while loop checks its condition after executing the body. (True/False) | False | CONFIRMED CORRECT |
| 2 | Which keyword is used in a Python for loop to iterate over a sequence? (to/from/in/over) | in | CONFIRMED CORRECT |
| 3 | How many times will the loop body execute for `for x in [3,1,4,1,5]:`? | 5 times | CONFIRMED CORRECT |
| 4 | Where is the condition checked in a while loop? (Before each iteration / Only when break appears / Only once at start / After each iteration ends) | Before each iteration begins | CONFIRMED CORRECT |
| 5 | Which scenario best suits a while loop? (fixed-length string / fixed numeric range / fixed-size list / read input until 'quit') | Read user input until the user types 'quit' | CONFIRMED CORRECT |

All 5/5 confirmed correct. Key reasoning:
- `while` loops are pre-check (condition tested **before** each iteration, including the first) — never post-check in Python (there is no do-while).
- `for x in sequence:` — `in` is a syntactic component of the for-statement, unrelated to the membership-test `in` operator.
- `for` loops over a list execute once per element, counting duplicates (5 elements → 5 iterations regardless of repeated values).
- `while` is the right choice whenever the number of iterations is unknown in advance (e.g., sentinel-controlled input loops); `for` suits fixed-size/known-length sequences and ranges.
