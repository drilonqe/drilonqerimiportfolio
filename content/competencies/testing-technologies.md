---
title: "Testing Technologies:"
draft: false
---


**Identify a portion of your test suite that utilizes advanced testing tools or techniques.**


### What advanced testing tool or technology did you employ in your code?

For advanced testing, I used Playwright, as PM advised me. Playwright as defined is an end to end testing tool which is a method of validating an app's workfrom start to finish, simulating realistic user scenarios. I had never used Playwright before so I used Claude Code to help me set up the testing suite and explain what the code was doing. As I was working wiht AI to do the tests, I was trying to understand how tests in Playwright open the page, how they click buttons, find text, and also mimic API responses.

---

### What did this tool/technology validate in your program?
Playwright tests checked that the page loads, that the Grinnell College header appears, and that the course table shows up. They also checked that all 8 semesters appear. The tests also checked user interactions. So one example would be that it tested that clicking + Add course opens the department dropdown, that choosing CSC only shows CSC courses, and that selecting a course actually puts it into the semester slot. They also tested that the Reset Plan button clears added courses, that Check Requirements updates the requirements panel, and that switching majors resets the plan. The tests used fake courses, fake majors, and fake requirement data to do extensive testing.

Here are the 17 tests that passed:

| # | Test |
|---|------|
| 1 | Grinnell College name shows in the header |
| 2 | Shows the 4-Year Planner label in the header |
| 3 | Loads the course table after data comes in |
| 4 | All 8 semesters show up |
| 5 | Clicking an empty slot opens the department dropdown |
| 6 | Can pick a department from the dropdown |
| 7 | Only CSC courses appear after picking CSC |
| 8 | Selecting a course closes the dropdown and shows the course id |
| 9 | Reset Plan button is visible |
| 10 | Check Requirements button is visible |
| 11 | Auto-Fill button is visible |
| 12 | Clicking Reset Plan clears any added courses |
| 13 | Major requirements panel heading shows up |
| 14 | Clicking Check Requirements shows the requirements status |
| 15 | Requirement blocks are listed in the panel |
| 16 | Major dropdown shows Computer Science by default |
| 17 | Switching the major resets the plan |

**17 / 17 passed in 4.5s**

---

### How effective was it in this task?

Playwright was pretty effective because it tested the app in the same way a user would actually use it as per end to end testing principles. So, it opened the planner page, clicked buttons, selected dropdown options, checked that the page changed correctly and a bunch of other things that a user would do to make sure that we have no hiden bug. When I ran the test suite, all 17 tests passed in about 4.5 seconds, so it was also very fast.

---

### In what contexts did you envision yourself utilizing this tool/technology in the future?

I would use Playwright again for web apps where user action is important. So if I was building a webApp that the users would interact with, I would want tests that actually click through the page like a real user. But that is the full extent. I do not think I would use it for small functions because I can just use unit testing for that.

---
