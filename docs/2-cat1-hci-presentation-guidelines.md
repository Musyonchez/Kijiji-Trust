# CAT 1 Presentation Guide – Kijiji-Trust Project
## SFE 4010A – Human Computer Interaction

**Worth**: 30 Marks  
**Format**: Team Presentation  
**Focus**: Mid-semester project demonstration

---

## Presentation Requirements

### i. Start Slide (2 minutes)

**What to Include:**
- Project title: "Kijiji-Trust: Digital Chama & Mutual Aid Platform"
- Team member names and registration numbers
- Course code: SFE 4010A

**Template:**
```
Title: Kijiji-Trust: Digital Chama & Mutual Aid Platform
Subtitle: User-Centered Design for Community Financial Management

Team Members:
- [Name] - [Reg Number]
- [Name] - [Reg Number]
- [Name] - [Reg Number]
- [Name] - [Reg Number]

Course: SFE 4010A - Human Computer Interaction
```

---

### ii. Introduction / Scenario (3-4 minutes)

**What to Cover:**

1. **Background Context**
   - Explain what Chamas are (traditional community savings groups)
   - Current limitations: manual record-keeping, lack of transparency, geographic constraints

2. **Problem Statement**
   - Difficulty tracking contributions
   - Trust and accountability issues
   - Limited accessibility for remote members
   - Prone to errors and disputes

3. **Project Goal**
   - Design a user-friendly web application to digitize Chama management
   - Maintain cultural values while adding transparency
   - Accessible to users with varying technical literacy

**Key Points:**
- Keep it relatable - many people understand savings groups
- Emphasize real-world relevance
- Clearly state the problem you're solving

---

### iii. Proposed Solution (4-5 minutes)

**What to Include:**

1. **Solution Overview**
   - Web-based platform for Chama management
   - Four core features:
     - Group Management
     - Contribution Tracking
     - Emergency Request System
     - Transparency Dashboard

2. **Visual Diagram**
   Create a simple system overview showing:
   - User types (Admin, Treasurer, Member)
   - Main features
   - Data flow (contributions → group pot → emergency requests)

3. **How It Addresses the Problem**
   - Digital ledger eliminates manual errors
   - Real-time updates increase transparency
   - Mobile access removes geographic barriers
   - Audit trail builds trust

**Tips:**
- Use mockups or wireframes if available
- Keep diagram simple and clear
- Focus on user benefits, not technical details

---

### iv. Requirements (4-5 minutes)

#### Functional Requirements (What the system does)

Present 8-10 key functional requirements:

1. User registration and secure login
2. Create groups with custom contribution rules
3. Join groups using invite codes
4. Display real-time group balance
5. View personal contribution history
6. Submit emergency requests (bereavement/medical)
7. Approve/reject emergency requests (admin)
8. Send in-app notifications for key events
9. Log all transactions in transparency dashboard
10. View group member list

#### Non-Functional Requirements (How the system performs)

Present 6-8 key non-functional requirements:

1. **Usability**: Intuitive for users with basic smartphone skills
2. **Accessibility**: 16px minimum font, high contrast colors
3. **Performance**: Load within 3 seconds on 3G
4. **Security**: Encrypted data, secure authentication
5. **Responsiveness**: Works on mobile screens (320px+)
6. **Reliability**: Offline mode with sync
7. **Trust**: Visual indicators of security and data integrity

**Presentation Tip:**
- Group similar requirements together
- Use bullet points, not paragraph
</text>
- Give example for each category

---

### v. Users (3-4 minutes)

**User Groups to Present:**

#### 1. Group Administrators (30-55 years)
- **Who**: Community leaders, moderate tech skills
- **Goals**: Manage group fairly, maintain trust
- **Needs**: Simple setup tools, clear oversight dashboard
- **Pain Points**: May not be highly technical
- **Design Impact**: Large buttons, clear labels, confirmation dialogs

#### 2. Group Members (25-65 years)
- **Who**: Diverse backgrounds, varying tech literacy
- **Goals**: Track contributions, access emergency funds when needed
- **Needs**: Easy viewing of their status, simple request process
- **Pain Points**: Some have limited smartphone experience
- **Design Impact**: Mobile-first design, minimal steps to complete tasks

#### 3. Treasurers (28-50 years)
- **Who**: Detail-oriented, organized individuals
- **Goals**: Accurate tracking, generate reports
- **Needs**: Overview of all transactions, export capabilities
- **Pain Points**: Reconciling digital and physical records
- **Design Impact**: Clear financial dashboard, downloadable transaction history

**Key Message:**
Show how understanding these users shaped your design decisions.

---

