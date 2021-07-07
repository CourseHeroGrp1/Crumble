# Project Plan

Pod Members: **Stephanie D., Abhiraj C., Gevork M.**

## Problem Statement and Description

### Problem Statement
Managing large-scale projects or assignments is difficult due to complex scope and competing priorities. Our goal is to provide a versatile web planning tool that allows users to easily view their deadlines/deliverables by organizing large assignments into smaller, digestible tasks.

### Description
The purpose of this app is to provide users a platform that helps users be more productive and at the same time reminds them to take breaks while working. Key features include adding main tabs and subtabs for each different category of work and using the pomodoro timer to further increase productivity. Each tab contains a calendar side by side with daily/weekly to-do lists, a notes section, and a running timer for the pomodoro in nav bar.


## User Roles and Personas

### User Roles
- Individual: a user who wants to be productive in their daily lives with the help of our application.

### User Personas
- Billy is a sophomore who goes to UCLA. Billy is a Computer Science student and wants to manage the different projects/assignments along with preparing for technical interviews. In order to be productive and not procrastinate, Billy wants to have a central manager which has all his notes and information for each of his classes.
 
- Susan is a middle aged woman working as a project manager. Susan’s team is undertaking a large project and wants to have an effective management system to keep track of the various moving parts. Susan needs to create and share a tool with a work-rest daily schedule, kanban-style todos and overview for future meetings.


## User Stories

1. As a high school student, I often have trouble managing my schedule and the tasks I have to complete in a day, so it would be nice to have some way to organize my weekly and daily schedule in one place.
2. As a forgetful person, I want to be able to create customized schedules and to-do-lists for specific projects.
3. As a busy college student, it would be nice to have a single place where I can store all my notes for a specific class along with customized schedules for each class.
4. As an office worker, it would be useful to have an easy way to manage my work-rest daily schedule, manage my TODOs, and have an overview of my weekly schedule.
5. As a project manager, I need a place to quickly write what tasks need to be completed along with having easy access to my documents.
6. As a software developer, having many tasks to complete can be overwhelming and difficult to keep track of, which is why I would like to be able to set long term and short term goals along with the ability to create custom notes for each assignment. 
7. As a researcher, it is extremely important to complete tasks on time as well as keeping all my notes organized and easy to access, so it would be nice to have an app where I can do all this in one place. 
8. As a teenager, my parents give me weekly chores to complete along with daily homework assignments that I have to work on for a set amount of time so it would be nice to have all the tools I need in one place. 
9. As a secretary, I am constantly busy managing plans and projects, as well as keeping notes about certain events which can become very messy and unorganized at times, so having one place for all my scheduling and note taking associated with specific events/assignments would be helpful. 
10. As a computer science student, it would be helpful to have a place where I can track which topics I need to review for my technical interviews.  


## Pages/Screens

Landing page                         
:-------------------------:
<img src="wireframes/landing.png" width=500><br>

Login/Register page             
:-------------------------:
<img src="wireframes/login_register.png" width=500><br>

Tabs Overview page    
:-------------------------:
<img src="wireframes/tab_overview.png" width=500><br> 

Tab page            
:-------------------------:
<img src="wireframes/tab.png" width=500><br>

Pomodoro Timer page
:-------------------------:
<img src="wireframes/pomodoro.png" width=500><br>


## Data Model

### users
Name |  Type  | Description
:-------------------------:|:-------------------------:|:-------------------------:
id | SERIAL | primary key
email | VARCHAR(70) | email of user, unique
password | TEXT | hashed user password
first_name | VARCHAR(50) | user's first name
last_name | VARCHAR(50) | user's last name
is_admin | BOOLEAN | default false
created_at | TIMESTAMP | when account was created

### main_tabs
Name |  Type  | Description
:-------------------------:|:-------------------------:|:-------------------------:
id | SERIAL | primary key
user_id | INTEGER | foreign key to users
name | VARCHAR(30) | name of main tab
created_at | TIMESTAMP | when main tab was created

### subtabs
Name |  Type  | Description
:-------------------------:|:-------------------------:|:-------------------------:
id | SERIAL | primary key
main_id | INTEGER | foreign key to main tab, possibly null
sub_id | INTEGER | foreign key to sub tab
created_at | TIMESTAMP | when sub tab was created

### tasks
Name |  Type  | Description
:-------------------------:|:-------------------------:|:-------------------------:
id | SERIAL | primary key
sub_id | INTEGER | foreign key to sub tab
details | VARCHAR(40) | task description
completed_at | TIMESTAMP | date the task was completed
created_at | TIMESTAMP | when task was created

### notes
Name |  Type  | Description
:-------------------------:|:-------------------------:|:-------------------------:
id | SERIAL | primary key
sub_id | INTEGER | foreign key to sub tab
title | VARCHAR(20) | notes title
details | TEXT | notes description
created_at | TIMESTAMP | when notes was created

### calendar
Name |  Type  | Description
:-------------------------:|:-------------------------:|:-------------------------:
id | SERIAL | primary key
sub_id | INTEGER | foreign key to sub tab
event | VARCHAR(20) | title of event
date | TIMESTAMP | date/deadline of event
created_at | TIMESTAMP | when calendar was created


## Endpoints

List the API endpoints you will need to implement.

***Don't forget to set up your Issues, Milestones, and Project Board!***
