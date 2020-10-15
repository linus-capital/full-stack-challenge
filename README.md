# LINUS Full-Stack Challenge

The main goal of this challenge is to understand how you build software.  

Take your time to read the challenge, understand the requirements and then start building it when you feel ready.  

You don't need to keep track of your time, this is not a race.

Things we consider: 

- Design of the solution
- Easiness to setup/execute
- Code quality
- Automated tests
- Version Control

## Scenario

Our platform customers are investors who want to participate in our real-estate deals. They can see all relevant information about these deals on the platform in order to make an informed decision whether to co-invest or not.

To make the process of co-investing as easy and efficient as possible, we want to enable our customers to submit their information, as well as sign documents directly via our platform.

## Challenge

The challenge is split into 2 parts, front-end and back-end. We would prefer a full-stack solution written in TypeScript/JavaScript, but if you feel more comfortable in the back-end using another language that's fine.

__Notes__
- You can use libraries and frameworks as you see fit, but keep in mind the goal of this is to evaluate your skills. To give some orientation: we are running on NuxtJS (VueX, SSR, SCSS), NestJS (REST, TypeORM), and PostgreSQL. You are not required to use any of these technologies, but working with very related frameworks and tools is beneficial.
- The front-end part is not a UI design contest. We would rather that you focus on component setup, state management, and general code quality.
- Use git with descriptive commit messages for documenting your progress, and to help us get an understanding of how you approached the implementation.
- Don't spend more than a couple of hours. The goal is to show how you work, not to deliver production-ready code.

### Part 1: Front-end

Build a three-step form for our customers to select a project and submit their data to us. The UI could (does not have to) look like this: https://www.figma.com/file/mveXRSbQV4cPFq1SzSvaF2/LINUS-Full-Stack-Challenge?node-id=0%3A1

__Step 1)__
- fetch available projects from `GET https://fullstack.linus-capital.com/projects`
- render a list of projects with their name and location
- make the items selectable -> clicking on a item will bring the user to the next step

__Step 2)__
- add some input fields: customer email (`string`), investment amount (`integer`)
- all of these fields are required to have valid values in order to proceed to step 3

__Step 3)__
- confirmation screen that contains: project name, email and investment amount
- add a terms and conditions checkbox
- confirm button to submit the request
- display an indicator when the request is in progress
- show text to let the user know if the submission was successful or not
- confirming should send all the form data to a back-end endpoint, which you will implement in the second part of this challenge

### Part 2: Back-end

Implement a single endpoint that retrieves the data from the form and executes the following operations:

__1) writes the record into a database__
- fields are: `email`, `investment_amount`, `project_id`
- you are free to use any database you think would be well suited in this case

__2) send the data to an external CRM__
- you are not required to integrate an actual CRM, mocking the request is sufficient

__3) send a confirmation e-mail to the customer__
- same here, no actual implementation required, mocking is sufficient


## General Requirements

- Your code should be well tested. You don't have to cover each edge-case, focus on the tests that have the biggest impact for this scenario in your eyes.
- This investment process does not receive high volumes of traffic, but the individual sessions are critical to our business. Think about how you would handle outages of certain systems, such that users do not experience errors unless completely unavoidable. You don't have to implement anything complicated. Maybe just add some comments on how you would deal with:
  - CRM outage
  - emailing issue
  - database outage
  
## Submission

Please push your code to a __public__ Github repository and submit a link of it to: [engineering@linus-capital.com](mailto:engineering@linus-capital.com) Please include a `README.md` in your repository with some instructions on how to run your application.

In case you have any questions about the challenge, feel free to [reach out](mailto:engineering@linus-capital.com).
