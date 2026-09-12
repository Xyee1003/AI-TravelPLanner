# Pocket Trip by The Last 4

**Team:** Kam Pue Shan, Faustina Lai Wan Yee, Tan Wen Jie, Tang Xin Yee  
**Problem Statement:** Lifestyle Track: Planning an Escape (Travel Planner)  
**Video Presentation:** [Unlisted Youtube Link]  
**Presentation Slides:** [Public Link]  

---

## 1. Project Overview

### The Problem
Group travel planning is notoriously friction-filled, often devolving into endless group chat debates, budget misunderstandings, and logistics headaches. The root causes of this breakdown include:

1. **Social Friction & Decision Paralysis**: Group members possess contrasting budgets, physical stamina levels, and activity preferences. When preferences clash, traditional voting mechanics force a "winner vs. loser" dynamic, causing social discomfort or awkward compromises.
2. **Asynchronous Onboarding Drag**: Travel groups usually contain a mix of proactive planners and passive ("go-with-the-flow") participants. Tools that require *every* member to complete upfront preference forms stall immediately because passive users delay or refuse to fill them out.
3. **Data Entry Fatigue & Information Scattering**: Information is fragmented across Instagram reels, Xiaohongshu posts, TikTok videos, flight confirmation PDFs, and chat screenshots. Manually copy-pasting names, addresses, opening hours, and costs into static spreadsheets creates heavy friction.
4. **Fragile, Static Itineraries**: Traditional travel apps create fixed daily timelines. When unexpected delays occur—such as a flight lag, sudden rainstorm, or prolonged queue—the entire schedule breaks down, forcing manual re-planning on the go.

#### Stakeholders
* **The Designated Trip Leader**: Takes on the burden of organizing, budgeting, and managing schedules while trying to keep everyone happy.
* **Passive / Casual Group Members**: Want a fun trip without spending hours filling out surveys or managing logistics.
* **Budget-Conscious Travelers**: Need strict, transparent cost tracking to avoid awkward post-trip expense disputes.
* **Families & Parents**: Require location updates and peace of mind without invasively tracking young adult travelers 24/7.

#### Existing Market Solutions & Their Shortcomings
* **Wanderlog**: Offers comprehensive itinerary building but relies heavily on text-heavy manual searches, link pasting, and manual drag-and-drop scheduling. It functions as a digital notebook rather than an active assistant and lacks non-confrontational conflict resolution tools.
* **TripIt**: Excellent for consolidating flight and hotel confirmation emails, but fails completely at group collaboration, social media inspiration ingestion, real-time in-trip adaptation, and dynamic budget mediation.

---

### Our Solution
**Pocket Trip AI** is an AI-native group travel platform that transforms travel planning from a tedious logistical task into a fluid, adaptive experience. Instead of forcing rigid questionnaires or enforcing hard majority votes, Pocket Trip AI leverages passive AI profiling, multimodal visual parsing, and continuous budget monitoring to orchestrate trips effortlessly. When group preferences diverge, the app's AI engine automatically generates non-confrontational, parallel micro-routes with automated reunion anchors, allowing members to explore independently for short intervals before seamlessly regrouping.

#### Key Feature Set
* **AI Vision Social Inspo Parser**: Allows users to bulk-upload screenshots from Xiaohongshu, Instagram, or TikTok. OpenAI GPT-4o Vision automatically extracts attraction names, category tags, opening hours, and estimated per-person costs.
* **Asynchronous Google Calendar Flight Sync**: Auto-detects arrival/departure windows via Google Calendar OAuth, automatically locking out unavailable time slots and building buffer periods around arrivals.
* **AI Harmony Hub & Subgroup Micro-Loops**: Eliminates harsh rejection buttons. When preferences split, AI generates temporary 45-minute parallel routes within 300 meters of each other and designates an automated reunion anchor (e.g., a nearby dessert café).
* **Transparent AI Rationale Engine**: Displays explicit "Why AI Suggested This" contextual tags (factoring in peak heat hours, travel distance, and group vibe) for full transparency.
* **Live Budget Bar & Dynamic AI Budget Trim**: Real-time spending tracker displaying per-pax financial health. If an item causes budget overruns, the AI proactively suggests one-tap cost-lowering alternatives.
* **Real-Time Disruption Management Agent**: Allows travelers to report delays or bad weather mid-trip. The AI instantly reorganizes remaining daily stops to protect mandatory highlights.
* **Privacy-Preserving Parent View**: Generates warm, AI-summarized trip updates and high-level progress digests for parents without exposing raw, intrusive real-time GPS coordinates.

---
## 2. Ideation & Process

### 2.1 Ideas We Considered

