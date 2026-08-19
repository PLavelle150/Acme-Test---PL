# Acme Robotics — Queue Status & Duplicate-Command Guard Prototype

**Status:** Sandbox prototype — do not merge without human review  
**Related PRD:** PRD Draft — Queue visibility and safe-mode command handling  
**Assigned Agent:** Claude Prototype Builder

---

## What this prototype demonstrates

1. **Command queue state visibility** — Operators see real-time status for every submitted route command: `Queued → Processing → Confirmed / Failed`
2. **Duplicate-command guard** — Submissions from the same operator + robot combination within a 10-second window are blocked with a clear user message
3. **Conflict detection** — If another operator has an active command for the same robot, the new submission is flagged before execution
4. **Supervisor priority routing** — Supervisors can approve conflict overrides; the decision is logged
5. **Audit trail** — Every state transition is recorded with actor, timestamp, and reason

## Running the prototype

Open `prototype/index.html` directly in a browser. No build step, no server required.

## File structure

```
prototype/
  index.html     Self-contained sandbox demo (HTML + CSS + JS)
README.md        This file
```

## Reviewer notes

- All state is in-memory and resets on page reload — no backend, no persistence
- The 10-second duplicate window is configurable via the Config panel in the prototype UI
- "Supervisor" mode is toggled by selecting Sarah Chen in the operator list — demo only
- Do not merge this PR without a human reviewer sign-off on the acceptance criteria

## Acceptance criteria (from task)

- [ ] A reviewer can see Queued / Processing / Confirmed / Failed states
- [ ] Duplicate submissions show a clear message
- [ ] Implementation includes notes for conflict detection and supervisor priority routing
- [ ] No automatic merge — human review required before any production use
