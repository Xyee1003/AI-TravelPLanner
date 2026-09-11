# Pocket Trip by The Last 4

**Team:** Kam Pue Shan, Faustina Lai Wan Yee, Tan Wen Jie, Tang Xin Yee  
**Problem Statement:** Lifestyle Track: Planning an Escape (Travel Planner)  
**Video Presentation:** [Unlisted Youtube Link]  
**Presentation Slides:** [Public Link]  

---

## 1. Project Overview

### The Problem
Planning group trips or dynamic escapes is currently fragmented across group chats, booking engines, and spreadsheet trackers. The core issues stem from three key pain points:
1. **High Group Friction:** Aligning individual budgets, daily pacing, and activity preferences across group members leads to endless debate and compromises.
2. **Static Plans vs. Real-Time Disruptions:** Flight delays, sudden rainstorms, or closed venues break static itineraries, leaving travelers without dynamic guidance.
3. **Disconnected Expenses:** Expense tracking happens separately from the itinerary, making post-trip cost calculations tedious.

* **Target Stakeholders:** Solo travelers, group organisers, and friend groups with mixed budgets and preferences.
* **Existing Alternatives & Shortfalls:** 
  * *Wanderlog / TripIt:* Great for static itineraries, but fail at real-time preference balancing and automated mid-trip re-planning when disruptions happen.
  * *Splitwise:* Manages shared costs well, but operates completely isolated from daily schedules and travel routes.

### Our Solution
An AI-powered collaborative travel assistant that eliminates group decision friction, dynamically clusters daily activities, and adapts plans on the fly during disruptions. By combining group preference vectors with real-time location and flight feeds, it turns complex travel planning into a single, effortless workflow.

* **Geo-Clustered Smart Routing:** Automatically groups nearby activities based on live transit time and geographic proximity.
* **Democratic Coordination:** Balances group consensus with personal freedom, ensuring trip logistics never strain personal relationships.
* **Disruption Handler:** Re-optimizes remaining day plans in seconds when hit by delays.
* **Context-Aware Shared Ledger:** Auto-calculates individual cost shares linked directly to active itinerary stops.

---

## 2. Ideation & Process

### 2.1 Ideas We Considered

| Idea | Why it was dropped / kept |
| :--- | :--- |
| **Disruption Handler (Chosen)** | **Kept:** Directly solves the major pain point of live mid-trip disruptions (flight delays, bad weather) without forcing manual schedule rebuilds. |
| **Group Harmony Preference (Chosen)** | **Kept:** Smart scheduling that balances shared must-sees with solo breaks, ensuring nobody feels dragged along or ignored. |
| **Context-Aware Split Ledger (Chosen)** | **Kept:** Integrates expense settlements directly into daily itinerary stops rather than using a third-party app. |
| **Native Flight & Hotel Booking Engine** | **Dropped:** High licensing complexity and API cost for a hackathon. Opted for affiliate live pricing previews via API instead. |
| **In-App Shared Album** | **Dropped:** Additional feature that strays away from core planning, budgeting, and disruption management goals. |

---

### 2.2 Ideation Boards

![First Draft](firstdraft.png)
*Figure 2.1: Initial application design and feature roadmap.*

![Problem Tree](docs/problem_tree.png)
*Figure 2.2: Problem tree analysing key usability and planning issues identified in the first draft.*

![Final Draft](finaldraft.png)
*Figure 2.3: Refined application architecture highlighting key iterations from the initial draft.*

![User Flow Diagram](docs/user_flow.png)
*Figure 2.4: User journey from group preference synchronization to live mid-trip itinerary re-planning.*

![Crazy Eights Scribbles](docs/crazy_eights.png)
*Figure 2.3: Initial UI layout sketches evaluating list-based vs. map-centric dynamic itinerary views.*

---

### 2.3 Mentor Consultation

