# Kijiji-Trust Implementation Plan
## Step-by-Step Development Roadmap

**Project**: Digital Chama & Mutual Aid Platform  
**Timeline**: 3 weeks  
**Goal**: Working prototype for CAT 1 presentation

---

## Overview

This plan breaks down the development into **manageable daily tasks** to build a working prototype without overwhelming the team. Focus is on core functionality that demonstrates HCI principles.

---

## Phase 1: Preparation (Days 1-3)

### Day 1: Project Setup & Planning

**Morning: Initialize Project**
```bash
# Navigate to project directory
cd ~/Code/Kijiji-Trust

# Create Next.js app
npx create-next-app@latest . --typescript --tailwind --app --no-src-dir

# Install additional dependencies
npm install firebase react-icons date-fns
```

**Configuration choices:**
- ✅ TypeScript
- ✅ Tailwind CSS
- ✅ App Router (not Pages Router)
- ❌ No src directory (keep it simple)

**Afternoon: Firebase Setup**
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create new project: "Kijiji-Trust"
3. Enable Authentication (Email/Password provider)
4. Create Firestore Database (Start in test mode)
5. Get Firebase config (Project Settings → General → Your apps)
6. Create `.env.local` file with Firebase credentials

**Evening: Project Structure**
```
Kijiji-Trust/
├── app/
│   ├── (auth)/
│   │   ├── login/
│   │   └── register/
│   ├── dashboard/
│   ├── groups/
│   │   ├── create/
│   │   └── join/
│   ├── requests/
│   │   ├── new/
│   │   └── [id]/
│   └── layout.tsx
├── components/
│   ├── ui/          # Buttons, inputs, cards
│   ├── groups/      # Group-related components
│   └── requests/    # Request-related components
├── lib/
│   ├── firebase.ts  # Firebase config
│   └── hooks/       # Custom React hooks
└── docs/            # Already created
```

**Deliverables:**
- ✅ Next.js project initialized
- ✅ Firebase project created
- ✅ Project structure planned
- ✅ Dependencies installed

---

### Day 2: Design Personas & Scenarios

**Morning: Create Personas (2-3)**

Use templates from doc 2, customize:

**Persona 1: Admin**
- Name, age, background
- Technical skill level
- Goals and frustrations
- Quote

**Persona 2: Member**
- Different demographic
- Different needs
- Different challenges

**Persona 3: Treasurer (Optional)**
- If time permits

**Afternoon: Write Scenarios (2-3)**

**Scenario 1**: Admin creating and setting up a group  
**Scenario 2**: Member submitting emergency request  
**Scenario 3**: Admin approving request and member receiving notification

Make them realistic and specific (use real names, amounts, contexts)

**Evening: Use Case Diagram**

Create simple diagram showing:
- Actors: Admin, Member, System
- Use Cases: Login, Create Group, Join Group, Submit Request, Approve Request, View Dashboard
- Relationships

**Tools**: Draw.io, Lucidchart, or even PowerPoint

**Deliverables:**
- ✅ 2-3 detailed personas
- ✅ 2-3 realistic scenarios
- ✅ Use case diagram

---

### Day 3: Wireframes & Design System

**Morning: Sketch Wireframes**

Hand-draw or use Figma for 5 key screens:
1. Login page
2. Dashboard (group overview)
3. Create group form
4. Submit emergency request form
5. Admin approval view

Keep it simple - boxes and labels are fine.

**Afternoon: Define Design System**

Based on HCI principles:

**Colors**:
- Primary: Green (trust, money, growth) - #10B981
- Secondary: Blue (security) - #3B82F6
- Success: #22C55E
- Warning: #F59E0B
- Error: #EF4444
- Neutral: Grays

**Typography**:
- Font: Inter or default system fonts
- Headings: 24px, 20px, 18px
- Body: 16px (minimum for accessibility)
- Small: 14px

**Components**:
- Buttons: 44px height (touch-friendly)
- Input fields: 48px height
- Cards: Rounded corners, subtle shadow
- Spacing: 8px base unit

**Evening: Mobile-First Layout**

