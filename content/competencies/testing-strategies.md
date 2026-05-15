---
title: "Testing strategies:"
draft: false
---


**Identify a component of your project that you were responsible for testing.**

One component I was responsible for testing is SemestersTable, which lives in src/components/semestersTable.jsx. This is, I would say, very important to the frontend end of our WebApp since it renders the table we see, manages the dropdowns when you click an empty slot, and lets a student pick a course. I was in charge of implementing this and I added some testing while I was doing so as well.


### According to code coverage tools, what aspects of this component are covered with tests? What kinds of tests are they?


I ran make coverage and these are the numbers I got for semestersTable.jsx:
- Statements: 76%
- Branches: 78%
- Functions: 100%
- Lines: 81%
- Lines not covered: 39-45

{{< figure src="/drilonqerimiportfolio/images/TestingSuite.png" alt="Testing Suite" >}}

The functions being at 100% means every function in the component got called at least once when the tests ran, which I thought was good since we manage to put everything there. The rest of the numbers show that the main things a student would actually do are covered, so like clicking on an empty slot, picking a department from the dropdown, selecting a course, and also the case where a course gets rejected and the dropdown stays open.

---

### For code that is not covered by tests, why did you not cover them?

The uncovered lines are the part where if a student picks "Custom course" from the dropdown,then a window is shown asking them to type a course in manually. I did not write a test for that because I honestly did not know how to write a test for that. All my other tests just click things and check what shows up, but a this was different and I could not figure out how to make that work in the testing suite, so I just left it out.


---



