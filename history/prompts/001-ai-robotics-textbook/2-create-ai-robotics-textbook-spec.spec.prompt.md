---
id: 2
title: create-ai-robotics-textbook-spec
stage: spec
date: 2025-12-08
surface: agent
model: Claude Sonnet 4.5
feature: 001-ai-robotics-textbook
branch: 001-ai-robotics-textbook
user: claude-code
command: /sp.specify
labels: [specification, textbook, ai, robotics]
links:
  spec: specs/001-ai-robotics-textbook/spec.md
  ticket: null
  adr: null
  pr: null
files:
 - specs/001-ai-robotics-textbook/spec.md
 - specs/001-ai-robotics-textbook/checklists/requirements.md
tests:
 - none
---

## Prompt

```
text
# Feature Specification — Physical AI & Humanoid Robotics Textbook
Feature Branch: 001-ai-robotics-textbook
Status: Stable (Aligned With Constitution)

---

## 1. Purpose & Scope

### 1.1 Definition
This specification defines all artifacts, checks, folder structures, automation rules, and deliverables needed to generate the **Docusaurus-based Physical AI & Humanoid Robotics textbook**, strictly following the project constitution.

### 1.2 Scope (Important)
This project ONLY includes:
- Textbook content creation
- Diagrams
- Example code
- Documentation
- CI scripts
- Deployment setup

This project does **NOT** include:
- Hardware installation
- Robot drivers
- Operating robots
- Chatbot or VLA agent development
- ROS/Isaac execution environments

(Execution restriction added for safety.)

### 1.3 Target Audience
- Primary: AI/ML students
- Secondary: Robotics beginners
- Tertiary: Hackathon learners

### 1.4 Deliverables
- Docusaurus textbook
- Public GitHub repository

---

## 2. Success Criteria (Measurable)

### 2.1 Content Requirements
Word count must satisfy:

| Module | Range |
|--------|---------|
| Module 1 | 4000–5000 |
| Module 2 | 3500–4500 |
| Module 3 | 4000–5000 |
| Module 4 | 3500–4500 |
| **Total** | **15000–20000** |

### 2.2 Code Examples
- 20 runnable examples (5 per module)
- Must include:
  - environment.yaml
  - requirements.txt or pyproject.toml
  - test.sh (Ubuntu 22.04 headless run)

### 2.3 Code Quality
- English comments
- Required: Type hints
- Required: Basic error handling

### 2.4 GPU Tagging
- GPU-required examples must include:

```yaml
gpu: true
```

in `examples/meta.yaml`.

---

## 3. Project Structure Requirements

### 3.1 Folder Structure (Final)
```
docs/
  module-1/
  module-2/
  module-3/
  module-4/
diagrams/
  module-1/
  module-2/
  module-3/
  module-4/
code/
  module-1/
  module-2/
  module-3/
  module-4/
examples/
scripts/
static/img/
specs/
templates/
```

### 3.2 Diagrams
- Store in `diagrams/module-x/`
- Formats:
  - Preferred: SVG
  - Fallback: PNG
- Each diagram must include:
  - Alt text (markdown)
  - Caption in `diagrams/meta.yaml`
- Accessibility: WCAG 2.1 AA

---

## 4. Deployment & Release

### 4.1 Build
```
npm run build
```
Output → `/build`

### 4.2 Deployment Platform (Mandatory)
Deployment MUST be done on **Vercel only**.
Claude Code MUST prepare Vercel-compatible build output and deployment instructions exclusively.


### 4.3 Pre-Release Verification
Before releasing:
1. `verify.sh`
2. Link checker
3. Accessibility audit
4. Word count check
5. Diagram count check

---

## 5. Deliverable Checklist (PR Requirement)

### 5.1 Content Deliverables
- [ ] docs/ (all 4 modules, frontmatter included)
- [ ] diagrams/ (12 diagrams + alt text)
- [ ] code/ (20 runnable examples)

### 5.2 Infrastructure Deliverables
- [ ] scripts/verify.sh
- [ ] scripts/check-wordcount.py
- [ ] scripts/link-check.sh

### 5.3 Documentation Deliverables
- [ ] README with:
  - Setup instructions
  - How to run examples
  - Environment variables
  - Known issues
  - WhatsApp contact
- [ ] demo-video.mp4 (≤90 seconds)

### 5.4 Automation Logs
- [ ] specs/auto-created.log (if auto-fill used)

---

## 6. Scoring & Bonuses

### Base Score (100 Points)
- 100% textbook content

### Bonus Features (+50 each)
- Claude Subagents
- Better-auth + profiling
- Personalization engine
- Urdu translation toggle

---

## 7. Exclusions (Strict)

The system MUST NOT:
- Build, install, or configure physical robots
- Run ROS / Gazebo / Isaac simulations
- Provide hardware setup scripts
- Implement chatbot / VLA agents
- Require cloud GPU usage without approval

(Added to avoid unintended execution by Claude Code.)

---

## 8. Notes & Recommendations

### 8.1 Templates
Provide:
- `templates/frontmatter.md`
- `docs/examples/frontmatter.md`

### 8.2 Validation Scripts
Required:
- `scripts/check-wordcount.py`
- `scripts/link-check.sh`

### 8.3 Testing Environment
- Dockerfile for Ubuntu 22.04
- Ensures examples run in a clean reproducible environment

---

## 9. Execution Restrictions (NEW – Added for Safety)
Claude Code MUST:
1. Only execute tasks related to textbook generation.
2. Never auto-start:
   - chatbot systems
   - hardware automation
   - ROS/Isaac execution
3. Only use this spec for:
   - file generation
   - content creation
   - documentation
   - CI tooling

---
```

## Response snapshot

Created the feature specification for the Physical AI & Humanoid Robotics Textbook project. The specification includes:

1. Three prioritized user stories covering textbook access, example code execution, and diagram viewing
2. Ten functional requirements covering content, examples, deployment, and accessibility
3. Four key entities related to textbook modules, examples, diagrams, and validation
4. Six measurable success criteria with specific metrics

The specification adheres to the project constitution by focusing on textbook content creation while excluding hardware installation, robot operation, and chatbot development.

## Outcome

- ✅ Impact: Created comprehensive feature specification aligned with project constitution
- 🧪 Tests: none
- 📁 Files: Created specs/001-ai-robotics-textbook/spec.md and specs/001-ai-robotics-textbook/checklists/requirements.md
- 🔁 Next prompts: Plan implementation using /sp.plan
- 🧠 Reflection: The specification successfully translates the feature requirements into testable user scenarios and measurable outcomes while maintaining focus on textbook content creation.

## Evaluation notes (flywheel)

- Failure modes observed: none
- Graders run and results (PASS/FAIL): N/A
- Prompt variant (if applicable): N/A
- Next experiment (smallest change to try): Create implementation plan based on this specification