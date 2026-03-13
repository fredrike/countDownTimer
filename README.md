# Work Time Countdown Widget

[![pages-build-deployment](https://github.com/fredrike/countDownTimer/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/fredrike/countDownTimer/actions/workflows/pages/pages-build-deployment)

**Live demo:**
https://fredrike.github.io/countDownTimer/

A configurable countdown timer that measures **remaining working time** until a specified deadline.
Designed to run as a **single static HTML file**, it can be deployed on GitHub Pages, embedded as a widget, or installed as a Progressive Web App (PWA).

Repository:
https://github.com/fredrike/countDownTimer/

---

# Features

## Working-time countdown

The timer can calculate time remaining based on:

* Custom working hours
* Multiple work segments per day (e.g., morning + afternoon with lunch)
* Weekends excluded
* Optional exclusion of Swedish public holidays

Example work schedule:

```
08:00–12:00
13:00–17:00
```

---

## Flexible display formats

Supported output formats:

```
months, weeks, days
weeks, days, hours
weeks, days
days, hours, seconds
days, hours
hours, seconds
```

---

## Shareable timers via URL

Configuration is stored in the URL hash (`#`).
This allows timers to be shared with a direct link.

Example:

```
https://fredrike.github.io/countDownTimer/#widget=true&end=2026-03-31T17:00&s1=08:00&e1=12:00&s2=13:00&e2=17:00&holidays=true&format=wdh
```

---

## Widget mode

When `widget=true` is present in the URL:

* Configuration panel is hidden
* Timer behaves like a compact dashboard widget
* Suitable for embedding or installing as a PWA

Example:

```
#widget=true
```

---

## Auto-scaling display

The timer text automatically scales to fill the available window space, making it readable in:

* small widgets
* embedded iframes
* full-screen displays

---

## Persistent settings

User preferences are stored locally using:

```
localStorage
```

Priority order when loading settings:

1. URL hash parameters
2. localStorage
3. default values

---

## Swedish holiday support

Optional exclusion of Swedish public holidays including:

* New Year's Day
* Epiphany
* Good Friday
* Easter Monday
* Labour Day
* Ascension Day
* Pentecost
* National Day
* Midsummer Eve
* All Saints’ Day
* Christmas Day
* Boxing Day

Holiday calculations are performed locally (no external API required).

---

# Configuration Parameters

All parameters are optional and provided via URL hash.

| Parameter  | Description                                 |
| ---------- | ------------------------------------------- |
| `end`      | Deadline datetime                           |
| `s1`       | Work segment 1 start                        |
| `e1`       | Work segment 1 end                          |
| `s2`       | Work segment 2 start                        |
| `e2`       | Work segment 2 end                          |
| `fullDays` | Count 24-hour days instead of work schedule |
| `holidays` | Exclude Swedish holidays                    |
| `format`   | Display format                              |
| `widget`   | Hide configuration UI                       |

Example:

```
#end=2026-03-31T17:00&s1=08:00&e1=12:00&s2=13:00&e2=17:00&holidays=true&format=wdh
```

---

# Deployment (GitHub Pages)

This project is designed to run as a **static site**.

Steps:

1. Fork or clone the repository
2. Ensure `index.html` is in the repository root
3. Enable GitHub Pages

```
Settings → Pages → Deploy from branch → main
```

Your site will be available at:

```
https://fredrike.github.io/countDownTimer/
```

---

# Embedding as a Widget

The timer can be embedded on other pages using an iframe.

Example:

```html
<iframe
src="https://fredrike.github.io/countDownTimer/#widget=true&format=dh"
width="320"
height="120"
style="border:0">
</iframe>
```

---

# Local Development

No dependencies or build tools are required.

Simply open:

```
index.html
```

in a browser.

---

# Example Timer Configurations

Standard Swedish work schedule:

```
#end=2026-03-31T17:00&s1=08:00&e1=12:00&s2=13:00&e2=17:00&holidays=true&format=wdh
```

Continuous countdown:

```
#fullDays=true&end=2026-03-31T17:00&format=hs
```

Compact widget:

```
#widget=true&format=dh
```

---

# License

MIT License
