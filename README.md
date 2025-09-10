<img width="1280" height="212" alt="synapse" src="https://github.com/user-attachments/assets/cdae4b36-48af-44d1-ad4d-3b9805e3b249" />

<br>
</br>

<p align="center">
  | <a href ="#objective"> Project Objective </a>  |
  <a href ="#vision"> Product Vision</a>  |   
  <a href ="#technologies"> Technologies</a>  |   
  <a href ="#mvp"> MVP</a>  |
  <a href ="#sprints"> Sprints</a>  |
  <a href ="#backlog"> Product Backlog</a>  |
  <a href ="#dor">DoR</a>  |
  <a href ="#dod">DoD</a>  |
  <a href ="#datamodel">Data Model</a>  |
  <a href ="#howtorun">How to run?</a>  |
  <a href ="#authors"> Authors</a> |
</p>

<span id="objective">

## 📌Project Objective

> [!IMPORTANT]
> The objective of this project is to deliver a smart and automated reporting platform that enhances organizational decision-making by providing structured, periodic reports based on client-defined templates. The platform aims to reduce manual workload, ensure consistent data communication, and offer an intuitive user experience through natural language interaction. By allowing administrators to manage who receives reports and when, and enabling users to retrieve information via an NLP-powered chat, the system empowers teams to access and act on key insights more efficiently and effectively.

> **Project Status: In Progress :construction:**

<span id="vision">

## 💡Product Vision

This platform is designed to simplify the digestion and strategic use of administrative data through the automated generation of reports based on a predefined template provided by the client. Reports are delivered periodically via email to configured recipients, ensuring that information is shared in a consistent and standardized format—eliminating the need for manual data extraction or repetitive formatting. Administrators have full control over who receives each report, allowing targeted distribution based on specific roles or requirements. Additionally, the system includes an intelligent chat powered by Natural Language Processing (NLP), enabling users to interact with the platform in a simple, conversational way to ask questions or retrieve relevant information. This solution streamlines analysis, enhances data accessibility, and supports decision-making across the organization by making business-critical insights clear, actionable, and easy to access.

## 📚Methodology

> [!TIP]
> The Agile Methodology framework used in the product was Scrum, an adaptive, iterative, flexible, and effective agile method. One of the tools used in Scrum is dividing the project into **Sprints**. To determine our Sprint deliverables, we first defined our **MVP**, prioritizing tasks that provided the most value to the customer. From these tasks, we built the **Product Backlog**, which was approved by the client and divided into three Sprint Backlogs. With the tasks outlined, we estimated the time required for each one and optimized the workload distribution among the development team.

<span id="technologies"> 
 
## 🔌**Technologies**
> [!NOTE]
> These are the technologies used in the project's development:

<h4 align="left">
badges das tecnologias
</h4>
 <br> 
 
 <span id="mvp"> 
 
  ## 🏆**MVP**

mvp banner

  <br>
  
  <span id="sprints"> 
  
## 📅Sprints
| Sprint          |    Period     | Documentation                                    | Status |
| --------------- | :-----------: | ------------------------------------------------ | :----: |
| 🔖 **SPRINT 1** | 08/09 - 28/09 | [Sprint 1 Docs](./docs/sprints/sprint-1.md) | In progress :construction: |
| 🔖 **SPRINT 2** | 06/10 - 26/10 | [Sprint 2 Docs](./docs/sprints/sprint-2.md) | In progress :construction: |
| 🔖 **SPRINT 3** | 03/11 - 23/11 | [Sprint 3 Docs](./docs/sprints/sprint-3.md) | In progress :construction: |
  
<br>

<span id="backlog">

## 🌱Product Backlog

