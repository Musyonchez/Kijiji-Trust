# Kijiji-Trust: Digital "Chama" & Mutual Aid
## HCI Course Project - Team Assignment

---

## Project Context

**Course**: SFE 4010A – Human-Computer Interaction  
**Project Type**: Mid-semester Team Assignment  
**Focus**: User-centered design for community financial management

---

## 1. Introduction & Scenario

### Background
In East Africa and other regions, "Chamas" are traditional informal cooperative societies where community members pool resources to support each other during times of need (bereavement, medical emergencies, development projects). Currently, these groups rely on:
- Manual record-keeping (notebooks, spreadsheets)
- Cash-based contributions
- Face-to-face meetings
- Trust-based accountability

### Problem Statement
Current Chama management faces several challenges:
- **Lack of transparency**: Hard to track contributions and disbursements
- **Accessibility issues**: Members must attend physical meetings
- **Record-keeping errors**: Manual processes prone to mistakes
- **Trust concerns**: No independent verification of transactions
- **Limited reach**: Geographic constraints limit membership

### Project Goal
Design a user-friendly web application that digitizes Chama group management while maintaining the cultural values of trust, community, and mutual aid. The system should be accessible to users with varying levels of technical literacy.

---

## 2. Target Users

### Primary User Groups

#### 1. Group Administrators (Ages 30-55)
- **Characteristics**: Community leaders, moderate tech literacy
- **Goals**: Manage group, ensure fairness, maintain trust
- **Needs**: Simple tools to set up groups, track contributions, approve requests
- **Challenges**: May not be highly technical, need clear guidance

#### 2. Group Members (Ages 25-65)
- **Characteristics**: Diverse backgrounds, varying tech skills
- **Goals**: Track their contributions, access help when needed
- **Needs**: Easy contribution tracking, simple emergency request process
- **Challenges**: Some may have limited smartphone/computer experience

#### 3. Treasurers (Ages 28-50)
- **Characteristics**: Organized, detail-oriented, moderate tech skills
- **Goals**: Accurate financial tracking, generate reports
- **Needs**: Clear overview of all transactions, easy reporting tools
- **Challenges**: Need to reconcile digital and physical records

### User Research Insights
- Many users access internet primarily via smartphones
- Data costs are a concern (need lightweight design)
- Trust is paramount in financial applications
- Users value simplicity over feature-richness
- Cultural sensitivity is important (respect for traditional practices)

---

## 3. Core Features (MVP for Prototype)

### Feature 1: Group Management
- Create and join groups with invite codes
- Set basic group rules (contribution amount, frequency)
- Simple member list with contact information

### Feature 2: Contribution Tracker
- View personal contribution history
- See current group balance
- Mark contributions as paid (with admin verification)
- Simple visual indicators for payment status

### Feature 3: Emergency Request System
- Submit emergency requests with:
  - Type (bereavement/medical/other)
  - Amount needed
  - Brief description
- Group admin can approve/reject requests
- Members receive notifications of new requests

### Feature 4: Transparency Dashboard
- View all group transactions
- See who contributed and when
- Track emergency disbursements
- Simple, clear history log

---

## 4. Requirements

### Functional Requirements
1. Users must be able to create an account and log in securely
2. Admins must be able to create new groups with custom rules
3. Members must be able to join groups using invite codes
4. System must display current group balance in real-time
5. Members must be able to view their contribution history
6. Members must be able to submit emergency requests
7. Admins must be able to approve/reject emergency requests
8. System must send notifications for key events (new requests, approvals)
9. All transactions must be logged in the transparency dashboard
10. Users must be able to view group member list

### Non-Functional Requirements
1. **Usability**: Interface must be intuitive for users with basic smartphone skills
2. **Accessibility**: Minimum font size of 16px, high contrast colors
3. **Performance**: Pages must load within 3 seconds on 3G connection
4. **Security**: User authentication required, data encrypted in transit
5. **Reliability**: System should work offline with sync when connection restored
6. **Responsiveness**: Mobile-first design, works on screens 320px and above
7. **Localization**: Support for English and Swahili (future: more languages)
8. **Trust**: Clear visual indicators of data integrity and security

---

## 5. Design Considerations (HCI Principles Applied)

