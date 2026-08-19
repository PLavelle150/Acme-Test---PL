# Acme-Test---PL

Acme Robotics MVP Build — prototype sandbox repository.

---

## Prototypes

### 1. Queue Status Indicator & Duplicate-Command Guard
**Path:** `prototype/index.html`  
**PRD:** Queue visibility and safe-mode command handling  
**PR:** [#1](https://github.com/PLavelle150/Acme-Test---PL/pull/1)  
**Status:** Needs Review

Demonstrates: Queued → Processing → Confirmed / Failed state machine, duplicate-command guard (same operator + robot within configurable window), conflict detection with supervisor override, and audit trail.

---

### 2. FleetOps Command Lifecycle & Latency Guardrails
**Path:** `prototypes/fleetops-lifecycle/index.html`  
**PRD:** FleetOps renewal & expansion blocked by command latency  
**Status:** Needs Review

Demonstrates the full **five-state command lifecycle** (Received → Queued → Dispatched → Executing → Completed/Failed), with:

- **Live time-in-queue counter** per command — always visible to operators
- **Latency warning banners** when a command exceeds the configurable warn threshold (default 5 s)
- **Queue timeout** with operator-friendly next-steps and one-click retry (default 15 s)
- **Peak Load simulation** — toggle to reproduce shift-change queue congestion (× 5 queue wait)
- **Duplicate-command guard** — blocks same operator + robot re-submission within the configured window
- **Conflict detection** with supervisor approve / reject override flow
- **Failure states** with specific failure reason and actionable next steps for operators
- **Structured telemetry / audit log** — every state transition logged with timestamps, durations, and metadata suitable for RCA and account-team communication; "show raw" toggle exposes JSON

#### Acceptance criteria checklist
- [ ] Operator sees all five lifecycle states in the UI
- [ ] Latency warning banner appears when time-in-queue exceeds threshold
- [ ] Duplicate submission within guard window shows a clear block message
- [ ] Conflicting commands surface a warning; supervisors can approve or reject override
- [ ] Timed-out commands show next-steps and a Retry button
- [ ] Failed commands show specific reason and recommended next steps
- [ ] Telemetry panel logs every event with structured metadata
- [ ] No auto-merge — reviewer must sign off before Done