Plan responsive breakpoints:
- Mobile: 320px - 640px
- Tablet: 641px - 1024px
- Desktop: 1025px+

**Deliverables:**
- ✅ Wireframes for 5 key screens
- ✅ Design system defined
- ✅ Ready to start coding

---

## Phase 2: Core Development (Days 4-14)

### Days 4-5: Authentication System

**Day 4 Morning: Firebase Configuration**

Create `lib/firebase.ts`:
```typescript
// Firebase initialization
// Auth configuration
// Firestore configuration
```

Create `lib/auth-context.tsx`:
```typescript
// AuthContext for global auth state
// useAuth hook
// Login, register, logout functions
```

**Day 4 Afternoon: Register Page**

Create `app/(auth)/register/page.tsx`:
- Email input
- Password input (with confirmation)
- Name input
- Register button
- Link to login page
- Form validation
- Error handling

**Day 5 Morning: Login Page**

Create `app/(auth)/login/page.tsx`:
- Email input
- Password input
- Login button
- Link to register page
- Error handling
- Loading states

**Day 5 Afternoon: Protected Routes**

Create middleware or route protection:
- Redirect to login if not authenticated
- Redirect to dashboard if authenticated and on login page

**Test**:
- ✅ User can register
- ✅ User can login
- ✅ User can logout
- ✅ Protected routes work

---

### Days 6-7: Group Management

**Day 6 Morning: Firestore Setup**

Define collections in Firestore:

**users** collection:
```
{
  uid: string
  email: string
  name: string
  joinedGroups: string[]
  createdAt: timestamp
}
```

**groups** collection:
```
{
  id: string
  name: string
  adminId: string
  contributionAmount: number
  currentBalance: number
  members: string[]
  createdAt: timestamp
}
```

**Day 6 Afternoon: Create Group**

Create `app/groups/create/page.tsx`:
- Group name input
- Contribution amount input
- Create button
- Generate simple group code (can be first 6 chars of group ID)
- Add admin as first member
- Save to Firestore

**Day 7 Morning: Join Group**

Create `app/groups/join/page.tsx`:
- Group code input
- Join button
- Look up group by ID
- Add user to group members
- Add group to user's joinedGroups
- Redirect to dashboard

**Day 7 Afternoon: Group List**

Create component to display user's groups:
- List all groups user is member of
- Show group name, balance, member count
- Click to view group dashboard

**Test**:
- ✅ Admin can create group
- ✅ User can join group with code
- ✅ Groups display correctly

---

### Days 8-9: Dashboard & Contribution Tracking

**Day 8 Morning: Dashboard Layout**

Create `app/dashboard/page.tsx`:
- Welcome message with user name
- Group selector (if user in multiple groups)
- Current group balance (large, prominent)
- Member count
- Quick stats

**Day 8 Afternoon: Group Members View**

Display all group members:
- Member names
- Join date
- Role badge (Admin/Member)
- Simple list or card layout

**Day 9 Morning: Contribution History**

Create **contributions** collection:
```
{
  id: string
  groupId: string
  userId: string
  userName: string
  amount: number
  status: 'pending' | 'verified'
  date: timestamp
}
```

Create form to manually log contribution:
- Amount input (default to group contribution amount)
- Submit button
- Status starts as 'pending'
- Admin can mark as 'verified' (simple button click)

**Day 9 Afternoon: Contribution Display**

Show contribution history:
- User's own contributions
- All group contributions (transparency)
- Status badges (paid/pending)
- Date formatting

**Test**:
- ✅ Dashboard displays correctly
- ✅ Can log contributions
- ✅ Can view contribution history
- ✅ Admin can verify contributions

---

### Days 10-11: Emergency Request System

**Day 10 Morning: Create Request**

Define **emergencyRequests** collection:
```
{
  id: string
  groupId: string
  requesterId: string
  requesterName: string
  type: 'bereavement' | 'medical' | 'other'
  amount: number
  description: string
  status: 'pending' | 'approved' | 'rejected'
  createdAt: timestamp
  resolvedAt: timestamp | null
}
```

