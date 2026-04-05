# Treewalk Academy — PRD + DESIGN CONTEXT

## Overview
This document combines:
1. Product Requirements (what to build)
2. Product Intent (why it exists)
3. Design Philosophy (how decisions should be made when unspecified)

This is intentional.

The goal is to allow a coding agent or engineer to:
- Build the system
- Make correct decisions when gaps exist
- Preserve product quality without constant oversight

---

# 1. Product Intent (CRITICAL)

Treewalk Academy is NOT a generic LMS.

It is a **CPD-first learning environment for accountants** that must balance:

### 1. Compliance (baseline requirement)
- Users need defensible participation records
- Certificates must be credible
- Data must persist for 3 years

### 2. Engagement (primary success driver)
- Users should WANT to log in
- The product should feel modern and useful
- Avoid "compliance software" feel

### 3. Simplicity (strategic constraint)
- Minimal features
- Clear flows
- No unnecessary complexity

---

# 2. Core Product Philosophy

## 2.1 This is a Content Product
Courses are the product.

Everything should optimize for:
- Discovering courses
- Consuming content
- Completing learning

NOT:
- Admin complexity
- Feature bloat

---

## 2.2 Momentum Over Everything
The system should always answer:
> "What should I do next?"

Primary behavior:
- Resume learning instantly
- Reduce friction to zero

---

## 2.3 Soft Professional UX
Target user: CPA

Therefore:
- Clean and credible
- Slight warmth
- No playful or gimmicky UI
- No heavy enterprise feel

---

## 2.4 Dual System Design
The product has two modes:

### Learner Mode
- Emotional
- Content-driven
- Engaging

### Admin Mode
- Functional
- Dense
- Efficient

These SHOULD feel different.

---

# 3. Design System Direction

## Learner Experience
Inspired by:
- Spotify (content consumption)
- Airbnb (marketplace discovery)

## Admin Experience
Inspired by:
- PostHog (data + control systems)

---

# 4. Product Requirements

## Product Overview

### Objective
Build a modern, invite-only LMS that:
- Enables CPAs to complete verifiable learning
- Tracks participation over a 3-year window
- Provides a high-quality UX
- Supports video courses + live webinars (Teams)
- Generates defensible completion records

### Success Metrics
Primary:
- Weekly active users / invited users

Secondary:
- Course completion rate
- Repeat login frequency
- Monthly engagement

---

# 5. User Roles

### Learner
- Browse courses
- Enroll
- Watch
- Take quizzes
- Download certificates

### Instructor
- Create/edit own courses
- Manage content + quizzes

### Content Admin
- Approve/publish courses
- Adjust CPD hours

### HR Admin
- Invite/suspend users

### Super Admin
- Full system control
- Overrides

---

# 6. Core System Decisions

## Completion Logic
A course is complete ONLY if:
- 100% video watched
- Quiz passed (≥80%)

## CPD Hours
hours = round(video_minutes / 60, nearest 0.25)

## Retakes
- Unlimited
- Most recent pass = active

## Certificates
- Auto-generated
- Always downloadable

---

# 7. Experience Design Rules (VERY IMPORTANT)

When uncertain, follow these:

### Rule 1: Default to Simplicity
If two options exist → choose simpler

### Rule 2: Bias Toward Learner Experience
If admin vs learner conflict → prioritize learner

### Rule 3: Reduce Steps
Every extra click reduces engagement

### Rule 4: Avoid Enterprise UX
Do NOT:
- Overuse tables for learners
- Add unnecessary dashboards

### Rule 5: Make Progress Visible
Users should always see:
- What they’ve done
- What’s next

---

# 8. Page-Level Requirements (Condensed)

## Home
- Continue learning
- Recommended courses
- Upcoming webinars
- CPD snapshot

## Courses
- Marketplace with filters
- Card-based layout

## Course Player
- Video left
- Segments right
- No skipping

## Quiz
- Clean, focused
- One question at a time

## My Learning
- 3-year transcript
- Export + certificates

## Webinars
- Teams integration
- Convert to course after

---

# 9. Admin System

## Course Workflow
Draft → Review → Publish

## Core Capabilities
- Course creation
- User management
- Reporting

---

# 10. Tech Stack

- React frontend
- Supabase backend
- Mux video
- Teams webinars

---

# 11. Edge Case Philosophy

Always prefer:
- Predictable behavior
- Data integrity

Examples:
- 99% watched = not complete
- Updates do not invalidate past completions

---

# 12. Final Guiding Principle

The product should feel like:

> "A place I want to learn"

NOT:

> "A system I’m forced to use"

