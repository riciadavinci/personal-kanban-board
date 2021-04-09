### Persona Kanban Board

#### Project Goal (Broad Overview):
- Make a web-app using good Test Driven Development (TDD) Practices
- Make a web-app using good Version Control (using git) Practices
- Make a productivity web-app for tracking Tasks in different projects


#### Specific Features:
1. Landing-page/Homepage to display the following:
    - [ ] Project names
    - [ ] Project Creating Date
    - [ ] Project Completion Date
    - [ ] No. of Tasks in that Project (TODOs, WIPs, DONEs) with a progress bar

2. Kanban Board Page:
    - [ ] Progress Bar for all Tasks at the Top (With No. of Tasks as well)
    - [ ] TODO Column (Tasks will be added here as a default) (With No. of Tasks) (Orange for Progress Bar)
    - [ ] WIP Column (Open Tasks and currently being worked on) (With No. of Tasks) (Orange for Progress Bar)
    - [ ] DONE column (Tasks Completed Successfully) (With No. of Tasks) (Orange for Progress Bar)

3. Analytics Dashboard:
    - [ ] Graph to show how much tasks created, opened, completed in a given day, month, year (need to figure out good data structure)

4. Project Page:
    - [ ] Project Name, Creation Date, Completion Date, No. of Different Tasks, Status Bar
    - [ ] Analytics Graph for the Project (Need to define more concretely; needs more research)

5. General Stuff:
    - Colours of the Progress Bar:
        - Orange: TODO
        - Purple: WIP
        - Dark-Green: DONE

6. Not included:
    - Re-opening of Tasks (Just create a new task with the same name and content, Can be fixed later)
    - Drag and Drop for Task-Cards (on the Kanban Board page)

7. Future Work:
    - Add User Feature
    - Work on deploying it
    - Connect the Backend to a Mobile App
    - Make the Web-app responsive
    - Connect the Tasks to a Custom Calendar App (Both Web and Mobile?)


--- 

### Tech-Specs

1. Backend: Python
    - Flask, Flask-sqlalchemy, sqlalchemy, ...

2. Frontend: Plain JS (ES6 std)

3. Database: PostgreSQL


---

### Database Model Definition:

1. Project:
    - Name* (String)
    - ID* (string of random characters and numbers)
    - Creation date* (Datetime) (default = Datetime.now())
    - Completion date (Datetime) (default = null)
    - Description (Markdown or Rich-Text) (default = null)
    - No. of TODO Tasks (default = 0)
    - No. of WIP Tasks (default = 0)
    - No. of Completed Tasks (default = 0)
    - One to Many (List of Tasks) (default = null)

2. Task:
    - ID* (Integer) (default = 1)
    - Description* (Capped at 500 characters) 
    - project_id* (String) (Foreign ID)
    - Creation Date (Datetime) (default = Datetime.now())
    - Start Date (Datetime) (default = null) (will be set when status changes to WIP)
    - End Date (Datetime) (default = null) (will be set when status changes to Closed)
    - status/current_bucket (String) (TODO/WIP/DONE)
    - Useful URL (String) (default = "") 


---

### Object Actioms:

1. Project:
    - Full CRUD

2. Task:
    - Full CRUD


---
