Code Tracing Tables
===================

This web app aims to help students learn to read and understand code by having them keep track of variables as a program executes. The app gives corrective feedback and can support different programming languages. Because the answers are determined statically and the Programming Language Under Practice (PLUP) is not being actually executed, the implementation of grading and giving feedback stays straightforward.

**PLUPs implemented**
 - Python3
 

**Underlying Technology**
 - HTML
 - CSS
 - JS (no external libraries)
 
Design
------
A JSON list of questions and answers is made for each PLUP. These are checked in under the `plup` subdirectory.

The suggested pedagogical approach is to have two types of questions: "tutorials" and "practice". The former are questions that the instructor will show the students how to do and walk through the thought process. "Practice" problems are for students to attempt by themselves. Contributions of walkthrough videos are welcome - see the README.md for a given PLUP.

No user data is collected. Filled in responses are stored in a user's web browser via localstorage, so their progress can be saved.

Upon completing an activity, a level code is produced. Students can be instructed to copy and paste the code into a CMS to verify completion and be awarded points. The level code is controlled by either the `solved_code` field (all codes will be identical) or `solved_piece` (codes will be randomly generated containing this substring). It is suggested to use `solved_code` for tutorial questions and `solved_piece` for practice questions.

Deployment
----------
Take all the code under src and expose it via a webserver. Take one `questions.js` from the desired `plup` subfolder and put it in the same directory as the `src` code. Direct students to this hosted web server. The webserver need not respond to any requests other than for those files.

For example, <https://python3tracing.kjlubick.repl.co/> has the Python3 questions loaded and uses Replit's free hosting. See <https://replit.com/@kjlubick/Python3Tracing> for the setup.

If an instructor would like to force deletion of all previous attempts (e.g. moving on to a new semester and requiring students taking the class again to redo the assignments), the CURRENT_VERSION variable in `src/load.js` can be updated.

Compatibility
-------------
This webapp should work on all modern browsers. It does not use any ultra-new APIs.
 