| ID    | Epic               | Priority | User Story                                                                                                                                                                     | Story Points | Sprint   |
| ----- | ------------------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------ | -------- |
| US-01 | Authentication     | High     | As a user, I want to access the registration interface to be able to create my system account simply and quickly.                                                              | 3            | Sprint 1 |
| US-02 | Authentication     | High     | As a user, I want to register in the system to be able to access the system.                                                                                                   | 3            | Sprint 1 |
| US-03 | Authentication     | High     | As a user, I want to access the login interface to authenticate my account safely.                                                                                             | 2            | Sprint 1 |
| US-04 | Authentication     | High     | As a user, I want to authentication in the system to be able to access the main page and use available resources.                                                              | 3            | Sprint 1 |
| US-05 | Reports            | High     | As a user, I want the system to manage reports following the template defined for the business, ensuring consistency and standardization of information.                       | 8            | Sprint 1 |
| US-06 | Reports            | High     | As a user, I want to receive the reports generated in the email informed in the register to be able to analyze the results and make decisions based on the submitted summary.  | 5            | Sprint 1 |
| US-07 | Reports            | High     | As a user, I want to access the tab that contains all reports that the system sent me by email to be able to view the reports again.                                           | 2            | Sprint 1 |
| US-08 | Reports            | High     | As a user, I want to filter reports for a specific time interval to be able to consult the reports more efficiently.                                                           | 3            | Sprint 1 |
| US-09 | Reports            | High     | As a user, I want to filter by the name of the report to be able to consult the desired report more efficiently.                                                               | 3            | Sprint 1 |
| US-10 | Reports            | High     | As a user, I want to filter through the content of the report to be able to consult the desired report more efficiently.                                                       | 3            | Sprint 1 |
| US-11 | Reports            | High     | As a user, I want to view the emails sent in the system if I have not received the email.                                                                                      | 5            | Sprint 1 |
| US-11 | Conversation (NLP) | High     | As a user, I want to access the system chat to be able to interact with the agent directly and simply.                                                                         | 3            | Sprint 2 |
| US-12 | Conversation (NLP) | High     | As a user, I want to send messages to the agent to receive processed answers quickly and reliably.                                                                             | 8            | Sprint 2 |
| US-13 | Conversation (NLP) | High     | As a user, I want to receive agent responses in natural language to easily understand information and draw conclusions related to my questions.                                | 5            | Sprint 2 |
| US-14 | Conversation (NLP) | High     | As a user, I want to see a history of my interactions on chat so I can consult previously asked questions.                                                                     | 5            | Sprint 2 |
| US-15 | Administration     | Medium   | As an administrator, I want to access an interface with the list of all users to facilitate access management and control.                                                     | 3            | Sprint 2 |
| US-16 | Administration     | Medium   | As an administrator, I want to filter users by status (active/inactive) to facilitate the management and maintenance of the user base.                                         | 2            | Sprint 2 |
| US-17 | Administration     | Medium   | As an administrator, I want to delete inactive system users to keep the user base updated and secure.                                                                          | 1            | Sprint 2 |
| US-18 | Administration     | Medium   | As an administrator, I want to filter users for the receipt of report receipt by email to facilitate the management and maintenance of users who received the report by email. | 2            | Sprint 2 |
| US-19 | Administration     | Medium   | As an administrator, I want to define users who should receive the report to maintain the control and integrity of the submitted reports.                                      | 3            | Sprint 2 |
| US-20 | Administration     | Medium   | As an administrator, I want to reactivate a user in the system to be able to bring a user back to the system without having to create a new user.                              | 3            | Sprint 2 |
| US-21 | Account management | Medium   | As a user, I want to change my account information so I can keep my registration data updated and correct.                                                                     | 3            | Sprint 3 |
| US-22 | Account management | Low      | As a user, I want to access the option of “I forgot my password” on the login screen to start the recovery process of my account.                                              | 1            | Sprint 3 |
| US-23 | Account management | Low      | As a user, I want to request the redefinition of my password informing my registered email to receive secure recovery instructions.                                            | 3            | Sprint 3 |
| US-24 | Account management | Low      | As a user, I want to receive a temporary password redefinition link on my email so I can create a new password safely.                                                         | 3            | Sprint 3 |
| US-25 | Account management | Low      | As a user, I want to set a new password through the link received to recover access to my account.                                                                             | 3            | Sprint 3 |
| US-26 | Account management | Low      | As a user, I want to delete my account to detach me from the system and stop receiving emails and reports.                                                                     | 1            | Sprint 3 |
| US-27 | Usability          | Low      | As a user, I want to access a tutorial/quick help within the system to learn to use it without the manual.                                                                     | 3            | Sprint 3 |

