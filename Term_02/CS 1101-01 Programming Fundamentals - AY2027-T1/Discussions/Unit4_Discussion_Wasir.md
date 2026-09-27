# Discussion Forum Unit 4: Tracking Fitness Goals with Functions

**Posted by:** S M Wasir Jayed Rafi
**Course:** CS 1101-01 — Programming Fundamentals (AY2027-T1)

## Question 1: Designing Custom Functions

A function is a named block of code that runs a specific task whenever it's called, and it can take in data through parameters and hand back a result through a `return` statement (Mohbey & Acharya, 2023). For the friend's fitness tracker, the repeated blocks described in the prompt — weekly averages, checking whether a daily goal was hit, and printing a performance summary — are exactly the kind of code a function is meant to replace, since each one runs the same logic on different numbers every day rather than needing its own written-out block (Programming with Mosh, 2018).

I would break the program into four small functions instead of one large one, since Mohbey and Acharya (2023) note that splitting long programs into functions based on what each part actually does makes the code easier to organize, test, and reuse:

```python
STEP_GOAL, CALORIE_GOAL, MINUTE_GOAL = 10000, 500, 30

def log_day(weekly_totals, steps, calories, minutes):
    """Add one day's activity into the shared weekly_totals dict."""
    weekly_totals["steps"] += steps
    weekly_totals["calories"] += calories
    weekly_totals["minutes"] += minutes
    return weekly_totals

def calculate_weekly_average(weekly_totals, days_logged):
    """Return average steps, calories, and minutes so far this week."""
    return {key: total / days_logged for key, total in weekly_totals.items()}

def check_goals_met(steps, calories, minutes):
    """Return which of today's three goals were met, as booleans."""
    return {"steps": steps >= STEP_GOAL,
            "calories": calories >= CALORIE_GOAL,
            "minutes": minutes >= MINUTE_GOAL}

def display_summary(day_number, steps, calories, minutes, goals_met):
    """Print a formatted summary for one day."""
    print(f"Day {day_number}: {steps} steps, {calories} cal, {minutes} min")
    for goal, met in goals_met.items():
        print(f"  {goal} goal {'met' if met else 'not met'}")
```

`log_day()` takes the running totals plus today's three numbers and returns the updated totals; `calculate_weekly_average()` takes those totals and a day count and returns a dictionary of averages; `check_goals_met()` takes today's numbers and returns booleans; `display_summary()` takes the day's numbers and prints them, returning nothing.

## Question 2: Local vs. Global Variables

A local variable only exists inside the function where it's created and disappears once that function finishes, while a global variable is created in the main body of the program and can be read from anywhere (Mohbey & Acharya, 2023). In the tracker above, `steps`, `calories`, `minutes`, and `goals_met` should stay local — each only matters for the one day being processed, so keeping them local prevents one day's numbers from leaking into the next.

`weekly_totals`, on the other hand, needs to persist and update across every call, which is the "shared without overwriting or duplicating" problem the assignment describes. Rather than declaring it `global` and reassigning it inside each function, I pass the dictionary in as an argument and return the updated version; since dictionaries are mutable, `log_day()` can update it in place without needing the `global` keyword at all. Bencini (2025) points out that reassigning a variable inside a function using the same name as an outer-scope variable just creates a new local variable that shadows the original rather than updating it — so if `weekly_totals` were declared global and a function accidentally did `weekly_totals = {...}` instead of updating keys, the outer variable would silently stop being touched. Passing it explicitly avoids that trap. The only genuinely global values here are `STEP_GOAL`, `CALORIE_GOAL`, and `MINUTE_GOAL`, since they're constants that never change and every function needs to read them.

## References

Bencini, N. (2025, March 4). *Variable shadowing in Python*. Medium. https://medium.com/@nicbencini/variable-shadowing-in-python-cfc5457a67c3

Mohbey, K. K., & Acharya, M. (2023). Functions. In *Basics of Python programming: A quick guide for beginners* (pp. 40–45). Bentham Science Publishers.

Programming with Mosh. (2018, November 6). *Python functions | Python tutorial for absolute beginners #1* [Video]. YouTube. https://www.youtube.com/watch?v=u-OmVr_fT4s
