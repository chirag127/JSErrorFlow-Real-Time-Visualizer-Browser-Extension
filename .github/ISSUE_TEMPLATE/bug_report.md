---
name: 🐛 Bug Report
about: Report unexpected behavior or defects in JSErrorFlow.
title: "[BUG]: Brief Summary of the Issue"
labels: bug, triage
assignees: ""
---

## 🚨 Summary & Intent Alignment

Please provide a concise, one-sentence summary of the defect. Ensure the reported behavior deviates from the documented specification.

> **Example:** "The extension fails to highlight errors originating from Web Workers on Chromium 119."

---

## ⚙️ Environment & Context (Mandatory)

This section ensures rapid triangulation of the failure domain. **Do not omit details.**

### A. Platform Details
- **Operating System:** [e.g., macOS Sonoma 14.2, Windows 11 Pro]
- **Browser:** [e.g., Chrome 119.0.6045.199, Firefox 120.0.1]
- **Extension Version:** `JSErrorFlow vX.Y.Z` (Check `manifest.json` or extension details)

### B. Target Application Context
- **URL / Domain:** (Use placeholders for sensitive sites)
- **Website Framework:** [e.g., React 18, Vue 3, Vanilla JS]

---

## 👣 Steps to Reproduce (The Critical Path)

Provide a numbered, deterministic sequence that reliably triggers the issue. If the error is intermittent, describe the specific load conditions or timing required.

1. Open Browser to `[Target URL]`
2. Ensure JSErrorFlow is actively injected.
3. Execute the triggering action (e.g., "Click the Submit button").
4. Observe the resulting error visualization or lack thereof.

---

## 🎯 Expected Behavior (The Specification)

What result aligns with the project's design goals (i.e., what *should* have happened)?

*   [ ] The JavaScript error stack trace should appear in the extension popup within 500ms.
*   [ ] The affected DOM node should receive a persistent, pulsating visual indicator as defined by the current UI theme.

---

## 💥 Actual Behavior (The Defect)

What actually occurred that constitutes the bug?

*   [ ] The error was logged in the browser console but **not** visualized by JSErrorFlow.
*   [ ] The visualization caused an unexpected side effect (e.g., UI component displacement or layout shift).

---

## 🖼️ Evidence & Logs

High-quality evidence accelerates triage by 75%.

### A. Visual Proof
(Attach screenshots or screen recordings demonstrating the discrepancy.)

### B. Console Output
Paste the full, relevant output from the browser's Developer Tools Console. Filter by JSErrorFlow sources if possible.

```javascript
// Paste logs here, including stack traces
```

---

## ⚖️ Impact Assessment (Severity)

How severely does this defect impede core functionality?

- [ ] **P0 - Critical:** Core visualization functionality completely blocked. High developer downtime incurred.
- [ ] **P1 - High:** Major error handling path broken; workaround requires disabling the extension.
- [ ] **P2 - Medium:** Minor functionality impaired; aesthetic inconsistency or edge-case handling failure.
- [ ] **P3 - Low:** Typo, documentation error, or non-critical performance degradation.

---

## 🤖 AI Agent Directives for Resolution

**Agent Focus:** Verify against the LATEST TypeScript Strictness settings. Ensure the Content Script's message passing to the Background Service Worker uses the high-reliability `chrome.runtime.sendMessage` pattern (asynchronous). Check Event Listener Cleanup in `cleanupOnDomDetach` to prevent memory leaks.

**Target Fix Location:** `src/content-script.ts` and related DOM manipulation handlers.
