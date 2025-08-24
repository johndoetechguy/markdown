

## 📄 `agents.md`

# 🤖 Project Agents

This document describes **development and workflow agents** to guide contributors and automate tasks.

---

## 🔧 Setup Agent
- Ensures all prerequisites (Node, npm/yarn) are installed.
- Installs dependencies and verifies environment variables.
- Bootstraps local dev server with hot reload.

---

## 🗂️ Project Structure Agent
- Validates file and folder structure.
- Suggests placement of new components (e.g., `src/components/`).
- Maintains separation of concerns (UI, pages, hooks, styles).

---

## 🧩 Routing Agent
- Handles navigation updates in `Routes.jsx`.
- Ensures new pages are registered properly with React Router v6.
- Enforces lazy loading for performance when needed.

---

## 🎨 Styling Agent
- Applies TailwindCSS design standards.
- Recommends responsive utility classes.
- Suggests plugin usage for typography, forms, or animations.

---

## 📊 Data Agent
- Guides integration of charts using D3.js or Recharts.
- Manages state for visualization data via Redux Toolkit.
- Ensures data-fetching hooks follow React best practices.

---

## 🧪 Testing Agent
- Ensures new components include Jest + React Testing Library tests.
- Suggests unit, integration, and snapshot tests.
- Runs test coverage reports before PR merges.

---

## 🚀 Deployment Agent
- Builds optimized production bundles via Vite.
- Verifies environment configs (`.env`).
- Provides CI/CD pipeline steps for deployment.

---

## 🔄 Collaboration Agent
- Enforces Git workflow standards (feature branches, PR reviews).
- Suggests commit message conventions (e.g., Conventional Commits).
- Ensures documentation is updated with every new feature.
