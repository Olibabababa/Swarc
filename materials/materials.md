# Introduction and Goals

The main purpose of Noodle is to optimize administrative tasks, improve communication and enhance the overall efficiency of the grading system.

  - Generating timetables for students and lecturers while also sending reminders
  
  - Ease the communication with the students
  
  - Grading system combined with feedback
  
  - Tracking the progress of the students
  
  - Resource Allocation

# Stakeholders

| Role/Name   | Expectations       |
|-------------|--------------------|
| *Manfred Lohr (Lecturer)* | *having the administrational issues* |
| *Rolandinho Csiszer (Student)* | *expects easier communication with the faculty* |
| *Volkan Papadopoulus (Student)* | *wants access to grades and feedback via Noodle* |
| *Brua Meyer (Head of administration)* | *Resource allocation should be done automatically and curriculum planning* |
| *Koliver Roller (IT Department)* | *Enhance efficiency and lower downtime* |

# Quality Goals 

| Priority   | Quality       | Motivation      |
|------------|---------------|-----------------|
|*1*| *Functional suitability*| *Ensure all data is correct and everything operates as expected*|
|*2*| *Reliability*| *Ensure that Noodle consistently without unexpected downtime*|
|*3*| *Usability*| *Create a userfriendly interface with german and english as choosable languages*|

# Architecture Constraints

| Constraints | Backround and/or Motivation |
|-------------|-----------------------------|
| *Sole reliance on the university database*| *Service is only available if the university database is operating.*|
| *Thrid party software must be available at all times*| *MS-Teams and LMS(Learning Management System) must be available for the application to be able to operate properly.*|
|*University Database must be used*| *Insuffitient funds and manpower to implement a database into the application.*|
|*Team*| *Maximum number of people working on the project is limited, due to the company's size*|
|*Language*| *Noodle should be accessible in German and English to make it usable for non German speaking students.*|

# System Scope and Context



# Business Context 

<img width="752" alt="image" src="https://github.com/Olibabababa/Swarc/assets/131277121/2b59dac0-f7fc-46d9-aa3a-c309a3e01306">

# Solution Strategy 

| Goal/Requirements   | Architectural Approach|
|----------------------------|----------------|
| *Resource Allocation*| *Monolithic*|
| *Grading System combined with feedback*| *Monolithic*|
| *Tracking progress of students* | *Monolithic*|

# Building Block View

Level 1
  
<img width="752" alt="image" src="https://github.com/Olibabababa/Swarc/assets/131277121/89fedb8a-2aa3-4cf0-9b88-de41fe404ef0">


Level 2
  
<img width="752" alt="image" src="https://github.com/Olibabababa/Swarc/assets/131277121/eaa27a39-66c5-417c-8125-d39611a311a8">

# Runtime View

Getting Grades

<img width="752" alt="image" src="https://github.com/Olibabababa/Swarc/assets/131277121/3443801e-2458-401b-bbb3-10bf5ac43db6">

Generate Timetable

<img width="752" alt="image" src="https://github.com/Olibabababa/Swarc/assets/131277121/ffdf2230-ec24-477d-9c74-683c81b373d2">

# Deployment View


<img width="752" alt="image" src="https://github.com/Olibabababa/Swarc/assets/131277121/e6d0f0c4-e8a7-4f7f-bd6b-1c7aaec82d17">


  Deployment Diagram

<img width="752" alt="image" src="https://github.com/Olibabababa/Swarc/assets/131277121/7bb7365b-4582-4726-87df-5b0ab70a8deb">


# Crosscutting Concepts

User Experience(UX)
  - Ergonomic and easy to use Website
  - English and German as pickable languages
    
Security and Safety
  - Keeping student's data secure and accessible
    
Operation Concepts
  - Automatic resource allocation

| Context   | Decision   | Consequences |
|------------|---------------|---------------------|
|*Startup with a small team*| *use Scrum as development model*| *Initial prototype won't be able to fulfill every feature*|
|*Limited resources (staff and money)*| *Monolithic architecture is used*| *Downtime when Noodle is updated*|
|*Integration of thrid-party systems (MS-Teams,...)*| *Using them, due to limited ressources*| *If the thrid-party systems are down it's unfixable for us*|


# Architecture Decisions

| Problem   | Considered Alternatives   | Decision |
|------------|---------------|---------------------|
|*ADR 1: downtime due to updates*| *No alternatives due to funding/staff issues*| *Monolithic / Inform the faculty that downtimes are required for updates*|
|*ADR 2: downtime due to errors*| *No alternatives due to funding/staff issues*| *Monolithic / Backup server or informing the faculty about the downtime happening to correct the mistake*|
|*ADR 3: incorrect data*| *No alternatives due to funding/staff issues*| *Monolithic / 9-5 faculty IT-Admin as support*|

# Quality Requirements

## Quality Goals and Scenarios

  Performance
  
  -Users exchange messages between each other under normal circumstances. The average latency of processing all messages is 0.5 seconds.

  Usability
  
  -User wants to generate timetables automatically to minimize human error during runtime. After he decides to generate the schedule, the generation takes under 3 seconds.

  Security
  
  -User wants to be informed when someone enters his account under normal circumstances. Unauthorized intrusion is reported in under 10 seconds.
  
## Quality Tree

<img width="752" alt="image" src="https://github.com/Olibabababa/Swarc/assets/131277121/1cdad6be-d9b1-4616-9b28-bdfedf83cfb4">

# Risks and Technical Debts

| Risk/Technical Debt   | Description|
|----------------------------|----------------|
| *Higher Downtime*| *Scheduled downtime for updates and Backup server when errors occur.*|
| *Security*| *Monolithic applications tend to have large and complex codebases, which can make it difficult to identify and fix security issues.*|
| *Data Management* | *In monolithic architectures, different components of the application often share the same database schema. This can make it difficult to make change to the database schema without affecting multiple parts of the application*|
