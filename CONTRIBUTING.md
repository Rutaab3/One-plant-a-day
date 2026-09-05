# CONTRIBUTING TO ONE PLANT A DAY

Thank you for your interest in contributing to One Plant a Day. We welcome contributions from developers, botanists, designers, and educators. This guide provides instructions and standards to help you contribute effectively.

---

## TABLE OF CONTENTS

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Features](#suggesting-features)
  - [Submitting Pull Requests](#submitting-pull-requests)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Commit Message Conventions](#commit-message-conventions)
- [Pull Request Process](#pull-request-process)

---

## CODE OF CONDUCT

This project is committed to providing a welcoming, respectful, and collaborative environment for all contributors. Please ensure that all interactions remain professional, inclusive, and constructive.

---

## HOW CAN I CONTRIBUTE?

### Reporting Bugs

Before creating a bug report, please check existing issues to avoid duplicates. When filing a bug report, include as much context as possible:

1. **Title**: Clear, descriptive title summarizing the problem.
2. **Steps to Reproduce**: Step-by-step instructions leading to the issue.
3. **Expected vs Actual Behavior**: Clear statement of what you expected to happen vs what actually occurred.
4. **Environment**: Browser name and version, operating system, and screen resolution.
5. **Console Logs / Screenshots**: Relevant error messages or visual screenshots.

### Suggesting Features

Feature requests are always welcome. When proposing a new feature:

1. Provide a detailed explanation of the proposed functionality.
2. Explain the use case and how it benefits users or contributors.
3. Detail any technical considerations or potential UI impacts.

### Submitting Pull Requests

1. Fork the repository and create your feature branch from `main`.
2. Ensure your changes follow the project coding standards.
3. Test your changes locally across different screen sizes and major browsers.
4. Submit a Pull Request targeting the `main` branch with a clear summary of changes.

---

## DEVELOPMENT SETUP

1. **Fork and Clone**:
   ```bash
   git clone https://github.com/YOUR-USERNAME/One-Plant-A-Day.git
   cd One-Plant-A-Day
   ```

2. **Create a Feature Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Run Locally**:
   Use a simple static file server to test changes:
   ```bash
   python3 -m http.server 8000
   ```
   Open `http://localhost:8000` in your web browser.

---

## CODING STANDARDS

### HTML
- Use semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`).
- Ensure proper element nesting and accessibility attributes (`alt` tags, ARIA labels).
- Keep indentation consistent using 2 spaces.

### CSS
- Maintain standard CSS variable naming in `css/base.css`.
- Keep page-specific styling inside dedicated stylesheets (`css/index.css`, `css/today.css`, etc.).
- Ensure fully responsive design using Bootstrap grid utilities and standard media queries.

### JavaScript
- Write clean, modern ES6+ JavaScript.
- Handle asynchronous operations (`fetch`) using `async/await` with `try...catch` blocks.
- Avoid global variable pollution where possible.
- Provide defensive fallback checks for missing data fields.

### Content & Emojis Policy
- Do not introduce emoji characters into core documentation files (`README.md`, `CONTRIBUTING.md`, `LICENSE`).

---

## COMMIT MESSAGE CONVENTIONS

Follow standard git commit conventions:

- Use short, descriptive subject lines (50 characters or less).
- Use the imperative mood (e.g., "Add calendar modal" instead of "Added calendar modal").
- Capitalize the subject line.
- Separate subject from body with a blank line when providing detailed explanations.

Example:
```
Add detailed plant habitat metadata section

Incorporate habitat and region field parsing into the today.html
display logic to give users geographical context for each entry.
```

---

## PULL REQUEST PROCESS

1. Update documentation if your changes modify features, API handling, or layout structure.
2. Ensure no linting errors or broken internal relative links exist.
3. Verify that responsive layouts function correctly on mobile, tablet, and desktop viewports.
4. Submit the Pull Request and link any relevant issue numbers.
5. A maintainer will review your Pull Request and provide feedback or approve the merge.
