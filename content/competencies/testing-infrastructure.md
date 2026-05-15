---
title: "Testing Infrastructure"
draft: false
---


**Identify relevant components from your development infrastructure (IDE, build, etc.) that you use to test your project.** 

For testing, we used Vitest, npm scripts, and a Makefile. So we added the  Makefile so that PM or anyone in the group can just run make test without remembering the npm command, and it is a 1-click so it runs everything at once.


### How have you automated your tests so that they both take "1-click" to run and run automatically as part of build validation.

We made testing one command by adding make test. That command runs all the tests together. We also added make coverage for checking test coverage. This makes the testing easier because everyone can run the same command.

We also added a GitHub Actions workflow. This means that when code is pushed or when there is a pull request, GitHub will run npm test. I used AI to help me understand how to write the GitHub Actions file because I had not really worked with workflow files before but I thought that it would be very useful for our project. I checked the result with my teammates and made sure it was what we wanted.


---

### Describe a specific occurrence in which your testing infrastructure saved you and/or your team work?

One place this helped was with testing SemestersTable. Since this is where all users interact with the semester course slots, it is very easy to accidentally break something when changing the UI. Since we had these tests, we could check that the everything was still working as we wanted without having to do the manual labor of checking every time.

The GitHub Actions we added later on also helped because tests now run automatically. So if someone pushes a change that breaks the tests, GitHub can catch it before we assume everything works. This saved time because we did not have to rely only on remembering to test manually. If we decide to move forward with the project and improve it even more, this is going to help a lot.


---



