---
title: "Self-Learning"
draft: false
---


**Identify a portion of your tech tutorial that you developed.**


### Describe the technology that the tutorial addresses and how it fits into your project.
The technology I covered was how the frontend and backend communicate with each other.The main technologies I talked about were Node.js, API calls, and JSON. In our project, this matters because the frontend cannot just be some hardcoded course information. What we do instead is ask the backend for data like for the courses, majors, and major requirements, and whatever response we get we use to update the website the user sees. This fits directly into our project because all of the data we need is in the database, and the only way the frontend can get to that data is by making API calls to the backend.

---

### Evaluate how useful the tool was in your work. What were its strengths and weaknesses, especially in comparison with other tools you have used.

The API and JSON tools were useful because they enabled us to separate the frontend from the backend. The frontend does not need to know anything about the database. We simply ask the backend what we need and get a response. The strength of this is that we could each work on our own part without stepping on each other, so my groupmates could change how the database was set up (We did have to do this at some point after talking to PM) and as long as the JSON response looked the same, my frontend code did not break. But we needed to make sure the frontend and backend have a set structure of the JSON response, so that frontend knows how to use it and doesnt break.

---

### Identify one particular sticking point to using this technology that you would want your team to know about when adopting the tool and how you resolved it.
One sticking point was that when something went wrong, it was not always obvious whether the problem was in the frontend or the backend. For example, if the page did not show the courses correctly, the problem could have been in many places. So it could have been the React code, the API route, or the backend data. This was a bit more difficult than the smaller projects we usually do in CS class where most of the code is in one place. We resolved this by checking each component separately. So, check if backend was returning data then check if frontend is receiving it and displaying it correctly and so on.