<br>

## 🏃‍ DoR - Definition of Ready <a id="dor"></a>

- User Stories with Acceptance Criteria
- Subtasks divided from the US
- Design in Figma
- Database Modeling
- Route Diagram
- Customer's Vectorized Database

## 🏆 DoD - Definition of Done <a id="dod"></a>

- User Manual
- Application Manual
- API (Application Programming Interface) Documentation
- Complete Code
- Videos of each delivery stage

<br>

<span id="datamodel">
 
 ## 🧱Data Model
 <p align="center">
  
<img width="1102" height="304" alt="image" src="https://github.com/user-attachments/assets/5931a26a-5181-46d1-b258-3782dadfb33f" />

## 📜Commit Tags

To maintain a clean and coherent Git history, the project follows the **Conventional Commits** standard. Commit messages must follow the format `type: #TASK_ID description`.

**Message structure:**

- `type`: Classifies the nature of the change.
- `#TASK_ID`: The task's identifier.
- `description`: A brief description of the change.

**Accepted commit types:**

|    Type    | Description                                                |
| :--------: | ---------------------------------------------------------- |
|   `feat`   | A new feature                                              |
|   `fix`    | A bug                                                      |
|   `docs`   | Documentation Changes                                      |
|  `style`   | Code formatting changes (CSS, etc.) without logic changes. |
| `refactor` | Code refactoring without a change in behavior.             |
|   `perf`   | Performance improvement.                                   |
|   `test`   | Adding or correcting tests.                                |
|  `build`   | Changes to the build system.                               |
|    `ci`    | Changes to the CI/CD configuration.                        |
|  `chore`   | Maintenance tasks that do not alter the source code.       |

**Examples of valid commits:**

```
fix: #123 fixes the login screen layout
feat: #456 adds a badge component
chore: #789 updates libraries
```

> [!IMPORTANT]
> Where I found the TASK_ID?

> [!TIP] >**the TASK_ID can be found in the jira panel, described in each task where only developers have access to this panel**

  <br>

<span id="howtorun">

## 🤔How to Run?

<span id="authors">

## 👨‍💻**Authors**

|              Name              |     Role      |                                                                          Github                                                                          |                                                                                         Linkedin                                                                                         |
| :----------------------------: | :-----------: | :------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|    Wellington Luiz de Faria    | Product Owner | <a href="https://github.com/WellingtonLFaria"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white"></a> |  <a href="https://br.linkedin.com/in/wellington-luiz-de-faria-92007425b"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a>  |
| Gabriel de Oliveira Silva Reis | Scrum Master  |      <a href="https://github.com/b4hia"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white"></a>       |               <a href="https://www.linkedin.com/in/b4hia/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a>                |
|       Iago Cardoso Souza       |   Developer   |     <a href="https://github.com/iagocpv"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white"></a>      |       <a href="https://www.linkedin.com/in/iago-cardoso-315955194/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a>       |
| João Vitor dos Santos Pereira  |   Developer   |     <a href="https://github.com/JaovitoP"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white"></a>     |           <a href="https://www.linkedin.com/in/joaopereira18/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a>            |
|    Ryan Verissimo de Araujo    |   Developer   |   <a href="https://github.com/ryandaraujo"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white"></a>    | <a href="https://www.linkedin.com/in/ryan-verissimo-de-araujo-910925239/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a> |
