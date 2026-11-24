# Zewail Pulse — Campus Event & Student Club Hub
## Frontend Prototype Scaffold (Phase 2 SRS Alignment)

**Course:** CSAI 203 - Fall 2026: Introduction to Software Engineering  
**Institution:** University of Science and Technology · Zewail City of Science, Technology and Innovation  
**Team 17:** Omar Ashraf (Team Leader), Ahmad Magdy, Abdelrahman Rabee  
**Stitch Project ID:** `8205380253736676900` ("Frontend Prototype Scaffold")

---

## 📌 Project Overview
This repository contains the standalone, frontend-only prototype for **Zewail Pulse**, implementing the complete set of interactive screens designed in Google Stitch and connecting them seamlessly according to the project's Software Requirements Specification (SRS Phase 2).

All backend operations have been replaced with **functional frontend placeholders, interactive state toggles, modals, and responsive toast notifications**, requiring **zero server, database, or backend logic**.

All assets, avatars, club photography, and screenshots have been downloaded locally under `assets/images/` and `screenshots/` for offline-first reliability.

---

## 📱 Complete Screen Architecture

| # | Screen Name | File | Stitch Screen ID | Key SRS Functional Requirements |
|---|---|---|---|---|
| **1** | **Student Login** | [`login.html`](login.html) / [`index.html`](index.html) | `b36121c3532445ff831584da2bb9ca01` | **FR-01** (User Registration & 24h Token), **FR-02** (Lockout Guards, Single-Role Account, Password Reset) |
| **2** | **Student Dashboard** | [`dashboard.html`](dashboard.html) | `9f717ce8b505486698aced1cfa18af6c` | **FR-04** (Personal Activity Timeline, Unread Badges), **FR-07** (Event Fast Pass QR), **FR-08** (24h Reminders) |
| **3** | **Campus Events Board** | [`events.html`](events.html) | `01016ec3eb85418982acc93a39ed9cb3` | **FR-05** (Multi-Tag Filtering, Grid/Calendar Toggle), **FR-06** (Live Capacity Tracking), **FR-07** (Roster Sign-Up) |
| **4** | **Dedicated Event Details** | [`event-details.html`](event-details.html) | *Harmonized Detail Screen* | **FR-06** (Live Capacity Meter, Venue Waypoints, Syllabus), **FR-07** (Fast Pass Terminal QR), **FR-14** (Q&A Thread) |
| **5** | **Club Directory** | [`clubs.html`](clubs.html) | `6bd464c37a0548b099e48f9f24410766` | **FR-09** (Public Club Directory), **FR-10** (Open Enrollment vs Application), **FR-18** (Club Charter Submission) |
| **6** | **Club Showcase (Non-Member)** | [`club-showcase.html`](club-showcase.html) | `61c2b69b8e15459b9fdf2a15051b8f16` | **FR-09** (Showcase Branding & Leadership), **FR-10** (Application Dossier Drawer), **FR-14** (Interactive Q&A) |
| **7** | **Club Member Portal** | [`club-portal.html`](club-portal.html) | `6dbae150122c48c990ed1c75db7b2550` | **FR-12** (Member Departure), **FR-13** (Pinned Announcements & Budget Ledger), **FR-16** (Event Proposal Guard) |
| **8** | **Student Profile & Credentials** | [`profile.html`](profile.html) | `b103ae56269d4c04a75c965a0c0d71d3` | **FR-03** (Editable Profile, 500-char Bio, Extracurricular Standing, Academic Transcript Verification) |

---

## 🎯 Implementation of Specific User Requirements

