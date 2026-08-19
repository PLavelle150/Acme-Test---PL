# Acme-Test---PL

Acme Robotics MVP Build — prototype sandbox repository.

---

## Prototypes

### 1. Queue Status Indicator & Duplicate-Command Guard
**Path:** `prototype/index.html`
**PRD:** Queue visibility and safe-mode command handling
**PR:** [#1](https://github.com/PLavelle150/Acme-Test---PL/pull/1)
**Status:** Done

Demonstrates: Queued → Processing → Confirmed / Failed state machine, duplicate-command guard (same operator+robot within configurable window), conflict detection with supervisor override, and audit trail.

---

### 2. FleetOps Command Lifecycle & Latency Guardrails
**Path:** `prototypes/fleetops-lifecycle/index.html`
**PRD:** FleetOps renewal & expansion blocked by command latency
**PR:** [#2](https://github.com/PLavelle150/Acme-Test---PL/pull/2)
**Status:** Done

Demonstrates the full five-state command lifecycle (Received → Queued → Dispatched → Executing → Completed/Failed), live time-in-queue counters, latency warning banners, queue timeout with operator next-steps and retry, peak load simulation, duplicate guard, conflict detection, failure states with next steps, and structured telemetry/audit log with raw JSON toggle.

---

### 3. Multi-Site Fleet Visibility Dashboard
**Path:** `prototypes/multisite-fleet-dashboard/index.html`
**PRD:** Multi-site fleet visibility and incident detection
**Status:** Needs Review

Demonstrates a unified multi-site fleet dashboard for enterprise operators managing multiple sites (Pacific Warehousing — Seattle/Oakland/LA; Meridian Logistics — Phoenix/Atlanta/Dallas):

- **Cross-site KPI rollups** — fleet availability %, active incidents, at-risk sites, and total robots monitored in a top bar
- **Incident banners** — site-wide alert when one or more sites have active incidents
- **Site cards** with colour-coded status (Incident/At Risk/Healthy/Offline), per-site availability, active robot count, and incident count
- **Filter bar** — filter by status (All/Incident/At Risk/Healthy/Offline) and free-text search
- **Drill-down drawer** — click any site to view individual robot statuses, incident log with severity, site KPIs, and coverage notes
- **CSV report export** — one-click export of full site + robot data as a dated CSV file (eliminates manual reporting)
- **Permissions model** — role selector switches between Admin (all 6 sites), Pacific Operator (3 sites), and Meridian Operator (3 sites)

#### Acceptance criteria checklist
- [ ] All sites visible in one dashboard with fleet status and health indicators
- [ ] Cross-site KPI rollups (fleet availability %, active incidents, at-risk sites) shown at top
- [ ] Filter by status and site search works correctly
- [ ] Incident and at-risk sites are clearly surfaced with banners and colour-coded cards
- [ ] Drill-down into a site shows fleet detail, robot list, and incident log
- [ ] Export button produces a downloadable CSV shift report
- [ ] Permissions model: Admin sees all 6 sites; Pacific and Meridian operators see only their own sites
- [ ] No auto-merge — reviewer must sign off before Done