Create `app/requests/new/page.tsx`:
- Type selector (dropdown)
- Amount input
- Description textarea
- Submit button
- Validation (amount > 0, description not empty)

**Day 10 Afternoon: View Requests**

Create request list view:
- Show all pending requests
- Show request details (type, amount, description, requester)
- Status badges
- Different views for admin vs member

**Day 11 Morning: Approve/Reject (Admin Only)**

Create admin actions:
- Approve button (green)
- Reject button (red)
- Confirmation dialog ("Are you sure?")
- Update request status in Firestore
- Update group balance (subtract amount if approved)

**Day 11 Afternoon: Request Details Page**

Create `app/requests/[id]/page.tsx`:
- Full request details
- Requester information
- Status history
- Action buttons (if admin and pending)

**Test**:
- ✅ Member can submit request
- ✅ Requests display correctly
- ✅ Admin can approve/reject
- ✅ Balance updates on approval
- ✅ Status updates correctly

---

### Days 12-13: Transparency Log & Polish

**Day 12 Morning: Transaction Log**

Create **transactions** collection (or use combined view):
```
{
  id: string
  groupId: string
  type: 'contribution' | 'disbursement'
  amount: number
  userId: string
  userName: string
  description: string
  timestamp: timestamp
}
```

Automatically create transaction when:
- Contribution is verified
- Request is approved

**Day 12 Afternoon: Transparency Dashboard**

Create `app/transparency/page.tsx`:
- Display all transactions chronologically
- Filter by type (contributions/disbursements)
- Show running balance
- Clear visual timeline

**Day 13: UI/UX Polish**

Focus on HCI principles:

**Visibility & Feedback**:
- Add loading spinners
- Success/error toast notifications
- Clear button states (disabled, loading, active)

**Consistency**:
- Use same button styles throughout
- Consistent spacing
- Uniform card layouts

**Error Prevention**:
- Form validation with clear messages
- Confirmation dialogs for critical actions
- Disable buttons while processing

**Mobile Responsiveness**:
- Test on mobile viewport (Chrome DevTools)
- Adjust layouts for small screens
- Touch-friendly button sizes

**Test**:
- ✅ Transparency log displays all activities
- ✅ UI is consistent across pages
- ✅ Mobile responsive
- ✅ Loading states work
- ✅ Error handling works

---

### Day 14: Testing & Bug Fixes

**Morning: Internal Testing**

Test all user flows:
1. Register → Login → Create Group → Get Code
2. Register → Login → Join Group (with code)
3. Log Contribution → Admin Verify
4. Submit Emergency Request → Admin Approve
5. View Transparency Log
6. Logout → Login again

**Create test checklist**:
- [ ] Registration works
- [ ] Login works
- [ ] Create group works
- [ ] Join group works
- [ ] Dashboard loads correctly
- [ ] Contributions can be logged
- [ ] Requests can be submitted
- [ ] Admin can approve/reject
- [ ] Balance updates correctly
- [ ] Transparency log shows all transactions
- [ ] Mobile responsive
- [ ] Error handling works

**Afternoon: Fix Critical Bugs**

Priority:
1. Anything that breaks the demo flow
2. Visual issues on mobile
3. Confusing error messages
4. Missing loading states

**Evening: Prepare Demo Data**

Create test accounts:
- Admin account (admin@test.com)
- Member accounts (2-3 users)
- Sample group with some history
- Mix of verified contributions
- Mix of approved/pending/rejected requests

This gives you a clean starting point for the demo.

**Deliverables**:
- ✅ All 7 core features working
- ✅ Critical bugs fixed
- ✅ Demo data prepared
- ✅ Mobile responsive

---

## Phase 3: Presentation Prep (Days 15-21)

### Days 15-16: Create Presentation Slides

**Day 15: Slides 1-5**

Follow structure from doc 2:

**Slide 1**: Title slide
- Project name
- Team members
- Course

**Slides 2-3**: Introduction/Scenario
- What are Chamas
- Current problems
- Project goal

**Slides 4-5**: Proposed Solution
- Solution overview
- System diagram (with screenshots)
- Four core features

**Day 16: Slides 6-9**

