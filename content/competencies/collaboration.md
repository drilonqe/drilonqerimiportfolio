---
title: "Collaboration"
draft: false
---

**Identify four different instances where you participated in collaborative work with your team as identified by specific commits, pull requests, and/or issue numbers on Github. These instances should not simply be "committing code" but situations that required back and forth with your peers, e.g., a substantial bug or a code review. You should have one instance each of (1) filing and/or resolving a bug, (2) filing a pull request, and (3) performing a code review of a pull request.**

### Identify the work you did in each of these instances.

One example of collaboration

{{< figure src="/drilonqerimiportfolio/images/Collaboration1.png" alt="Collaboration" >}}

**Instance 1**

- One collaboration instance I was part in in was a code review where I commented on the way major requirements and prerequisites were being represented. In the pull request, I noticed that some of the prerequisite and requirement logic was still being hardcoded for the Computer Science major. I commented that we should try to have a more universal way of defining majors, so that when we add more majors later, we do not have to rewrite the server logic every time, which we used later on when adding more majors


**Instance 2**

- Another instance was  another PR, where we did “UI improvement and major requirements structure update.” This pull request was about changes to the UI, and the major requirements display. It changed the frontend UI by adding a Grinnell header/banner and improving the requirements display and making the overall page look a bit better. My role in this collaboration was to look over the frontend side and look how the requirements should be shown to users. We talked about how we wanted to display the major requirements depending both on the frontend UI and the backend data structure. The hard part was not only making the page look better, but also making sure the requirement information was still understandable and useful, which Nahom did a great job with. I looked over the interface and also the requirements and made sure they show good and are easily readable / understandable from user point of view.

**Instance 3**

- Another collaboration instance was a bug we noticed with the Mathematics major. Our app was supposed to eventually place Linear Algebra, but Linear Algebra needed Calculus I and Calculus II as prerequisites. The problem was that those calculus courses were not being treated as requirements that the planner needed to place first, so the auto fill would get stuck and never reach Linear Algebra.

- My work here was noticing and explaining the issue from the frontend side. The problem was about how the requirement data and the auto fill logic worked together. The solution I suggested was to make sure the data included the right prerequisite path so the planner knew to place the earlier calc classes before trying to place the later classes like Linear Algebra. This was a good realization point that requirements and prerequisites are crucial to making the planner work like we want.

**Instance 4**

- Another collaboration instance was the MVP code that I committed. This was originally supposed to be done through a pull request, but I accidentally committed it directly instead (Oops). Even though it did not go through the normal PR process, it was still collaborative because we were all in a meeting room together when I was just finishing up on it. I was showing my teammates what I was adding, and we were discussing the code and the direction of the MVP as I was making changes. 

- The code here was the first working version of the planner in App.jsx. It created the eight semesters, added buttons for auto fill and resetting the plan, connected the page to SemestersTable and MajorRequirements, and included logic for placing courses into semesters. It also added warning messages for cases where a course could not be placed, like when a course was already planned, not offered in that semester, or missing a prerequisite. The main problem though was thinking about what MVP should include. Me and my group mates decided that making the planner workable for the CS major as a starting point was sufficient enough. Apart from all of this, I learned from this that even if we are discussing code in person, it is still better to use a branch and pull request. Since I committed it directly, the collaboration was not recorded as clearly on GitHub.

---


### Describe the difficulties that necessitated communication with your peers in each instance.

Going through these instances, I notice that the biggest reason we had to communicate was that frontend, backend, and database work were all connected to each other, and since we all were interchaning on what we work in, we needed good communication.

For Instance 1, the difficulty was that some prerequisite and requirement logic was still too 'hardcode'-ish to the Computer Science major. I needed to talk with my groupmates about this since it would affect how we would add more majors later. 

For Instance 2, the difficulty was making the requirements display both  look good and also concise and convey what we want to. The UI could look good, but if the requirement information was confusing, then the page would not actually help the user. So we had to talk about how the frontend display should compliment the backend.

For Instance 3, the difficulty was the Mathematics major bug. The auto fill logic needed some revision, more on the database site, and changed the way we think about the database. We needed to make sure that courses that are needed to take upper level courses but are not on some major's requirement still should be prerequisites in our data. Since Linear Algebra needed earlier calculus courses, but those courses were not being taken (since technically not required), the plan could get stuck. This required communication because the issue was in the way we thought about prerequisites that are not in the major and needed to think about the future cases we might encounter that.

For Instance 4, the difficulty was deciding what we place in the MVP. We had a lot of ideas, but we needed to choose what was "good enough" for a first version. We talked through this as a group and decided that getting something that works for the CS major was a good starting point.

---

### Did you encounter any difficulties in collaboration with team during these instances? If so, how did you resolve those difficulties?

Since each part like frontend, backend and data depended on each other, then it was a bit difficult to be on the same page concurrently. We resolved this by talking through the problems together and checking what each side needed. This was a big portion of what our meetings during the week were used. Another difficulty that I had was that we were still learning the tools while we were building the project. So tasks just took a lot more time than expected and when we made changes that took us back even more. We resolved this by being focused more on getting something that works, then we build on top of that.

---