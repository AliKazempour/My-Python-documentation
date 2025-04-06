# Working with Datetime in Python

**Datetime** in Python is a module that helps you work with dates and times. Whether you need to track when something happened, calculate time differences, or format dates for display, the `datetime` module has you covered.

---

## Table of Contents

1. [Introduction to Datetime](#1-introduction-to-datetime)
2. [Core Concepts of Datetime](#2-core-concepts-of-datetime)
   - [Date and Time Objects](#21-date-and-time-objects)
   - [Current Date and Time](#22-current-date-and-time)
   - [Formatting Dates and Times](#23-formatting-dates-and-times)
   - [Time Deltas](#24-time-deltas)
   - [Parsing Strings to Datetime](#25-parsing-strings-to-datetime)
3. [Syntax of Datetime](#3-syntax-of-datetime)
4. [Common Datetime Methods](#4-common-datetime-methods)
5. [Timezone Handling](#5-timezone-handling)
6. [Best Practices](#6-best-practices)
7. [Problems and Practice](#7-problems-and-practice)
8. [Summary](#8-summary)

---

## 1. Introduction to Datetime

Imagine you’re building an app that logs when a user signs up or schedules a reminder for next week. The `datetime` module lets you handle these tasks easily—getting today’s date, adding days, or displaying times in a friendly format like "March 14, 2025, 3:00 PM."

### Why Use Datetime?
- **Time Tracking**: Record events with precision.
- **Calculations**: Find differences between dates or add time.
- **User-Friendly**: Display dates and times in any format.
- **Automation**: Schedule tasks or check deadlines.

---

## 2. Core Concepts of Datetime

Let’s break down the essentials of the `datetime` module with relatable examples.

---

### 2.1 Date and Time Objects

- **Date**: Represents a day (year, month, day).
- **Time**: Represents a time (hour, minute, second).
- **Datetime**: Combines both date and time.

#### Detailed Explanation:
Think of `date` as a calendar page, `time` as a clock, and `datetime` as both together—like a timestamp on a photo.

#### Example 1: Basic Date and Datetime
```python
from datetime import date, datetime

my_date = date(2025, 3, 14)  # March 14, 2025
print(my_date)  # Output: 2025-03-14

my_datetime = datetime(2025, 3, 14, 15, 30)  # 3:30 PM
print(my_datetime)  # Output: 2025-03-14 15:30:00
```

#### Example 2: Accessing Parts
```python
from datetime import datetime

dt = datetime(2025, 3, 14, 15, 30)
print(dt.year)    # Output: 2025
print(dt.hour)    # Output: 15
print(dt.minute)  # Output: 30
```

---

### 2.2 Current Date and Time

- **Now**: Get the current date and time.

#### Detailed Explanation:
It’s like asking, "What time is it right now?"—useful for logging or real-time apps.

#### Example 1: Today’s Date
```python
from datetime import date

today = date.today()
print(f"Today is {today}")  # Output: Today is 2025-03-14 (assuming current date)
```

#### Example 2: Current Datetime
```python
from datetime import datetime

now = datetime.now()
print(f"Right now: {now}")  # Output: Right now: 2025-03-14 10:15:23.123456 (example)
```

---

### 2.3 Formatting Dates and Times

- **Formatting**: Turn dates/times into readable strings using `strftime`.

#### Detailed Explanation:
Think of it as styling a timestamp—like "03/14/25" vs. "Friday, March 14, 2025."

#### Example 1: Simple Format
```python
from datetime import datetime

now = datetime.now()
formatted = now.strftime("%Y-%m-%d %H:%M")
print(formatted)  # Output: 2025-03-14 10:15 (example)
```

#### Example 2: Friendly Format
```python
from datetime import datetime

dt = datetime(2025, 3, 14, 15, 30)
pretty = dt.strftime("%A, %B %d, %Y at %I:%M %p")
print(pretty)  # Output: Friday, March 14, 2025 at 03:30 PM
```

---

### 2.4 Time Deltas

- **Timedelta**: Add or subtract time from dates/times.

#### Detailed Explanation:
It’s like a time calculator—find tomorrow’s date or a deadline in 7 days.

#### Example 1: Add Days
```python
from datetime import datetime, timedelta

now = datetime.now()
one_week_later = now + timedelta(days=7)
print(one_week_later)  # Output: 2025-03-21 10:15:23.123456 (example)
```

#### Example 2: Time Difference
```python
from datetime import datetime, timedelta

start = datetime(2025, 3, 14)
end = datetime(2025, 3, 20)
difference = end - start
print(f"Days between: {difference.days}")  # Output: Days between: 6
```

---

### 2.5 Parsing Strings to Datetime

- **Parsing**: Convert a string (like "2025-03-14") into a `datetime` object using `strptime`.

#### Detailed Explanation:
It’s like reading a date from a form and turning it into something Python can work with.

#### Example 1: Basic Parsing
```python
from datetime import datetime

date_str = "2025-03-14"
dt = datetime.strptime(date_str, "%Y-%m-%d")
print(dt)  # Output: 2025-03-14 00:00:00
```

#### Example 2: Custom Format
```python
from datetime import datetime

date_str = "14-Mar-2025 15:30"
dt = datetime.strptime(date_str, "%d-%b-%Y %H:%M")
print(dt)  # Output: 2025-03-14 15:30:00
```

---

## 3. Syntax of Datetime

Basic usage:
```python
from datetime import date, datetime, timedelta

# Date
d = date(year, month, day)

# Datetime
dt = datetime(year, month, day, hour, minute, second)

# Timedelta
td = timedelta(days=1, hours=2)
```

---

## 4. Common Datetime Methods

| Method/Property | What It Does                          | Example Output         |
|-----------------|---------------------------------------|------------------------|
| `.today()`      | Current date                         | `2025-03-14`          |
| `.now()`        | Current date and time                | `2025-03-14 10:15:23` |
| `.strftime()`   | Format as string                     | `"03/14/2025"`        |
| `.strptime()`   | Parse string to datetime             | `2025-03-14 00:00:00` |
| `.year`, `.day` | Access components                    | `2025`, `14`          |

---

## 5. Timezone Handling

- **Timezone**: Use `pytz` for accurate timezone support (not built into `datetime` by default).

#### Detailed Explanation:
Timezones matter for global apps—3 PM in New York isn’t 3 PM in Tokyo.

#### Example 1: Basic Timezone
```python
from datetime import datetime
import pytz

tz = pytz.timezone("America/New_York")
ny_time = datetime.now(tz)
print(ny_time)  # Output: 2025-03-14 10:15:23.123456-04:00 (example)
```

#### Example 2: Convert Timezone
```python
from datetime import datetime
import pytz

ny_tz = pytz.timezone("America/New_York")
london_tz = pytz.timezone("Europe/London")
ny_time = datetime(2025, 3, 14, 15, 0, tzinfo=ny_tz)
london_time = ny_time.astimezone(london_tz)
print(london_time)  # Output: 2025-03-14 20:00:00+00:00 (example)
```

---

## 6. Best Practices

- **Import Specifics**: Use `from datetime import datetime` instead of `import datetime`.
- **Timezone Awareness**: Use `pytz` for apps needing global time.
- **Consistent Formatting**: Stick to standard formats (e.g., ISO: `YYYY-MM-DD`).
- **Error Handling**: Combine with `try-except` for invalid dates.
- **Avoid Overcomplication**: Use `timedelta` for simple math, not manual calculations.

---

## 7. Problems and Practice

### Problem 1: Birthday Countdown
```python
from datetime import datetime

birth_date = datetime.strptime(input("Enter birthday (YYYY-MM-DD): "), "%Y-%m-%d")
today = datetime.now()
difference = birth_date - today
print(f"Days until your birthday: {difference.days}")
```

### Problem 2: Event Scheduler
```python
from datetime import datetime, timedelta

event = datetime.now()
days_ahead = int(input("Schedule event in how many days? "))
event_date = event + timedelta(days=days_ahead)
print(f"Event scheduled for: {event_date.strftime('%Y-%m-%d %H:%M')}")
```



---

## 8. Summary

| Concept               | What It Does                              | Example                       |
|-----------------------|-------------------------------------------|-------------------------------|
| **Date/Time Objects** | Represent dates and times                 | `2025-03-14 15:30:00`         |
| **Current Time**      | Get now or today                          | `datetime.now()`              |
| **Formatting**        | Display dates/times as strings            | `"Friday, March 14, 2025"`    |
| **Time Deltas**       | Add/subtract time                         | `now + timedelta(days=7)`     |
| **Parsing**           | Convert strings to datetime               | `strptime("2025-03-14")`      |

---

### Teaching Tips
- **Start Simple**: Use `date.today()` and basic formatting first.
- **Build Up**: Add `timedelta` and timezones later.
- **Hands-On**: Have students calculate their age in days or schedule a fake event.
- **Visuals**: Show a calendar or clock to explain components.
- **Real-World**: Tie to apps (e.g., reminders, logs).


