---
title: "Infrastructure"
draft: false
---


**Identify relevant artifacts from the human-centered design process that address the following points:**



### What development tools did you use through process to help write code and automate the build/deployment process?

For development infrastructure, we used GitHub, VS Code, npm, Vite, React, ESLint, and a Node.js backend. VS Code was the main editor I used to write and debug code since it is what I work with most and I am used to it. 

For running and checking if everything is right the project, we used the scripts in package.json. The project has scripts like npm run dev for starting Vite frontend, npm run server for starting backend server, npm run build for building project, npm run lint for checking for errors, and so on. This helped make the project easier to run because we did not have to manually any command every time. For the build, we used Vite which made possible so that any change we made in the React code showed up in the browser instantly without having to restart anything. The app runs locally on our computers, even though I did try hosting the database on a cloud service so all teammates could share the same data, but in the end we decided to keep everything local because it was simpler.

---

### What is one specific problem (e.g., debugging and issue) that you encountered while writing code and how did your tools help or hinder your ability to address that problem?

One problem I ran into was like a path issue in React. I had some error where Vite could not resolve some importend component because the file name on the import did not match the actual file name and I quickly learned that React is very strict about file paths and needed to stay consistent so that I do not break the app. The tools helped because Vite  server gave me the feedback in the terminal that the import could not be resolved. That made it easier to search where  the problem was. At the same time, the tools also made this a little annoying because the error was not about the logic of my code, but about some naming issue. So tools are helpful but you need to read and understand the error first.