### vi. Personas, Scenarios & Use Case Diagrams (5-6 minutes)

#### Personas (Show 2-3)

**Example Persona 1:**
```
Name: Grace Wanjiku
Age: 42
Role: Group Administrator
Tech Level: Moderate

Background: Community leader managing a 25-member women's group

Goals:
- Set up digital Chama easily
- Ensure all members can use the system
- Maintain transparency and trust

Frustrations:
- Current Excel sheets are error-prone
- Hard to reach all members quickly

Quote: "I need something simple that all my members can use, even those who aren't tech-savvy."
```

**Example Persona 2:**
```
Name: John Kamau
Age: 34
Role: Group Member
Tech Level: Basic

Background: Works in informal sector, supports family

Goals:
- Keep track of his contributions
- Request help quickly in emergencies

Frustrations:
- Doesn't always make meetings to know group balance
- Worries about transparency in fund disbursement

Quote: "I just want to know my money is safe and I can get help when I need it."
```

#### Scenarios (Show 2-3 realistic use cases)

**Scenario 1: Creating a Group**
> Grace wants to set up a digital Chama for her women's group. She opens the app, creates a new group called "Mama Mboga Welfare," sets monthly contributions at 500 KES, generates an invite code, and shares it via WhatsApp with her 24 members.

**Scenario 2: Emergency Request**
> John's mother is hospitalized. He logs into the app, submits an emergency request under "Medical" for 10,000 KES, and attaches a photo of the hospital bill. The admin receives a notification, reviews the request, and approves it. John receives confirmation within 10 minutes.

#### Use Case Diagram

Create a UML use case diagram showing:
- **Actors**: Admin, Member, Treasurer, System
- **Use Cases**: 
  - Register/Login
  - Create Group
  - Join Group
  - Make Contribution
  - Submit Emergency Request
  - Approve Request
  - View Transparency Log
  - Generate Reports

---

### vii. Design Considerations (5-6 minutes)

**HCI Principles Applied:**

#### 1. Visibility & Feedback
- **Principle**: Users should always know what's happening
- **Implementation**:
  - Loading spinners for all actions
  - "Payment recorded" confirmation messages
  - Real-time balance updates
  - Color-coded status badges (paid=green, pending=yellow, overdue=red)

#### 2. Consistency
- **Principle**: Similar things should work similarly
- **Implementation**:
  - All action buttons in same position
  - Green = confirm/success, Red = cancel/error
  - Consistent navigation menu across pages

#### 3. Error Prevention
- **Principle**: Prevent mistakes before they happen
- **Implementation**:
  - "Are you sure?" for approving large requests
  - Input validation (amount must be positive number)
  - Disable "Submit" until required fields complete

#### 4. Mobile-First Design
- **Research**: 70%+ of target users use smartphones primarily
- **Implementation**:
  - Touch-friendly buttons (44x44px minimum)
  - Bottom navigation for thumb reach
  - Large text (16px minimum)
  - Single-column layouts

#### 5. Accessibility
- **Research**: Diverse age groups, some with vision challenges
- **Implementation**:
  - High contrast (WCAG AA compliant)
  - Screen reader support
  - Clear error messages
  - No reliance on color alone

#### 6. Cultural Sensitivity
- **Research**: Users value traditional Chama practices
- **Implementation**:
  - Familiar terminology ("Group," not "Organization")
  - Respect traditional roles
  - Local language support (future)

**Show Examples:**
- Screenshots demonstrating these principles
- Before/after comparisons if you iterated
- Side-by-side mobile and desktop views

---

### viii. Demo (6-8 minutes)

**Demo Flow (Practice this!):**

1. **Homepage/Landing** (30 seconds)
   - Show the clean, simple interface
   - Point out call-to-action buttons

2. **User Registration** (1 minute)
   - Quick signup process
   - Show form validation

3. **Create a Group** (2 minutes)
   - Admin creates "Test Chama"
   - Sets contribution amount (e.g., 1000 KES)
   - Sets frequency (Monthly)
   - Generates invite code

4. **Join Group** (1 minute)
   - Switch to member account
   - Use invite code to join
   - Show confirmation

5. **View Dashboard** (1 minute)
   - Member sees group balance
   - Views their contribution status
   - Sees other members (anonymized if needed)

6. **Submit Emergency Request** (2 minutes)
   - Member creates request
   - Fills in type, amount, description
   - Submits successfully

7. **Approve Request** (1 minute)
   - Switch to admin account
   - See notification of new request
   - Review and approve
   - Show updated balance

8. **Transparency Log** (1 minute)
   - Show complete transaction history
   - All contributes visible
   - Request approval logged

