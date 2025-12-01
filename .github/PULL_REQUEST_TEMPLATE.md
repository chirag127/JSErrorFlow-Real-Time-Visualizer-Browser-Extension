# Pull Request Template

**Thank you for contributing to JSErrorFlow!**

This template helps ensure your Pull Request (PR) is clear, concise, and meets our high-quality standards. Please fill out all sections accurately.

--- 

## 1. PR Checklist

Before submitting, please verify that you have:

* [ ] **Self-Implemented Apex Principles:** Your changes adhere to SOLID, DRY, KISS, CQS, and Zero Trust principles.
* [ ] **Zero-Error Code:** All code passes linting (`biome check --apply`) and testing (`vitest`) without errors or warnings.
* [ ] **Comprehensive Tests:** New functionality is covered by unit and/or E2E tests in the `tests/` directory.
* [ ] **Documentation Sync:** `README.md` (especially the AI Agent Directives block) and other relevant documentation are updated to reflect changes.
* [ ] **Conventional Commits:** Your commit messages follow the Conventional Commits specification (e.g., `feat:`, `fix:`, `docs:`).
* [ ] **Security Scrutiny:** All inputs are sanitized, and no new security vulnerabilities have been introduced (refer to OWASP Top 10 2025).
* [ ] **Performance Focus:** Changes aim to improve or maintain performance (e.g., INP optimization, lazy loading).
* [ ] **Branch Strategy:** Your changes are based on the latest `main` branch and have been rebased accordingly.

--- 

## 2. Pull Request Description

### 2.1. Title

*Use Conventional Commits format:* `type(scope): short description`

*Example:* `fix(core): Resolve issue with error highlighting on dynamic content`

### 2.2. Bottom Line Up Front (BLUF)

*Provide a concise 1-2 sentence summary of the problem this PR solves and its impact.*

--- 

### 2.3. Motivation & Context

*Why is this change needed? What problem does it solve?*
*Are there any related issues? Please link them using `#issue-number`.*

--- 

### 2.4. Proposed Solution

*Describe the approach taken to solve the problem.*
*Explain any significant architectural decisions or trade-offs made.*

--- 

### 2.5. Changes Made

*List the key files or modules affected.*
*Highlight any new features, bug fixes, or refactorings.*

--- 

### 2.6. Verification Steps

*How can the reviewer verify these changes?*
*Provide specific steps, including any necessary setup or commands.*

--- 

### 2.7. Screenshots/Recordings (If Applicable)

*For UI changes, please include before/after screenshots or a GIF/video.*

--- 

### 2.8. Related AI Agent Directives (If Applicable)

*If this PR introduces changes that affect the "AI Agent Directives" section in the README, please mention them here and provide a brief explanation.*

--- 

## 3. Reviewer Notes

*Any specific areas you'd like the reviewer to focus on?*
*Potential risks or concerns?*

--- 

**Please remember to Star ⭐ this repository if you find it valuable!**
