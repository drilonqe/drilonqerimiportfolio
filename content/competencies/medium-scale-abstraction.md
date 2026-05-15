---
title: "Medium-scale Abstraction"
draft: false
---


### Sample Location

Repository: `4yearplanner`

Files:
- `App.jsx`

Lines:
- `229-312`
---

### Code Sample

```javascript
function canPlaceCourse(plan, semesterIndex, code) {
    const normalizedCode = normalizeCourse(code);
    const course = courseMap[normalizedCode];
    if (!course) return false;

    const term = getTermFromSemesterName(plan[semesterIndex].name);
    const completedBefore = getCompletedBeforeSemester(plan, semesterIndex);
    const currentSemester = getCoursesInSemester(plan, semesterIndex);

    if (isCourseAlreadyPlanned(plan, normalizedCode)) return false;
    if (course.offered?.length && !course.offered.includes(term)) return false;

    const rule = course.registrationRule;
    if (
      rule?.minSemesterIndex !== null &&
      rule?.minSemesterIndex !== undefined &&
      semesterIndex < rule.minSemesterIndex
    ) {
      return false;
    }

    if (
      rule?.minPriorCoursesCount &&
      countPriorCoursesMatchingRule(completedBefore, rule) <
        rule.minPriorCoursesCount
    ) {
      return false;
    }

    const isFirstYear = semesterIndex <= 1;
    const currentSemesterCourses = plan[semesterIndex].courses
      .filter(Boolean)
      .map(normalizeCourse);

    const dept = normalizedCode.match(/^[A-Z]+/)?.[0] ?? "";
    const sameDeptCourses = currentSemesterCourses.filter(
      (c) => c.match(/^[A-Z]+/)?.[0] === dept,
    );

    if (isFirstYear) {
      // First year: max 1 per dept. Exception: CSC-208 may share a semester
      // with one other CSC course (e.g. CSC-161 + CSC-208 in Spring 1st Year).
      if (normalizedCode.startsWith("CSC")) {
        const has208Already = sameDeptCourses.includes("CSC208");
        const isAdding208 = normalizedCode === "CSC208";
        if (has208Already || isAdding208) {
          if (sameDeptCourses.length >= 2) return false;
        } else {
          if (sameDeptCourses.length >= 1) return false;
        }
      } else {
        if (sameDeptCourses.length >= 1) return false;
      }
    } else {
      if (sameDeptCourses.length >= 2) return false;
    }
    const prereqGroups = course.prerequisiteGroups || [];

    // prevent high-level courses from appearing too early.
    // Only applies when no specific prerequisites and no specific min_semester_index.
    const hasExplicitMinSemester =
      rule?.minSemesterIndex !== null && rule?.minSemesterIndex !== undefined;
    if (prereqGroups.length === 0 && !hasExplicitMinSemester) {
      const courseNum = getCourseNumber(normalizedCode);
      if (courseNum >= 300 && semesterIndex < 4) retu4rn false;
      if (courseNum >= 200 && semesterIndex < 2) return false;
    }

    for (const group of prereqGroups) {
      const isSatisfied = group.options.some((prereq) => {
        const normalizedPrereq = normalizeCourse(prereq);
        return (
          completedBefore.has(normalizedPrereq) ||
          (group.canBeCorequisite && currentSemester.has(normalizedPrereq))
        );
      });

      if (!isSatisfied) {
        return false;
      }
    }

    return true;
  }
```


  
---

### My Contribution

I contributed to writing the function `canPlaceCourse`. For the parts that were a bit easier and simpler, so checking if a course is already in the plan, checking if it's offered in the right term, and going through prerequisites, I wrote the code directly there. For the harder and more complicated parts I used Claude to help me. Now, to be specific, AI helped me with the level-based check that prevents 300-level courses from appearing too early, and with the logic in countPriorCoursesMatchingRule that counts how many prior courses match a department and number range, and also the code that extracts the department prefix from a course code so lines where I used `(/^[A-Z]+/)` . I was reviewing everything what AI gave to me and made sure that it was right but it was helpful to get suggestions from Claude and help towards implementing the function.

---

### What functionality does this code abstract away?

`canPlaceCourse` abstracts the rules that determine whether a course can in a valid way go into a specific semester spot. So this function checks if the course has been placed somewhere else in the plan, if it is offered that Semester (as we know some courses are only Fall or Spring), checks whether the student is taking a 300 level in first year(not really possible), if the prereqs are satisfied and including the cases where we have corequisites. So this process is all behind the scenes, and the autofill simply call `canPlaceCourse` and get a boolean answer back.

---

### How does it mechanically achieve abstraction?

The function achieves abstraction in two ways. Firstly, we have checks that return false if something is wrong so these checks are all independent from each other. And the other way is that it uses some smaller helpers to do the data stuff instead of cramping everything in one place. So the functions like `getCompletedBeforeSemester` which is used to get courses already taken, `getCoursesInSemester` to get what we have in current semester or also something like `normalizeCourse` to make sure we are consistent with names and cases like CSC-151 and csc151 will be treated as the same thing. So `canPlaceCourse` uses all these results together and is more of like some checklist instead of doing all in one and having a big not understandable function.

---

## What purpose does this abstraction serve in the larger program?
`canPlaceCourse` is the function in the code which we check with if we can place a course in a certain box of a semester. This is important since the auto-fill will check before it places any course in a slot, the manual type box checks it when the user types the course, and there is another function that gets the error and shows it in the UI to let the user know what went wrong. Without this abstraction, we would need to like build the rules for each function separately, and anytime some rule changed we would need to update it in multiple places which is not ideal.
