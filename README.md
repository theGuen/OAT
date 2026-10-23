# Octal Absolute Time (OAT)

**Octal Absolute Time (OAT)** is an alternative timekeeping system that divides a solar day into `100₈` (64 decimal) ticks, with each tick divided into `100₈` (64 decimal) moments.

OAT counts time from a fixed epoch and uses octal (base 8) notation throughout. It has no time zones or daylight saving time: the same OAT timestamp applies everywhere on Earth.

## How It Works

An OAT timestamp has three parts:

`Day · Tick · Moment`

| Unit | Octal size | Decimal equivalent | Traditional time |
| --- | --- | --- | --- |
| Day | `1` | 1 solar day | 24 hours |
| Tick | `1/100₈` day | 1/64 day | 22 min 30 sec |
| Moment | `1/100₈` tick | 1/4096 day | ≈ 21.1 seconds |
| Week | `10₈` days | 8 days | — |

All OAT values are written in octal unless explicitly marked as decimal.

## Core Concepts

- **Epoch:** Day `0 · 00 · 00` is the starting point of OAT. The prototype uses 1 January 2000 at 12:00 UTC, approximately 64.184 seconds before the astronomical instant J2000.0, which is defined as 12:00 Terrestrial Time (TT).
- **One global clock:** OAT has no time zones or daylight saving time. The day rolls over at 12:00 UTC in the current implementation.
- **Machine form:** A timestamp can be written as a single octal number, with the day before the radix point and the tick and moment after it. For example, `23100.4000` represents Day `23100`, Tick `40`, Moment `00`, all in octal.
- **Time arithmetic:** When timestamps are represented consistently, their difference gives the elapsed time. Octal notation must be interpreted correctly when performing calculations.
- **Weekday:** The last octal digit of the day count identifies one of eight weekday positions, numbered `0` through `7`.

## Weeks, Years, and the Moon

### Weeks

An OAT week lasts `10₈` days, or eight solar days. Its weekday positions are numbered `0` through `7`, without traditional weekday names.

The eight-day cycle has a historical parallel in the Roman *nundinal cycle*, an eight-day market cycle.

### Years and Seasons

The year is not a native OAT unit. A block of `1000₈` days equals 512 decimal days, which does not match Earth's orbital period of approximately 365.24 days.

Rather than forcing a fixed-length year into the system, equinoxes and solstices provide seasonal reference points.

### The Moon

The optional lunar ring displays lunar information alongside OAT, including moonrise, moonset, and upcoming phases such as the new moon, quarter moons, and full moon.

This allows lunar events to be viewed within the same time system without making the Moon a required part of OAT.

## The Interface

The OAT dial combines absolute time, daily routines, and local astronomical information.

- **Daylight arc:** Shows the time between local sunrise and sunset.
- **Seasonal change:** Arrows indicate whether sunrise and sunset are shifting earlier or later, with their lengths representing the rate of change.
- **Seasonal markers:** Equinoxes and solstices are highlighted as they approach.
- **Body clock:** Divides the day into a recurring routine, including sleep, post-wake focus, high-performance time, and wind-down periods.
- **Lunar ring:** Can be enabled to view lunar events alongside the daily dial.
- **Legacy time:** Displays conventional UTC and local time for comparison with OAT.

## The Verdict

OAT is probably not useful at all.

But it tries to answer some important questions:

- When is day, and when is night?
- When does the livestream start if it says 18:30 AKDT?
- Why do I have to adjust the clock instead of getting up when I wake up?
- Why can't I do sports every other day without missing Monday's yoga class?
- Why do I not have twelve fingers?
- Why is winter such a depressing word when the light is already coming back?

- Why should a clock tell us only what time it is, rather than help us understand where we are in the day?

OAT doesn't claim to have all the answers. It probably creates a few new problems of its own.

But maybe a clock can be more than a device for making us late, scheduling meetings, and reminding us when to be somewhere else.

Maybe it can help us see time differently.

That's what OAT is trying to do.

## Try It

**[Open Octal Absolute Time](https://theguen.github.io/OAT/)**

Explore the OAT dial, compare octal time with conventional clocks, and see how daylight, daily routines, and lunar events fit into a single global time system.