### 1. Events Board Single Event Screen Navigation
- On `events.html`, clicking **any event card, title, or "View Event Details" button** navigates directly to [`event-details.html`](event-details.html).
- `event-details.html` showcases full logistical specs for the *Autonomous Rover Workshop: ROS 2 & LiDAR Sensor Fusion*:
  - **Venue & Room:** Nano Tech Building • Room 102
  - **Time & Schedule:** Tomorrow, Nov 18, 2026 • 2:00 PM – 5:00 PM
  - **Live Capacity Meter (FR-06):** 42 / 50 seats filled (84% capacity) with real-time registrar sync indicator
  - **Fast Pass Entry Badge (FR-07):** Scannable terminal QR pass
  - **Syllabus & Agenda:** 3-stage hands-on pipeline (ROS 2 nodes, SLAM 2D mapping, rover hardware test)
  - **Discussion & Q&A (FR-14):** Interactive inquiry forum with placeholder submit

### 2. Events Board Monthly Calendar View
- Toggling the **"Monthly Calendar View"** button on `events.html` cleanly hides the feed and renders the **November 2026 Academic Term Calendar**:
  - Full 7-column layout (Sunday through Saturday, 35 day cells).
  - Prominent scheduled event chips (Convocation, Deep Learning Bootcamp, Stargazing Night, Rover Workshop).
  - **Clicking any event chip in the calendar** also opens [`event-details.html`](event-details.html) (or [`club-showcase.html`](club-showcase.html) for club fairs).
  - Month navigation controls (`<` and `>`) with interactive toast feedback.
  - One-click **"Sync to Calendar (.ics)"** export placeholder.

### 3. Club Directory Unregistered Clubs Navigation
- On `clubs.html`, all buttons and title links for unregistered clubs (*GDSC Zewail, Zewail Astronomy Society, Biotech Syndicate, Zewail Debate & MUN, Fall Club Exposition*) route to the public inspection showcase: [`club-showcase.html`](club-showcase.html).
- The inspection page includes the club leadership breakdown, upcoming general meetings, public gallery, and the **FR-10 Application Dossier Drawer**.

### 4. Registered Club Member Portal Button
- On `clubs.html`, the card for **Zewail Robotics Club** (the active membership club) has an **"Open Member Portal"** button that routes directly to [`club-portal.html`](club-portal.html).
- `club-portal.html` includes meeting RSVP toggles, budget ledger transparency (**FR-13**), internal discussion threads, and the **FR-12 "Leave Club" modal**.

### 5. Student Profile Integration & Universal Header Dropdown
- Integrated the newly added Stitch screen: **Student Profile - Zewail Pulse** (`b103ae56269d4c04a75c965a0c0d71d3`) as [`profile.html`](profile.html).
- Features live bio character counter (500 char max per FR-03), academic Standing badge (*Junior • CGPA 3.84*), active club affiliations, dispatch toggles (FR-08), and credential save placeholder with toast notification.
- **Universal Profile Dropdown:** Added a prominent **"Student Profile (FR-03)"** action in the top-right profile dropdown menu across **all** authenticated screens (`dashboard.html`, `events.html`, `event-details.html`, `clubs.html`, `club-showcase.html`, `club-portal.html`, `profile.html`).

---

## 🚀 How to Run the Prototype

Since this is a pure HTML5 + Tailwind CSS + Vanilla JS implementation, no server or build step is required:

### Option A: Double-Click
Double-click [`login.html`](login.html) or [`dashboard.html`](dashboard.html) in your file explorer to open directly in any modern browser.

### Option B: Local HTTP Server (Python / Node / VS Code Live Server)
```bash
# Using Python 3:
cd "D:\Astronial\College\GitHub Projects\Demo event campus"
python -m http.server 8000
# Open http://localhost:8000 in your browser
```

---

## 🎨 Design System Specifications
- **Theme:** Navy (`#0b1d3a`), Electric Blue (`#0056b3`), Warm Amber (`#d97706`), Neutral Gray (`#f4f6f9`)
- **Typography:** Inter (Headlines, Body, Labels)
- **Icons:** Google Material Symbols Outlined
- **Styling:** Tailwind CSS CDN v3.4+
- **Responsive:** Fluid layout supporting Mobile, Tablet, and Desktop (1440px container).