**Demo Tips:**
- Have test data pre-loaded
- Practice timing
- Have screenshots as backup
- Explain each click: "I'm clicking 'New Request' because..."
- Highlight HCI principles in action

---

### ix. Next Steps (2-3 minutes)

**What's Next for the Project:**

#### Immediate Tasks (Next 2-3 weeks)
- Conduct usability testing with 5-10 participants from target user group
- Fix identified bugs and UI issues
- Refine based on user feedback
- Complete remaining MVP features

#### Evaluation Plan

**Method 1: Usability Testing**
- **Participants**: 8-10 users matching our personas
- **Tasks**:
  1. Create an account and join a group
  2. View your contribution status
  3. Submit an emergency request
  4. (Admin) Approve a request
- **Metrics**: Task completion rate, time to complete, errors made
- **Goal**: 80%+ success rate, SUS score of 70+

**Method 2: Heuristic Evaluation**
- Use Nielsen's 10 usability heuristics
- Have 3-4 evaluators review independently
- Prioritize violations by severity
- Fix critical issues before final submission

**Method 3: System Usability Scale (SUS)**
- 10-question survey after testing
- Benchmark against industry standards
- Target: Score above 70 (good usability)

#### Future Enhancements (Beyond this course)
- Mobile app (iOS/Android)
- M-Pesa payment integration
- SMS notifications
- Multi-language support (Swahili, Kikuyu)
- Analytics dashboard for group insights

**Key Message:**
Show that you have a clear plan for evaluation and iteration based on HCI principles learned in class.

---

## Presentation Delivery Tips

### Time Management
- **Total Time**: Aim for 20-25 minutes + 5 min Q&A
- Assign sections to team members
- Practice with a timer
- Have a timekeeper during presentation

### Visual Design
- Use consistent slide template
- Avoid text-heavy slides
- Use visuals, diagrams, screenshots
- Readable fonts (24pt minimum)
- High contrast colors

### Team Coordination
- Clear transitions between speakers
- Everyone should participate equally
- Practice together at least twice
- Support each other during Q&A

### Engagement
- Make eye contact
- Speak clearly and not too fast
- Show enthusiasm for your project
- Welcome questions

---

## Marking Criteria

**Expected evaluation areas (30 marks total):**

- ✅ **Completeness**: All 9 sections covered (~5 marks)
- ✅ **HCI Understanding**: Clear application of principles (~6 marks)
- ✅ **User Research**: Quality of personas and user analysis (~5 marks)
- ✅ **Design Justification**: Rationale for design choices (~5 marks)
- ✅ **Prototype Demo**: Working demonstration (~5 marks)
- ✅ **Presentation Quality**: Clarity, organization, delivery (~4 marks)

---

## Final Checklist

Before your presentation:

- [ ] Start slide with all required information
- [ ] Clear problem statement and project goal
- [ ] Solution overview with visual diagram
- [ ] Complete list of functional requirements (8-10)
- [ ] Complete list of non-functional requirements (6-8)
- [ ] 3 detailed user descriptions
- [ ] 2-3 personas created
- [ ] 2-3 realistic scenarios written
- [ ] Use case diagram prepared
- [ ] Design considerations mapped to HCI principles
- [ ] Evidence of user research
- [ ] Working prototype demo practiced
- [ ] Evaluation plan outlined
- [ ] All team members know their parts
- [ ] Timing practiced (under 25 minutes)
- [ ] Backup screenshots prepared
- [ ] Q&A responses discussed

---

## Quick Reference: Kijiji-Trust Key Points

**Problem**: Manual Chama management lacks transparency and accessibility

**Solution**: Web app with group management, contribution tracking, emergency requests, and transparency logs

**Users**: Admins (30-55), Members (25-65), Treasurers (28-50)

**Tech**: Next.js + Firebase + Tailwind CSS

**HCI Focus**: Mobile-first, accessible, error-prevention, cultural sensitivity

**Evaluation**: Usability testing with 8-10 participants, SUS score, heuristic evaluation

---

**Good luck with your presentation! Remember to focus on demonstrating your understanding of user-centered design and HCI principles throughout.**


---

## Presentation Structure

### i. Start Slide

**Requirements:**
- Title of your project
- Names of all team members
- Registration numbers of all team members

**Example Title:**
> "Designing an Assistive Robot Game to Train Social Skills to Children with Autism"

**Template:**
```
Project Title: [Your Project Name]

Team Members:
- [Name 1] - [Registration Number]
- [Name 2] - [Registration Number]
- [Name 3] - [Registration Number]
- [Name 4] - [Registration Number]
```

---

### ii. Introduction / Scenario