**Slides 6-7**: Requirements
- Functional requirements (10 items)
- Non-functional requirements (8 items)

**Slides 8**: Users
- 3 user types with characteristics

**Slide 9**: Personas
- Display 2-3 personas created on Day 2

**Deliverables**:
- ✅ Complete slide deck (30-40 slides total)
- ✅ Screenshots embedded
- ✅ Diagrams included

---

### Days 17-18: Demo Preparation & Scenarios

**Day 17 Morning: Demo Script**

Write step-by-step script:

```
1. [Homepage] "This is Kijiji-Trust landing page..." (15 sec)
2. [Register] "Let me register as a group admin..." (30 sec)
3. [Create Group] "Now I'll create a Chama group..." (60 sec)
4. [Get Code] "The system generates this invite code..." (15 sec)
5. [Switch Account] "Now from a member's perspective..." (15 sec)
6. [Join Group] "Using the invite code to join..." (45 sec)
7. [Dashboard] "Member sees the group dashboard..." (30 sec)
8. [Submit Request] "Submitting an emergency request..." (60 sec)
9. [Switch to Admin] "Back to admin account..." (15 sec)
10. [Approve Request] "Admin reviews and approves..." (45 sec)
11. [Transparency Log] "All actions are logged..." (30 sec)
```

Total: ~6 minutes

**Day 17 Afternoon: Practice Demo Solo**

Each team member:
- Practices the full demo flow
- Times each section
- Identifies potential issues
- Prepares for what to say

**Day 18: Team Practice**

**Morning**: Full run-through
- Assign sections to team members
- Practice transitions
- Time the full presentation (aim for 20-25 min)

**Afternoon**: Refinement
- Adjust timing
- Smooth transitions
- Prepare for questions

**Evening**: Backup Plan
- Take screenshots of each demo step
- Export presentation as PDF
- Test on presentation computer/projector if possible

**Deliverables**:
- ✅ Demo script written
- ✅ Full presentation practiced
- ✅ Backup screenshots ready

---

### Days 19-20: Usability Testing (Optional but Recommended)

**Day 19: Quick Testing**

Find 3-5 people (friends, classmates):

**Tasks**:
1. "Register and join this group: [code]"
2. "Check your contribution status"
3. "Submit an emergency request for medical expenses"

**Observe**:
- Where do they struggle?
- What's confusing?
- How long does each task take?
- Any errors?

**Day 20: Quick Improvements**

Based on feedback:
- Fix top 2-3 confusing things
- Improve error messages
- Add clarifying labels
- Test again quickly

**Deliverables**:
- ✅ User feedback collected
- ✅ Critical improvements made
- ✅ Better user experience

---

### Day 21: Final Preparations

**Morning: Final Polish**
- Review all slides
- Spell check
- Ensure screenshots are current
- Verify demo data is loaded

**Afternoon: Dress Rehearsal**
- Full presentation with timer
- Someone plays professor and asks questions
- Record on phone to watch back
- Fine-tune timing

**Evening: Submission Prep**
- Export presentation
- Prepare any required documents
- Charge laptop
- Test internet connection
- Get good sleep!

**Deliverables**:
- ✅ Presentation polished
- ✅ Demo tested
- ✅ Team confident
- ✅ Ready to present!

---

## Development Best Practices

### Version Control

Use Git throughout:

```bash
# Initial commit
git init
git add .
git commit -m "Initial Next.js setup"

# Feature branches (optional)
git checkout -b feature/auth
git checkout -b feature/groups
git checkout -b feature/requests

# Regular commits
git add .
git commit -m "Add user registration"
git commit -m "Create group dashboard"
git commit -m "Implement emergency requests"

# Push to GitHub
git remote add origin [your-repo-url]
git push -u origin main
```

### Code Organization

**Keep it simple**:
- One feature per file
- Reusable components in `/components`
- Firebase logic in `/lib`
- Don't over-engineer

**Comment your code**:
```typescript
// ADMIN ONLY: Approve emergency request
// This updates the request status and deducts from group balance
```

### Testing as You Go