| Date | Mentor | Feedback Received | What Was Changed |
| :--- | :--- | :--- | :--- |
| 2026-09-08 | [Mentor Name] | "Full native booking transactions are too broad for a hackathon. Focus heavily on solving group conflict and dynamic disruption recovery." | Pivoted away from native transaction flows; shifted full focus to the Pivot Engine and Group Harmony quiz algorithms. |
| 2026-09-10 | [Mentor Name] | "Make sure cost splitting automatically reacts when an itinerary item gets dropped during dynamic re-planning." | Updated database schema so ledger items link to dynamic itinerary node IDs, auto-updating balances when stops drop. |

---

## 3. Design & Prototype

**UI Prototype:** [Public Link to Figma / Canva / Web Prototype]

| Screen Preview | Feature & Interaction Description |
| :---: | :--- |
| ![Screen 1](docs/screen1.png) | **Group Harmony Quiz:** Swipe-based onboarding where each user selects budget ceilings, pacing preferences, and activity tags. |
| ![Screen 2](docs/screen2.png) | **Synced Master Itinerary:** Map-integrated schedule displaying route lines, transit times, and venue status indicators. |
| ![Screen 3](docs/screen3.png) | **Pivot Engine Overlay:** One-tap alert center allowing users to input delays/weather alerts and preview reshuffled plans. |
| ![Screen 4](docs/screen4.png) | **Automated Ledger Split:** Live expense ledger displaying group balances tied directly to itinerary nodes. |

---

## 4. What Makes It Different

| Feature | Our Solution | Wanderlog / TripIt | Splitwise |
| :--- | :--- | :--- | :--- |
| **Dynamic Re-planning** | **Instant One-Tap Pivot** (Auto-reschedules around live delays) | Static (Manual deletion & search needed) | N/A |
| **Group Alignment** | **Vector Match Quiz** (Calculates multi-user interest overlap) | Text notes / Manual voting | N/A |
| **Ledger Integration** | **Native & Linked** (Expenses map to daily schedule stops) | External link / Manual entry | Standalone ledger |

* **Dynamic Pivot Engine:** Instead of forcing manual edits during disruptions, the system recalculates route order, filters out closed venues, and keeps travel times realistic.
* **Group Harmony Quantifier:** Converts subjective group preferences into quantitative weighted vectors, auto-generating itineraries that minimize personal compromises.

---

## 5. Technical Architecture & Feasibility

### Tech Stack

* **Frontend (Next.js / Tailwind CSS):** Chosen for rapid server-side rendering, crisp mobile responsiveness, and seamless Vercel deployment. *Constraint: Must optimize client-side bundle size for low-bandwidth mobile connections.*
* **Backend & Realtime Database (Supabase / PostgreSQL):** Provides instant WebSocket sync for group collaboration and flexible JSON schemas for itinerary arrays. *Constraint: Row Level Security (RLS) policies must be carefully tuned for shared trip access.*
* **AI Orchestration Engine (OpenAI GPT-4o API):** Generates structured JSON outputs for travel routing and dynamic re-planning scripts. *Constraint: Requires fallback prompts to avoid hallucinated venue operational hours.*
* **Location & Travel Feeds (Google Places API & Amadeus API):** Delivers live distance calculations, opening hours, and real-time flight status data. *Constraint: API rate limits require client-side caching of map nodes.*
* **Hosting (Vercel):** Free tier hosting with global CDN distribution and seamless git integration.

### System Architecture Diagram

![System Architecture](docs/architecture.png)
*Figure 5.1: High-level data architecture showing real-time client sync via Supabase WebSockets and background AI plan recalculation via serverless functions.*

### Build Plan & Scope (3-Week Hackathon MVP)

* **Week 1 (Data & Sync Core):** Set up Supabase DB schemas, implement multi-user trip joining logic, and construct the Group Harmony quiz interface.
* **Week 2 (Routing & AI Integration):** Wire Google Places API to OpenAI structured output to generate map-clustered daily schedules.
* **Week 3 (Pivot Engine & Ledger Polish):** Finalize the one-tap delay/weather re-plan engine, link shared expense splitting to itinerary nodes, and perform end-to-end user testing.
