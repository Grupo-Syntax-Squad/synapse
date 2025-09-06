# Acceptance Criteria

### ✅ **Sprint 1 — Authentication**

#### **US-01** – Access registration interface

**Acceptance Criteria:**

- Given the user is on the homepage
  When they click on "Create account"
  Then the registration interface should be displayed.

- Given the user is on the registration interface
  When they fill in all required fields
  Then the submit button should become enabled.

---

#### **US-02** – Complete registration

**Acceptance Criteria:**

- Given the user enters valid registration data
  When they click "Register"
  Then the system should create the account and redirect to the login page.

- Given the user enters invalid data
  When they click "Register"
  Then a clear error message should be displayed.

---

#### **US-03** – Access login interface

**Acceptance Criteria:**

- Given the user opens the login screen
  When they enter a valid email and password
  Then the system should log them in and redirect to the main page.

- Given the user enters incorrect credentials
  When they click "Login"
  Then an authentication error message should be displayed.

---

#### **US-04** – Authenticate and access the system

**Acceptance Criteria:**

- Given the user is authenticated
  Then the system should grant access to the main page.

- Given the authentication fails
  Then the system should deny access and show an error message.

---

### 📊 **Sprint 1 — Reports**

#### **US-05** – Generate report with business template

**Acceptance Criteria:**

- Given there is data to report
  When a report is generated
  Then it must follow the defined business template.

- Given a report is generated
  Then it must contain accurate data in the correct format.

---

#### **US-06** – Send report by email

**Acceptance Criteria:**

- Given a report is successfully generated
  When the user has a valid email on file
  Then the report should be sent to that email automatically.

---

#### **US-07** – Access previously sent reports

**Acceptance Criteria:**

- Given the user accesses the reports tab
  When they click on a report
  Then they should see the content of the previously sent report.

---

#### **US-08** – Filter reports by date

**Acceptance Criteria:**

- Given the user is in the reports tab
  When they select a date range
  Then only reports from that period should be shown.

---

#### **US-09** – Filter reports by name

**Acceptance Criteria:**

- Given the user wants to find a report by name
  When they type in the report name
  Then only matching reports should be displayed.

---

#### **US-10** – Filter reports by content

**Acceptance Criteria:**

- Given the user wants to find a report by content
  When they enter a keyword
  Then only reports containing that keyword should be displayed.

---

#### **US-11** – View sent report emails in system

**Acceptance Criteria:**

- Given the user did not receive the report by email
  When they open the sent reports tab
  Then all attempted email sends should be visible.

---

### 💬 **Sprint 2 — Conversation (NLP)**

#### **US-11 (NLP)** – Access chat

**Acceptance Criteria:**

- Given the user is logged in
  When they click the chat icon
  Then the chat interface should open.

---

#### **US-12** – Send messages to chatbot

**Acceptance Criteria:**

- Given the user types a message
  When they press send
  Then the system should process the message and reply.

---

#### **US-13** – Receive answers in natural language

**Acceptance Criteria:**

- Given the chatbot replies to the user
  Then the answer should be in natural, easy-to-understand language.

---

#### **US-14** – View chat history

**Acceptance Criteria:**

- Given the user opens the chat
  When there are previous interactions
  Then the system should show a chronological history of the chat.

---

### 🛠️ **Sprint 2 — Administration**

#### **US-15** – View list of all users

**Acceptance Criteria:**

- Given the admin is logged in
  When they open the user management page
  Then a list of all users should be displayed.

---

#### **US-16** – Filter users by status

**Acceptance Criteria:**

- Given the admin is on the user list
  When they apply the active/inactive filter
  Then only matching users should appear.

---

#### **US-17** – Delete inactive users

**Acceptance Criteria:**

- Given a user is marked as inactive
  When the admin clicks "Delete"
  Then the user should be removed from the system.

---

#### **US-18** – Filter users by report email status

**Acceptance Criteria:**

- Given the admin wants to manage report recipients
  When they apply a filter based on report email status
  Then the filtered user list should reflect the selection.

---

#### **US-19** – Define report recipients

**Acceptance Criteria:**

- Given the admin selects users
  When they confirm the selection
  Then those users should be marked to receive the reports.

---

#### **US-20** – Reactivate users

**Acceptance Criteria:**

- Given a user is inactive
  When the admin clicks "Reactivate"
  Then the user should regain access to the system.

---

### 🔐 **Sprint 3 — Account Management**

#### **US-21** – Edit account info

**Acceptance Criteria:**

- Given the user is logged in
  When they access their account settings
  Then they should be able to update their name, email, etc.

---

#### **US-22** – "Forgot password" option

**Acceptance Criteria:**

- Given the user is on the login page
  When they click "Forgot password"
  Then they should be taken to the password recovery screen.

---

#### **US-23** – Request password reset

**Acceptance Criteria:**

- Given the user is on the recovery screen
  When they enter a valid email
  Then a password reset email should be sent.

---

#### **US-24** – Receive reset link

**Acceptance Criteria:**

- Given the system sends a reset link
  When the user clicks it
  Then they should be directed to the "new password" page.

---

#### **US-25** – Set new password

**Acceptance Criteria:**

- Given the user is on the password reset page
  When they submit a new password
  Then the password should be updated, and they should be able to log in again.

---

#### **US-26** – Delete account

**Acceptance Criteria:**

- Given the user is logged in
  When they request to delete their account
  Then the system should confirm and permanently remove the account.

---

### 💡 **Sprint 3 — Usability**

#### **US-27** – Access in-app tutorial/help

**Acceptance Criteria:**

- Given the user needs assistance
  When they click on "Help" or "Tutorial"
  Then the system should show simple and clear usage instructions.

---

If you’d like to **convert this into a document**, table, or upload it to a project management tool like **Jira**, **ClickUp**, or **Trello**, I can help format it for that.

Would you like to turn this into a downloadable file (like Excel, Word, or PDF)? Or is there something else you want to do next with this?