| Idea | Status | Why it was kept / dropped |
| :--- | :--- | :--- |
| **AI Subgroup Micro-Loops & Auto-Reunion Anchors** | **Chosen** | **Kept**: Replaced harsh "Hard-No" splits with seamless 45-minute parallel pathways, resolving group preference conflicts without social friction or team isolation. |
| **Social Media Screenshot Parsing (AI Vision)** | **Chosen** | **Kept**: Eliminates manual text entry by extracting location names, category tags, and price estimates directly from uploaded social media images using GPT-4o Vision. |
| **Dynamic Live Budget Bar & Proactive AI Trim** | **Chosen** | **Kept**: Maintains financial transparency in real time without requiring tedious upfront surveys that stall initial trip creation. |
| **Leader-Only Edit Authority with Group Micro-Votes** | **Chosen** | **Kept**: Prevents itinerary clutter and consensus deadlock by letting AI assist and members vote on lightweight cards, while the Leader retains sole final editing rights. |
| **Passive AI Profiling (Default "Follower" Mode)** | **Chosen** | **Kept**: Resolves asynchronous onboarding bottlenecks by letting inactive users default to a "chill traveler" persona based on destination averages until they express active preferences. |
| **In-App Shared Photo Album** | **Dropped** | **Dropped**: Removed following mentor feedback to keep the app lightweight and strictly focused on dynamic coordination, scheduling, and budget optimization. |
| **Mandatory Upfront Group Preference Questionnaire** | **Dropped** | **Dropped**: Rejected because forcing passive group members to fill out forms before generating a trip draft created high onboarding friction and stalled group progress. |
| **Hard-No Voting & Rigid Split Confirmation Modals** | **Dropped** | **Dropped**: Initial prototype used hard rejection buttons and binary split confirmation modals, which created social awkwardness and rigid logic branches. Replaced by soft AI arbitration. |

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

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th>Mentor</th>
      <th>Feedback Received</th>
      <th>What Was Changed / Team Rationale</th>
    </tr>
  </thead>
  <tbody>
    <!-- Session 1: Zach Khong -->
    <tr>
      <td rowspan="5"><b>07/09/2026</b></td>
      <td rowspan="5">Zach Khong</td>
      <td><b>1. Feature Scope</b><br>Remove the Photo Album feature to keep focus sharp.</td>
      <td><b>Agreed & Implemented</b><br>Removed Photo Album module entirely.</td>
    </tr>
    <tr>
      <td><b>2. Flight Sync</b><br>Sync flight schedules via Google Calendar integration.</td>
      <td><b>Agreed & Implemented</b><br>Integrated Google Calendar OAuth for flight availability.</td>
    </tr>
    <tr>
      <td><b>3. Governance</b><br>Assign sole editing authority to a designated Trip Leader.</td>
      <td><b>Agreed & Implemented</b><br>Restructured permissions to Leader-only edit model.</td>
    </tr>
    <tr>
      <td><b>4. Onboarding Friction</b><br>Solve flow blockages caused by unresponsive group members.</td>
      <td><b>Agreed & Implemented</b><br>Implemented AI auto-completion defaults for inactive users.</td>
    </tr>
    <tr>
      <td><b>5. Conflict Resolution</b><br>Provide split pathways or compromise spots for conflicting preferences.</td>
      <td><b>Agreed & Implemented</b><br>Replaced hard splits with 45-minute parallel subgroup loops and automated reunion points.</td>
    </tr>
    <!-- Session 2: Mah Qing Fung -->
    <tr>
      <td rowspan="4"><b>11/09/2026</b></td>
      <td rowspan="4">Mah Qing Fung</td>
      <td><b>1. AI Integration Depth</b><br>Increase AI touchpoints across all key screens.</td>
      <td><b>Agreed & Implemented</b><br>Added AI Vision parsing, proactive AI budget guardrails, and AI disruption agents.</td>
    </tr>
    <tr>
      <td><b>2. Logic Refinement</b><br>Remove hard-coded "Hard-No" mechanics; let AI mediate decisions dynamically.</td>
      <td><b>Agreed & Implemented</b><br>Replaced Hard-No modals with soft AI Harmony arbitration.</td>
    </tr>
    <tr>
      <td><b>3. User Onboarding</b><br>Force users to complete preference and budget forms upfront.</td>
      <td><b>Disagreed & Omitted Upfront Forms</b><br>Opted for passive AI profiling and dynamic screenshot budget parsing instead to prevent onboarding bottlenecks.</td>
    </tr>
    <tr>
      <td><b>4. AI Transparency</b><br>Add explicit AI explanations for schedule choices and pre-swap recommendations.</td>
      <td><b>Agreed & Implemented</b><br>Added "Why AI suggested this" rationale tags and AI Smart Swap modals.</td>
    </tr>
  </tbody>
