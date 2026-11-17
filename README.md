# The Herd Helpdesk

An interactive, responsive prototype based on the uploaded requirements traceability matrix. Open dist/index.html or serve dist with any static web server. All student information should be fictional.

## Workflows

- Student: see staffing and estimated waits; check in; track an automatically refreshed queue; receive in-app alerts and optional browser notifications; look up cases using a case number and student ID.
- Advisor: select an account, see department requests grouped by issue category and sorted by urgency plus time waited, inspect intake details, call a student, and complete a session with notes, pending actions, and a unique case number. Transfers create a new queue ticket.
- Supervisor: see live local queue and staffing counts, reassign advisors, record staffing requests, and inspect a sample day/hour heatmap.
- Administration: edit operating hours and manual availability, create/edit/deactivate simulated staff accounts, configure category routing, and simulate outage alerts.
- Analytics: filter illustrative historical data by period and department; download CSV and a valid PDF summary.

## Requirements and limitations

F1/R1–R4, F2/R6, F3/R5, F4/R7–R10, F5/R11–R13, F6/R14–R17, F7/R18–R22, and F8/R23–R26 have mapped prototype experiences. R20 is demonstrated through UI role restrictions; it is not a security boundary. This is not a production implementation of all 26 requirements.

Data is stored in localStorage on one browser. Cross-tab changes synchronize through storage events; queue calculations refresh every 10 seconds. There is no server database, WebSocket connection, external SMS delivery, authenticated university staff access, or actual uptime telemetry. Browser notifications require permission and the app to remain open. Posted hours are informational; accepting check-ins is an explicit manual control. Heatmaps and historical reporting use sample fixtures. Live prototype: https://herd-helpdesk-hub.cherishedcarnation3.chatgpt.site

Before production use, implement durable shared records, server-side per-role authorization, university identity integration, case ownership verification, real push/SMS integration, staff capacity/session accounting, schedule-aware availability, and monitoring fed by live service telemetry.

## Validation

JavaScript syntax and workflow checks passed: rendering all role screens, check-in, calling, session completion, case lookup matching, inactive advisor UI restrictions, hours propagation, downloads, and persistence. The managed preview relay failed to open its browser port, so browser visual QA was unavailable.

## Run locally

Run `python3 -m http.server 8000 --directory dist`, then open http://localhost:8000. No build step is required.

GitHub stores this source snapshot; pushes do not automatically update the Sites deployment.
