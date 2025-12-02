# Pull Request Checklist & Review Directive

<!--

Thank you for contributing to JSErrorFlow! 

Before submitting, please ensure this PR adheres to the Apex Technical Authority standards.

1. **Branch Naming:** Is your branch descriptive (e.g., `feature/new-dom-highlight` or `fix/error-parsing-bug`)?
2. **Self-Review:** Have you reviewed your own changes against the architectural guidelines in AGENTS.md?
3. **Testing:** Have you added/updated necessary unit/E2E tests?
4. **Description:** Is the description clear, concise, and does it reference any related issues (e.g., `Closes #123`)?

-->

## 🚀 Feature / Fix Summary

**Briefly describe the change this PR introduces.** (Why was this change necessary?)

<!-- Example: Implements real-time error visualization for unhandled promise rejections by hooking into the global `unhandledrejection` event. -->


[Describe the core change here]


## Related Issues

Closes/Fixes/Relates to: (e.g., `Closes #42`, `Fixes #10`)

---

## ✅ Checklist

**Developer Confirmation (Check all that apply):**

- [ ] **Code Quality:** Linting passes without warnings (`npm run lint`).
- [ ] **Formatting:** Code formatting is consistent (`npm run format`).
- [ ] **Testing:** Unit tests (`npm run test:unit`) pass successfully for the added scope.
- [ ] **Documentation:** Any new public APIs or significant behavioral changes are documented in the relevant source files or README.
- [ ] **Architecture Alignment:** Changes adhere to the established FSD/WXT patterns outlined in `AGENTS.md`.
- [ ] **Security:** No secrets exposed, and input sanitization has been applied where necessary (especially DOM manipulation).

---

## 🧠 Architecture & Technical Deep Dive

**For non-trivial changes, detail the architectural impact or implementation decisions.**

1. **Component Impact:** Which main FSD layers were affected (e.g., `entities/error-model`, `features/visualizer-display`)?
2. **DOM/Runtime Strategy:** How does this interact with the browser's event loop or MutationObserver (if applicable)?
3. **Performance Considerations:** Are there any new DOM thrashing or excessive re-renders introduced? (Targeting sub-10ms updates).

markdown
[Technical notes here]


---

## 🖼️ Screenshots / Artifacts (If Applicable)

<!-- If this PR affects the UI or observable behavior, include visual proof. -->

| Before | After |
| :---: | :---: | 
| (Optional Screenshot/GIF) | (Optional Screenshot/GIF) |

---

## 🤖 Reviewer Guidance

**Please focus review efforts on the following areas:**

1.  Performance implications of the new visualizer logic.
2.  Correctness of TypeScript type definitions introduced.
3.  Adherence to WXT extension lifecycle management.