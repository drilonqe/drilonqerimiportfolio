---
title: "Medium-scale Architecture"
draft: false
---

### Sample Location

Repository: `4yearplanner`

Files:

- `App.jsx`,

### Code Sample

```javascript
// App.jsx lines 36-61
 useEffect(() => {
    async function loadPlannerData() {
      try {
        const [coursesResponse, majorsResponse] = await Promise.all([
          fetch("/api/courses"),
          fetch("/api/majors"),
        ]);

        if (!coursesResponse.ok || !majorsResponse.ok) {
          throw new Error("Could not load planner data from SQL.");
        }

        const [courses, majorsList] = await Promise.all([
          coursesResponse.json(),
          majorsResponse.json(),
        ]);

        setCoursesData(courses);
        setMajors(majorsList.majors);
      } catch (error) {
        setLoadError(error.message);
      }
    }

    loadPlannerData();
  }, []);

  // App.jsx lines 919 - 924
          <SemestersTable
            semesters={semesters}
            onCourseSelect={handleManualCourseSelect}
            courseOptions={coursesData?.courses || []} // added line so it doesn't break when coursesData is null during loading (Autosuggested)
          />
```

---

### My Contribution

I contributed to writing the frontend side of the architecture in App.jsx. For the parts that were a bit easier and simpler, like setting up the state variables for majors, selected major, courses data, and load errors, and then connecting that data back into the planner page, I worked on those parts independently. Then I had to look online or use Claude to explain the useEffect structure, the async/await, the Promise.all, and also try/catchwhen loading data from /api/courses and /api/majors. It was a good way to learn more about react features in general and knowing how to load data in ways that I have not really worked much before.
Very helpful was React Documentation https://react.dev/reference/react/useEffect and youtube videos that I cannot find right now. 

---

### What architectural pattern does your program employ?

Our web-app  uses a frontend and a backend. The frontend is the React website that the user interacts with, and the backend is what provides the course and major data through API routes. We chose this setup because the planner needs to display information to users, but it also needs to get the classes data from somewhere else instead of just hardcoding everything directly into the page. We first did everything in one place, (during the MVP, there was backend logic in the frontend) which we changed a little bit.

---

### What components result from this pattern in your program?
The components that come from this pattern are the interface, the API and the data behind it. On the frontend we have like App.jsx and SemesterTable.jsx that are responsible for showing the 4year planner and the data behind it. On the backend, through API we have the courses, majors and major reqs which the frontend loads up and displays.

---

## What technologies and/or libraries make-up each of the components?
For the frontend, we used React with Vite and JavaScript. This is the part that builds the planner, handles the states, and lets the user like interact with the semester table. For the backend and data side, we used APIs and the data we have with SQL for courses and requirements, which allowed the planner to load the information instead of putting everything manually in the frontend.