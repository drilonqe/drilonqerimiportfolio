---
title: "Quality:"
draft: false
---


**Imagine that you were up for promotion and your case rests on the quality of your project's codebase. Provide an overall evaluation of its quality.**



 **In what ways does your codebase exemplify engineering excellence?**

**In what ways does it fall short? How would you address these issues if given more time?**

Overall, I think our code has ended in a good place for a semester-long student project, with us being the smallest group out of everyone and also considering that all three of us having to learn a lot of the technologies while building the project. It is definitely not perfect but I do think that it shows that we can make something big in the future if we put our mind to it. We started with some very small MVP where a lot of the logic was in the frontend, and then over time we moved to a way more organized structure which I am very happy about.

One strong aspect of our codebase is that we separated the frontend, backend, and data. The frontend is mostly responsible for showing the planner and handling user interaction, while the backend gets course and major data from SQL and sends it through API routes. This is better than hardcoding everything directly in the frontend because it makes the project easier to expand.

Another strength is that we moved toward a more general way of storing majors and their requirements. When we first did the MVP for CS, we simply hardcoded the requirements but as we moved on, we storded more requirement and prereqs in SQL, and adding majors would not need us to rewrite the same code everytime. This was good in the aspect of extending the project to multiple majors.

The project also shows quality because our  testing is good and the fact that we added a Makefile and GitHub Actions so tests can run more easily and automatically makes it more reliable than just looking at everything manually. 

I also think the UI improved a lot from the MVP. The original version worked, but it looked kind of like a bad prototype. Later, we improved the layout, buttons, contrasts, added a nice background and so on. Everything looked so much better and I actually wanted to try the website.

One weakness though is that  App.jsx still does too much for our webAPP. It handles a lot of the stuff like loadig the data, the state, course placement, the auto fill logic, warnings, major changes, and even more. It works, but it would be easier to understand for someone who looks at our code and easier to test if some of that logic was moved into smaller files. Maybe in the future we could have written helper files that lay out the jobs a bit more and are more clear to someone looking at our codebook. 

Another weakness is that the course and major requirement data can change every year. Right now, a lot of our data depends on what we manually put into the SQL files. That works for the project, but it would be hard to maintain long-term because Grinnell’s catalog changes over time. If a requirement changes on the course website, our planner could become outdated.

If we had more time, I would want to build some kind of scraper or importer that could pull updated course and requirement information from the Grinnell catalog website. Then we could update the database more automatically instead of manually editing SQL files every year. That would make the app more reliable and easier to keep current.

---
