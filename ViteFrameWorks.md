# Vite Frameworks — Quick Notes

Vite is a **build tool** that helps us create, run, and build frontend applications. During project scaffolding, it lets us choose a framework or library to build the UI.

## 1. Vanilla JavaScript

**Purpose:** Build websites using plain JavaScript without a frontend framework.

* Uses HTML, CSS, and JavaScript directly.
* Suitable for simple websites, small interactive components, and projects that don't need a large UI framework.
* You manage DOM updates and UI behavior yourself.

**Example:** A calculator, a simple landing page, or a basic to-do list.

## 2. React

**Purpose:** Build interactive, component-based user interfaces.

* Developed by Meta.
* Breaks the UI into reusable components.
* Uses JSX to describe UI and state to manage dynamic data.
* Suitable for dashboards, project management apps, e-commerce sites, and complex web applications.

**Example:** Your Luminar Lectures library, TaskForge, or an ERP dashboard.

## 3. Vue.js

**Purpose:** Build interactive user interfaces with a progressive JavaScript framework.

* Provides a structured way to build reusable components.
* Uses templates, reactive data, and directives such as `v-if` and `v-for`.
* Often approachable for beginners and can be introduced gradually into an existing website.
* Suitable for dashboards, admin panels, and full web applications.

**Example:** An admin panel with dynamic tables, filters, forms, and charts.

## Quick Comparison

| Feature         | Vanilla JS            | React                 | Vue.js                   |
| --------------- | --------------------- | --------------------- | ------------------------ |
| Type            | Plain JavaScript      | UI library            | UI framework             |
| UI structure    | Manual DOM management | Components + JSX      | Components + templates   |
| Reusability     | Manually organized    | High                  | High                     |
| Best suited for | Small interactions    | Flexible, complex UIs | Structured, reactive UIs |
| Learning curve  | Easy initially        | Moderate              | Easy to moderate         |

**Remember:**

* **Vanilla JS** — build the UI yourself with plain JavaScript.
* **React** — build the UI using reusable components.
* **Vue.js** — build the UI using components and a reactive framework.

**Important distinction:** Vite is not a replacement for React or Vue. Vite runs the development server and builds your application; React or Vue provides the approach for building the UI.
