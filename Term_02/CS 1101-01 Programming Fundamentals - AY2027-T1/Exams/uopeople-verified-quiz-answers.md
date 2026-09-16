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