After each feature:
1. Test the happy path (everything works)
2. Test edge cases (empty fields, wrong data)
3. Test on mobile view
4. Test as different user roles

---

## Troubleshooting Guide

### Common Issues

**Firebase Connection Issues**:
- Check `.env.local` variables
- Verify Firebase config is correct
- Check Firestore rules (should be in test mode)

**Authentication Not Persisting**:
- Use Firebase onAuthStateChanged
- Implement proper loading states
- Check browser cookies aren't blocked

**Data Not Updating**:
- Check Firestore rules
- Verify user has write permissions
- Use Firebase console to verify data

**TypeScript Errors**:
- Can ignore with `// @ts-ignore` if needed
- Or use `any` type temporarily
- Focus on functionality first

**Styling Issues**:
- Use Tailwind classes correctly
- Check responsive breakpoints
- Test in Chrome DevTools mobile view

---

## Team Collaboration Tips

### Divide & Conquer

**Option 1**: By Features
- Person A: Auth + Groups
- Person B: Dashboard + Contributions
- Person C: Requests + Transparency
- Person D: UI/UX + Presentation

**Option 2**: By Role
- Person A: Frontend (all pages)
- Person B: Firebase (all backend)
- Person C: UI/Design (styling)
- Person D: Testing + Documentation

### Communication

**Daily Check-ins** (15 min):
- What did you complete?
- What are you working on today?
- Any blockers?

**Tools**:
- WhatsApp group for quick questions
- GitHub for code
- Google Docs for presentation
- Shared Figma for designs

---

## Success Checklist

### Week Before Presentation

- [ ] All 7 core features working
- [ ] Demo data loaded
- [ ] Presentation slides complete
- [ ] Personas & scenarios finalized
- [ ] Use case diagram created
- [ ] Practice demo 2+ times

### Day Before Presentation

- [ ] Final practice (full team)
- [ ] Screenshots updated
- [ ] Demo tested on presentation device
- [ ] Backup plan ready
- [ ] Questions prepared for
- [ ] Dress code decided
- [ ] Time and location confirmed

### Presentation Day

- [ ] Laptop charged
- [ ] Presentation file on USB (backup)
- [ ] Internet connection tested
- [ ] Demo account credentials handy
- [ ] Team members present
- [ ] Confidence high! 💪

---

## What Could Go Wrong (and Backup Plans)

**Demo doesn't work**:
→ Use screenshots, walk through as if it's working

**Internet down**:
→ Run on localhost, show Firestore console separately

**Forgot login credentials**:
→ Write them down before presentation

**Feature breaks last minute**:
→ Skip that feature, mention it's in development

**Run out of time**:
→ Skip use case details, focus on demo

**Hard questions**:
→ "Great question! That's in our future iterations..."

---

## Post-Presentation

### After CAT 1

If you want to continue:
1. Implement user feedback
2. Add missing features
3. Improve UI
4. Deploy to Vercel
5. Portfolio piece!

But for now: **Focus on passing CAT 1!** 🎯

---

## Quick Reference Commands

```bash
# Run development server
npm run dev

# Build for production (if needed)
npm run build

# Check for TypeScript errors
npm run type-check

# Git shortcuts
git add .
git commit -m "Your message"
git push
```

---

## Timeline At-a-Glance

| Week | Days | Focus | Deliverable |
|------|------|-------|-------------|
| 1 | 1-3 | Setup & Planning | Project initialized, personas, wireframes |
| 2 | 4-11 | Core Development | Auth, groups, dashboard, requests working |
| 2 | 12-14 | Testing & Polish | Transparency log, bug fixes, demo data |
| 3 | 15-18 | Presentation | Slides, demo script, practice |
| 3 | 19-21 | Final Prep | User testing, refinement, rehearsal |

---

## Remember

✅ **Done is better than perfect**  
✅ **Focus on demonstrating HCI principles**  
✅ **Working demo > beautiful design**  
✅ **Practice makes confident**  
✅ **You got this!** 🚀

---

**Good luck with Kijiji-Trust! Follow this plan and you'll have a solid prototype and presentation ready in 3 weeks.**