**Requirements:**
- Brief description of your project scenario
- Clear statement of the goal
- Context in which the project operates

**Example Goal:**
> "To design a board game activity using the NAO robot to help children with autism develop social skills, such as eye contact."

**What to Include:**
- Problem statement
- Target audience
- Why this project matters
- What gap it fills
- Real-world context

---

### iii. Proposed Solution

**Requirements:**
- Describe your approach to solving the problem
- Include visualization or diagram depicting the application
- Explain how your solution addresses the scenario

**What to Include:**
- High-level overview of your solution
- Key features and functionality
- System architecture diagram or workflow visualization
- Screenshots or mockups (if available)
- How the solution meets user needs

**Visualization Types:**
- System architecture diagram
- User flow diagram
- Interface mockups
- Wireframes
- Conceptual diagrams

---

### iv. Requirements

**Requirements:**
- List both functional and non-functional requirements
- Clearly separate the two types
- Be specific and measurable

#### Functional Requirements
Requirements that describe what the system should do.

**Examples:**
- "The system should allow users to add their payment details."
- "The system should send notifications when a contribution is due."
- "Users should be able to create and manage groups."
- "The system should display real-time balance updates."
- "Members should be able to submit emergency requests."

#### Non-Functional Requirements
Requirements that describe how the system should perform.

**Examples:**
- **Security**: Payment details must be encrypted
- **Performance**: Pages should load within 2 seconds
- **Usability**: Interface should be accessible to users with varying technical skills
- **Reliability**: System uptime of 99.9%
- **Scalability**: Support up to 10,000 concurrent users
- **Accessibility**: WCAG 2.1 AA compliance

**Template:**
```
Functional Requirements:
FR1: [Specific action the system must perform]
FR2: [Another specific action]
...

Non-Functional Requirements:
NFR1: [Performance/quality attribute]
NFR2: [Security/reliability attribute]
...
```

---

### v. Users

**Requirements:**
- Describe the users of your application or product
- Include their needs and goals
- Explain how those needs informed your design

**What to Include:**
- User demographics
- User characteristics (technical skill level, age, background)
- Primary goals and motivations
- Pain points and challenges
- Context of use
- How understanding these users shaped your design decisions

**Example Structure:**
```
Target Users: [Describe who they are]

User Needs:
- Need 1: [Description] → Design Decision: [How you addressed it]
- Need 2: [Description] → Design Decision: [How you addressed it]

User Goals:
- Goal 1: [What they want to achieve]
- Goal 2: [Another objective]

How This Informed Design:
- [Specific design choice based on user research]
- [Another design choice]
```

---

### vi. Demonstrate Your Personas, Scenarios, and Use Case Diagrams

**Requirements:**
- Present the personas you've created
- Show typical usage scenarios
- Include use case diagrams illustrating user interactions

#### Personas
Create detailed user personas representing your target users.

**Persona Template:**
```
Name: [Persona Name]
Age: [Age range]
Occupation: [Job/Role]
Technical Proficiency: [Low/Medium/High]

Background:
- [Relevant background information]

Goals:
- [Primary goal]
- [Secondary goal]

Frustrations:
- [Pain point 1]
- [Pain point 2]

Quote: "[Something they might say]"
```

#### Scenarios
Describe realistic usage scenarios.

**Example:**
> "Sarah, a 45-year-old community leader, needs to set up a bereavement fund for her village. She creates a new group, invites 20 members, and sets monthly contributions of 500 KES per member."

#### Use Case Diagrams
Visual representation of user interactions with the system.

**Should Include:**
- Actors (users and external systems)
- Use cases (actions/functions)
- Relationships between them
- System boundaries

---

### vii. Design Considerations

**Requirements:**
- Explain design considerations for making your application usable
- Refer to specific design principles
- Include brief research about the user group
- Show how user characteristics influenced design

**Design Principles to Consider:**
- **Visibility**: Make important functions visible
- **Feedback**: Provide clear feedback for user actions
- **Constraints**: Prevent errors through design
- **Consistency**: Use familiar patterns
- **Affordance**: Make it clear how to interact
- **Mapping**: Logical relationship between controls and effects
- **Error Prevention & Recovery**: Help users avoid and recover from errors

**Example:**
> "Design considerations for older adults (over 65) might include:
> - Larger text (minimum 16px)
> - Simple navigation with clear labels
> - High contrast colors
> - Minimal scrolling
> - Clear error messages
> - Familiar metaphors"

