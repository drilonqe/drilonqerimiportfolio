---
title: "User Interface Design:"
draft: false
---


**Identify a portion of the user interface that you designed.**

I designed the semester tables, the buttons for Major selector, Auto-Fill, Check Requirements, Reset, and so on. My teammate designed the requirements tree below and added Grinnell College as a background.

### How does your design adhere to one or more of the principles of interaction design?
- My design uses visibility because the user can see all of the  8 semester plan in one place. This was important for our project because students are not only planning one semester at a time. They need to see how earlier semesters affect later semesters, especially with prerequisites and major requirements. This is crucial since we want important information to be visible instead of hidden behind too many different irrelevant structures.

- The design also uses affordance because the empty course slots say + Add course, which makes it clear that the user can click there to add something. The buttons like Auto Fill Remaining Plan, Check Requirements, and Reset Plan are also styled like buttons, so users can tell they are actions. This matters because students should not have to guess what parts of the page are interactive. When selecting a major, there is an arrow on the right that indicates that there is going to be a drop down of majors that the user can select from.

- Another principle is feedback. When users click a course slot, the interface changes and lets them select a department and course. When they click auto fill or check requirements, the plan and requirements update. If something is wrong, like a course missing a prerequisite, the app will show a warning. This helps the user understand that the app responded to their action. I think we did a good job of covering most edge cases in this way. Even when the user types a course, they will still get clear warnings if it is invalid.

- Finally, another principle that I think the UI I designed uses is structure. I had the planner be a 4-column grid for the four years of college, left to right, fall then spring, to kind of mimic what colleague self service has but in our own way. Inside each grid the courses stack top to bottom like a normal schedule. I also put the buttons in order of how often people would use them so the  red Auto Fill button is probably the most used one because that's the main use of our webApp, then Check Requirements is the next to it, since that is what you would normally use after filling, and then Reset on the end. My goal was for the UI to be clear without the user having any questions about it.
---

### What alternative designs did you consider (describe at least one) and why did the current design prevail, appealing to the principles of interaction design?

One alternative design we considered was showing the plan year by year instead of showing all eight semesters at once. In that version, the user would look at Year 1 first and then click an arrow to move to Year 2, Year 3, and Year 4. This would have made each screen less crowded, but that means that it would also limit some important information. The users would not be able to see what they took before or what they filled already.

Example that was also shown in prototyping:
{{< figure src="/drilonqerimiportfolio/images/Whiteboard-sketch.jpg" alt="Whiteboard Sketch" >}}


We decided not to use that design because our needfinding showed that students wanted planning information in one place. If we did that year by year design, then it would be harder to compare early and later semesters, especially for prerequisites.

We choose the current 8 semester grid because it was the way students think about a four year plan. And Instead of having to constantly move between years, the user can just look at the whole plan at once.

---

I also used WAVE to check the accessibility of the interface as per PM's advice. Before making changes, the WAVE score was lower and showed many contrast errors, small text alerts, and missing heading.

{{< figure src="/drilonqerimiportfolio/images/WebaimScoreWithoutEdit.png" alt="WebAIM Score Without Edits" >}}

After editing, the score went up by a lot, from 4.9 to 9.7. The main fixes were improving color contrast, making text easier to read, and adding a proper first level heading as it suggested.

{{< figure src="/drilonqerimiportfolio/images/WebaimAfterEditing.png" alt="WebAIM Score After Editing" >}}

So an interface that looked fine to me still had a lot of accessibility problems. Some gray text upon a gray background that initially looked okay to me, but WAVE advised that I need to make contrast higher, make text sizes bigger and such so the interface is easier to read.

My main goal was not to just change everything to get a higher score but to also make sure that whatever I am changing is still following the design principles we talked about above and in class. That is why I liked using WAVE.

--- 

### How the UI changed from the MVP

The UI changed a lot from the MVP version. In the MVP, the main idea was already there: eight semesters, course slots, and buttons for auto-fill, checking requirements, and resetting the plan. But visually, it was still very plain and looked more like a first working prototype.

In the later version, we kept the same structure because it worked well, but we made the interface cleaner and easier to read. We simply just made everything look cleaner and easier to see when using, which was basically just polishing the MVP design.

{{< figure src="/drilonqerimiportfolio/images/Grinnell 4 year planner MVP version.png" alt="Grinnell 4 Year Planner MVP" >}}
