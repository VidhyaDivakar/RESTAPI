# Freelance Worker API Endponts

What is this endpoint, what is the need of this?

This API helps any freelancer to retrive the jobs from five specifc websites on a daily basis. You need to resgister to these websites and based on your profile information, the API will return jobs for the day. In this scenario, I have consider a freelancer who is an Engineering graduate and a all rounder in work, meaning he/she can work on any given job precisely. Each day you need to collect what type of work you will be working on that day. Work of interests - Creating UX screens for a new start up app, Testing Automation Use Cases, Software Documentation, Release Notes, Developer Facing Documents, Demos, Conducting Training Sessions etc. That work will have a ID, when you lookup the ID, you can get information about that job.

In this document you will get information on how to request the API. What endpoints can work for this scenario. You can also find few response examples.

Daily Work API Documentation

Base URL:

<https://api.dailywork.com>

Description:
This API allows freelancers to manage daily work tasks collected from multiple websites. Each task has a unique ID, type, title, description, deadline, priority, website source, and status.

1. Get All Work for Today

Endpoint:

GET /work/today

Description:
Retrieve all work items assigned for the current day.

Query Parameters (Optional):

Parameter Type Description
type string Filter by work type (e.g., UX Design, Documentation, Training)

Response Example:

[
  {
    "id": 101,
    "type": "UX Design",
    "title": "Create login screens for Startup App",
    "description": "Design 5 screens for the login and signup flow",
    "deadline": "2025-10-17T18:00:00Z",
    "priority": "High",
    "website": "FreelanceSiteA",
    "status": "Pending"
  },
  {
    "id": 102,
    "type": "Documentation",
    "title": "Software Documentation for Project X",
    "description": "Document modules and user guide",
    "deadline": "2025-10-17T20:00:00Z",
    "priority": "Medium",
    "website": "FreelanceSiteB",
    "status": "Pending"
  }
]

2. Get Work Details by ID

Endpoint:

GET /work/{id}

Description:
Fetch detailed information about a specific work item using its unique ID.

Path Parameter:

Parameter Type Description
id integer Unique work ID

Response Example:

{
  "id": 101,
  "type": "UX Design",
  "title": "Create login screens for Startup App",
  "description": "Design 5 screens for the login and signup flow",
  "deadline": "2025-10-17T18:00:00Z",
  "priority": "High",
  "website": "FreelanceSiteA",
  "instructions": [
    "Use Figma for design",
    "Follow the company’s branding guidelines",
    "Share prototype via link"
  ],
  "status": "Pending"
}

3. Add a New Work Item

Endpoint:

POST /work

Description:
Add a new work item to your daily tasks.

Request Body (JSON):

{
  "type": "Training",
  "title": "Conduct Selenium Automation Session",
  "description": "Training session for QA team on Selenium automation",
  "deadline": "2025-10-18T16:00:00Z",
  "priority": "High",
  "website": "FreelanceSiteC"
}

Response Example:

{
  "message": "Work item created successfully",
  "id": 105
}

4. Update Work Status

Endpoint:

PUT /work/{id}

Description:
Update the status of a work item (e.g., Pending → Completed).

Path Parameter:

Parameter Type Description
id integer Unique work ID

Request Body (JSON):

{
  "status": "Completed"
}

Response Example:

{
  "message": "Work item updated successfully",
  "id": 101,
  "status": "Completed"
}

5. Delete a Work Item

Endpoint:

DELETE /work/{id}

Description:
Delete a work item if it’s no longer needed.

Path Parameter:

Parameter Type Description
id integer Unique work ID

Response Example:

{
  "message": "Work item deleted successfully",
  "id": 101
}

6. Work Types Reference
   Work Type Description
   UX Design Creating screens, mockups, prototypes
   Testing Automation Writing and executing automated test cases
   Documentation Software manuals, guides, or developer docs
   Release Notes Writing release notes for versions
   Demos Preparing demo environments or presentations
   Training Conducting training sessions for teams
   Benefits of This API

Centralized Daily Work Management – Track tasks from multiple platforms in one place.

Quick Lookup – Easily fetch details of a work item by ID.

Structured Data – JSON responses make reporting and automation easy.

Interactive & Automatable – Integrate with dashboards or scripts for reminders.

Documentation Ready – All endpoints can be exported into Swagger/Postman for official API docs.