**For Kijiji-Trust Consider:**
- **Mobile-first design**: Many users access via smartphones
- **Low-bandwidth optimization**: Users may have limited data
- **Multiple language support**: Diverse user base
- **Simple financial terminology**: Avoid complex jargon
- **Trust indicators**: Build confidence in financial transactions
- **Offline capability**: Work without constant internet connection
- **Accessibility**: Support for users with varying abilities

**Research Examples:**
- Studies on mobile money usage in East Africa
- Best practices for financial applications
- Cultural considerations for group savings systems
- Trust and transparency in digital platforms

---

### viii. Demo

**Requirements:**
- Demonstrate your initial prototype (Version 1)
- Show key features in action
- Walk through primary user flows

**Demo Preparation:**
1. **Prepare test data**: Have sample users, groups, and transactions ready
2. **Plan the flow**: Script your demonstration path
3. **Highlight key features**: Focus on most important functionality
4. **Show, don't tell**: Let the interface speak for itself
5. **Have backup**: Screenshots in case of technical issues

**What to Demonstrate:**
- User registration/login
- Core functionality (e.g., creating a group, making a contribution)
- Key differentiators of your solution
- User interface and navigation
- Mobile responsiveness (if applicable)

**Demo Tips:**
- Keep it concise (3-5 minutes)
- Focus on user value
- Explain what you're clicking and why
- Point out design considerations in action
- Be prepared for questions

---

### ix. Next Steps

**Requirements:**
- Mention what is next for your team project
- Include brief description of the evaluation process for the prototype

**What to Include:**

#### Immediate Next Steps
- Features to be added in Version 2
- Known issues to be fixed
- Design improvements planned

#### Evaluation Process
Describe how you will evaluate your prototype.

**Evaluation Methods:**
1. **Usability Testing**
   - Number of participants
   - Tasks they will perform
   - Metrics to measure (success rate, time, errors)

2. **User Interviews**
   - Questions to ask
   - Insights you're seeking

3. **Heuristic Evaluation**
   - Which heuristics you'll use
   - How violations will be addressed

4. **A/B Testing** (if applicable)
   - What variations you'll test
   - Success criteria

5. **Analytics**
   - What metrics you'll track
   - How they inform design decisions

**Example:**
> "Next Steps:
> - Conduct usability testing with 10 participants from our target user group
> - Implement feedback and iterate on the design
> - Add payment integration with M-Pesa
> - Develop mobile applications for iOS and Android
> - Evaluate using System Usability Scale (SUS) and task completion metrics
> - Plan for pilot launch with 3 community groups"

**Timeline Example:**
```
Week 1-2: Usability testing and feedback collection
Week 3-4: Iteration and improvements
Week 5-6: Feature completion
Week 7-8: Final evaluation and documentation
```

---

## Presentation Delivery Tips

### Time Management
- Allocate appropriate time to each section
- Practice to ensure you stay within time limit
- Have a timekeeper during presentation

### Visual Design
- Use consistent formatting
- Avoid cluttered slides
- Use high-quality images and diagrams
- Ensure text is readable from a distance

### Team Coordination
- Assign sections to team members
- Practice transitions between speakers
- Ensure everyone participates
- Have a backup presenter for each section

### Engagement
- Make eye contact with audience
- Speak clearly and at appropriate pace
- Invite questions at appropriate times
- Show enthusiasm for your project

---

## Marking Criteria (30 Marks Total)

While specific marking breakdown may vary, expect evaluation on:

- **Completeness**: All required sections included (5 marks)
- **Understanding**: Demonstration of HCI principles (5 marks)
- **User Research**: Quality of personas, scenarios, and user analysis (5 marks)
- **Design Rationale**: Justification of design decisions (5 marks)
- **Prototype**: Functionality and usability of demo (5 marks)
- **Presentation Quality**: Clarity, organization, and delivery (5 marks)

---

## Checklist

Before your presentation, ensure you have:

- [ ] Start slide with project title and all team member details
- [ ] Clear introduction and scenario description
- [ ] Proposed solution with visualizations
- [ ] Comprehensive list of functional requirements
- [ ] Comprehensive list of non-functional requirements
- [ ] Detailed user descriptions with needs and goals
- [ ] At least 2-3 personas created
- [ ] Realistic usage scenarios
- [ ] Use case diagram(s)
- [ ] Design considerations with reference to principles
- [ ] Research on your user group
- [ ] Working prototype demo prepared
- [ ] Next steps and evaluation plan outlined
- [ ] Presentation practiced and timed
- [ ] All team members prepared for their sections
- [ ] Backup plan for technical issues

---

## Good Luck!

Remember: This presentation is an opportunity to showcase your understanding of HCI principles and your ability to apply them to real-world problems. Focus on demonstrating user-centered design thinking throughout your project.