### Visibility & Feedback
- **Principle**: Users should know what the system is doing
- **Application**: 
  - Clear loading indicators
  - Confirmation messages after actions
  - Real-time balance updates
  - Status badges (paid/pending/overdue)

### Consistency
- **Principle**: Similar operations should work similarly
- **Application**:
  - Consistent navigation across all pages
  - Standard button styles (green=confirm, red=cancel)
  - Uniform layout patterns

### Error Prevention & Recovery
- **Principle**: Prevent errors where possible, make recovery easy
- **Application**:
  - Confirmation dialogs for critical actions (approving requests)
  - Input validation (e.g., amount must be positive number)
  - Clear error messages with guidance on how to fix

### Affordance & Constraints
- **Principle**: Make it clear what actions are possible
- **Application**:
  - Buttons look clickable with shadows/borders
  - Disabled states are visually distinct
  - Input fields clearly marked

### Simplicity & Minimal Cognitive Load
- **Principle**: Don't make users think unnecessarily
- **Application**:
  - Limited menu options (5-6 main features)
  - Progressive disclosure (advanced options hidden initially)
  - Clear, jargon-free language
  - Icons with text labels

### Mobile-First & Accessibility
- **Research Finding**: 70%+ of target users primarily use mobile devices
- **Application**:
  - Touch-friendly buttons (minimum 44x44px)
  - Thumb-reachable navigation
  - Large, readable text (minimum 16px)
  - High contrast (WCAG AA standard)
  - Support for screen readers

### Cultural Sensitivity
- **Research Finding**: Users value traditional Chama practices
- **Application**:
  - Use familiar terminology ("Group" vs "Organization")
  - Reflect traditional roles (Admin, Treasurer, Member)
  - Visual design respects cultural context

---

## 6. Technology Stack (Prototype)

### Frontend
- **Next.js**: React-based framework for web application
- **Tailwind CSS**: Utility-first CSS for responsive design

### Backend & Database
- **Firebase Authentication**: Secure user login
- **Firebase Firestore**: Real-time database for contributions and transactions
- **Firebase Hosting**: Deploy the prototype

### Rationale
- **Rapid prototyping**: Firebase allows quick MVP development
- **Real-time updates**: Essential for transparency and trust
- **No backend coding**: Focus on user experience design
- **Free tier**: Suitable for academic project scale

---

## 7. Simplified Database Structure

```
Users Collection
├── userId
├── name
├── email
├── phone
└── joinedGroups[]

Groups Collection
├── groupId
├── groupName
├── adminId
├── contributionAmount
├── currentBalance
└── members[]

Contributions Collection
├── contributionId
├── groupId
├── userId
├── amount
├── date
└── status (pending/verified)

EmergencyRequests Collection
├── requestId
├── groupId
├── requesterId
├── type
├── amount
├── description
├── status (pending/approved/rejected)
└── dateCreated
```

---

## 8. Success Criteria for Prototype

### Usability Goals
1. New users can create an account and join a group within 5 minutes
2. Users can view their contribution status within 2 clicks from homepage
3. Admins can process an emergency request within 3 clicks
4. 80%+ task completion rate in usability testing
5. System Usability Scale (SUS) score of 70+

### Technical Goals
1. Working authentication system
2. Create and join groups functionality
3. Basic contribution tracking
4. Emergency request submission and approval
5. Responsive design working on mobile and desktop

---

## 9. Project Scope (What's Included in Prototype V1)

### ✅ Included
- User registration and login
- Create/join groups
- View group balance and member list
- Log contributions (manual entry for prototype)
- Submit emergency requests
- Admin approve/reject requests
- Basic transparency log
- Mobile-responsive design

### ❌ Not Included (Future Versions)
- Actual payment integration (M-Pesa, etc.)
- SMS/email notifications (just in-app for now)
- Complex analytics and reports
- Multi-language support
- File/photo uploads
- Advanced security features
- Group-to-group features

---

## Summary

**Kijiji-Trust** is a focused HCI student project that demonstrates user-centered design principles applied to a real-world problem. By digitizing traditional community savings groups (Chamas), the project showcases:

- Understanding of diverse user needs
- Application of HCI design principles
- Mobile-first, accessible interface design
- Rapid prototyping with modern web technologies
- Evaluation through usability testing

The scope is intentionally limited to what's achievable in a semester project while still delivering meaningful value and demonstrating core HCI competencies.