</table>

## 3. Design & Prototype

**UI Prototype:** [https://www.figma.com/design/Vd08aJCY0ix9kyV9NJg8pR/UI-Prototype-Pocket-Trip?node-id=2009-632&t=7SCQYwLwL8Ws1qtk-1]

### Key Screen Breakdowns

![Homepage & Trip Setup](docs/assets/1.png)

*Figure 3.1: Homepage & Trip Setup (`Create_Step1` & `Create_Step2`) — The Leader initializes the trip, syncs flight schedules via Google Calendar, and selects overarching "Trip Vibes" (e.g., Chill & Cafe, Food Hunt). Passive group members can join instantly without filling out tedious questionnaires.*

---

![Social Media Image Recognition Parsing](docs/assets/2.png)

*Figure 3.2: Multimodal Social Inspo Parsing (`Image Recognition 1 & 2`) — Group members drop screenshots from Instagram, TikTok, or Xiaohongshu. GPT-4o Vision processes the images, extracts venue names, categorizes spots (Must-See vs. Nice-to-Have), and calculates estimated costs.*

---

![Master Itinerary & AI Rationale](docs/assets/3.png)

*Figure 3.3: Master Itinerary & AI Rationale (`Itinerary 2nd Draft` & `Activity Desc`) — Displays the optimized itinerary timeline. Tapping any attraction reveals a modal with an explicit "Why AI Suggested This" section detailing timing, heat avoidance, and budget optimization rationale.*

---

![Subgroup Micro-Loops & Parallel Routing](docs/assets/4.png)

*Figure 3.4: Subgroup Micro-Loops (`Subgroup Itinerary`) — When member preferences diverge, the AI generates a 45-minute parallel split route. Subgroup A (Art Cafe) and Subgroup B (Historic Fort) explore nearby venues independently before automatically reuniting at a designated meeting point.*

---

![Proactive AI Budget Trim & In-App Chat](docs/assets/5.png)

*Figure 3.5: AI Budget Trim & Contextual Chat (`Trim Budget` & `Chat`) — Real-time budget monitoring tracks per-pax spending. If an item exceeds limits, the AI presents a one-tap budget-lowering alternative. The embedded chat features interactive AI voting cards to keep discussions in-app.*

---

![Live Disruption Agent & Parent View](docs/assets/6.png)

*Figure 3.6: Live Execution, Disruption Agent & Parent View (`Start Trip View`) — Mid-trip delays or bad weather trigger the AI Disruption Agent to instantly recalculate remaining stops. Meanwhile, Parent View generates high-level progress digests without invading user privacy.*

---

## 4. What Makes It Different

### Feature Comparison Matrix

| Feature Dimension | Pocket Trip AI | Wanderlog | TripIt |
| :--- | :--- | :--- | :--- |
| **Inspiration Ingestion** | **Multimodal AI Vision**: Parses screenshots from Xiaohongshu, IG, and TikTok directly into pricing and location nodes | **Manual Search / Paste**: Requires typing place names or manually copying web URLs | **Email Forwarding**: Limited to confirmation emails for flights/hotels |
| **Conflict Mediation** | **AI Subgroup Micro-Loops**: 45-min non-confrontational split paths with auto reunion anchors | **Manual Negotiation**: Group must argue out disagreements externally in third-party chats | **None**: Displays a rigid single-timeline schedule |
| **Budget Management** | **Live AI Budget Bar**: Dynamic per-pax tracking with instant AI cost-trimming proposals | **Manual Expense Log**: Basic post-spending expense tracking | **Basic Cost Sum**: Summarizes booking costs from confirmation emails |
| **In-Trip Adaptability** | **Proactive Disruption Agent**: Automatically reschedules remaining stops during rain or delays | **Manual Drag-and-Drop**: User must manually re-order items when plans fall through | **Flight Status Alerts Only**: Sends delay alerts without adjusting daily itineraries |
| **User Onboarding** | **Passive AI Profiling**: Starts immediately; handles inactive members via sensible defaults | **High Friction**: Requires all members to join and manually input preferences | **Individual Setup**: Designed for solo travelers or static sharing |
| **Group Governance** | **Leader Authority + AI Micro-Votes**: Balanced governance prevents itinerary clutter | **Unrestricted Editing**: Multiple users can edit simultaneously, causing accidental overrides | **Read-Only / Full Edit**: Lacks granular voting or AI-assisted moderation |

---

## 5. Technical Architecture & Feasibility

### Tech Stack

| Layer | Technology | Selection Rationale | Expected Constraints & Mitigation |
| :--- | :--- | :--- | :--- |
| **Frontend** | **React Native (Expo)** | Cross-platform (iOS/Android) compatibility, rapid UI prototyping, and smooth native map rendering capabilities. | High memory consumption during batch image uploads; mitigated by client-side image compression before API transmission. |
| **Backend API** | **Node.js / Express** | Asynchronous, non-blocking I/O ideal for real-time chat, concurrent voting cards, and API orchestration. | Single-threaded bottlenecks; compute-heavy AI processing is offloaded to asynchronous background jobs. |
| **Database** | **Supabase (PostgreSQL)** | Relational data integrity for complex trip hierarchies, combined with built-in WebSockets for real-time collaboration. | Connection limit thresholds on free tier; mitigated using Supabase connection pooling (PgBouncer). |
| **AI Services** | **OpenAI GPT-4o Vision API** | State-of-the-art multimodal capability to parse unstructured travel screenshots, execute OCR, and infer costs. | API latency (2–4s) and token costs; mitigated by caching venue metadata and stripping non-essential visual tokens. |
| **External APIs** | **Google Maps & Calendar APIs** | Industry standard for place details, distance/duration matrix calculations, and OAuth calendar schedule sync. | Strict API rate limits and usage costs; mitigated by aggressively caching geocoding results in PostgreSQL. |
| **Hosting** | **Vercel / Render** | Instant CI/CD deployments with serverless architecture and preview environments for fast feedback loops. | Serverless cold starts; mitigated by keeping core backend endpoints warm via ping health-checks. |

---

### System Architecture Diagram

```mermaid
graph TD
    classDef client fill:#e1f5fe,stroke:#0288d1,stroke-width:2px;
    classDef server fill:#fff3e0,stroke:#f57c00,stroke-width:2px;
    classDef db fill:#e8f5e9,stroke:#388e3c,stroke-width:2px;
    classDef ai fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px;

    subgraph Client ["1. Frontend Layer (React Native / Expo)"]
        UI_Upload["Image Upload Sync (Vision UI)"]:::client
        UI_Cards["Interactive Voting Cards"]:::client
        UI_Map["Map Canvas & Live Itinerary"]:::client
    end

    subgraph Server ["2. Backend Services (Node.js / Express Engine)"]
        API_Vision["AI Vision Parsing Pipeline"]:::server
        API_Harmony["AI Harmony Subgroup Router"]:::server
        API_Budget["Live Budget & Trim Engine"]:::server
    end

    subgraph External ["3. Cloud Infrastructure & External APIs"]
        Ext_OpenAI["OpenAI GPT-4o Vision API"]:::ai
        Ext_GoogleMaps["Google Maps / Places API"]:::ai
        Ext_GoogleCal["Google Calendar OAuth API"]:::ai
        DB_Supa[("Supabase (PostgreSQL & WebSockets)")]:::db
    end

    UI_Upload -->|Screenshot Data| API_Vision
    UI_Cards -->|Vote / Preference Event| API_Harmony
    UI_Map -->|Cost & Expense Track| API_Budget

    API_Vision -->|OCR & Extraction| Ext_OpenAI
    API_Harmony -->|Routing & Meeting Points| Ext_GoogleMaps
    UI_Upload -.->|Flight Sync| Ext_GoogleCal

    API_Vision <--> DB_Supa
    API_Harmony <--> DB_Supa
    API_Budget <--> DB_Supa
```

### Build Plan & Scope (3-Week Hackathon MVP)

#### Week 1: Core Architecture & Data Integration
* Set up React Native (Expo) shell, navigation stacks, and Figma-aligned UI design tokens.
* Configure Supabase PostgreSQL schema with Leader-only edit permissions and WebSocket subscription channels.
* Implement Google Calendar OAuth integration to pull user flight schedules and automatically flag availability windows.

#### Week 2: AI Vision & Itinerary Generation Engine
* Build backend integration with OpenAI GPT-4o Vision API for multi-image screenshot processing and venue extraction.
* Develop the **AI Harmony Router** algorithm to generate master timelines and identify preference divergence points.
* Implement the **Subgroup Micro-Loop** logic: auto-generating 45-minute parallel branches and identifying nearest coffee/dessert reunion anchors via Google Places API.

#### Week 3: Dynamic Budgeting & In-App Collaboration
* Build the frontend **Live Budget Bar** component with per-pax dynamic calculation hooks.
* Develop the **Proactive AI Budget Trim** engine to generate automated cost-cutting swap proposals.
* Implement in-app chat with embedded interactive voting cards (allowing members to approve/reject nodes directly in-chat).

#### Week 4: Live Execution Agent, Safety & Testing
* Build the **Report Disruption** workflow to recalculate remaining stops in response to delays or weather events.
* Implement the **Parent View** digest generator to output high-level AI status reports.
* Conduct end-to-end integration testing, API error handling, and performance optimization prior to submission.
