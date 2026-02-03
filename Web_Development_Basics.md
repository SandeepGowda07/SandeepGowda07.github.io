# Web Development Fundamentals: Portfolio Edition

This guide explains the core technologies used to build your portfolio. It covers the basics of HTML, CSS, and JavaScript with syntax examples and real-world applications from your project.

---

## 1. HTML5 (The Structure)
HTML (HyperText Markup Language) provides the skeleton of your website.

### Semantic Elements
Instead of using `<div>` for everything, we use **Semantic Tags**. These help search engines (SEO) and screen readers understand your page structure.
- `<header>`: The top section (logo, navigation).
- `<main>`: The unique content of the page.
- `<section>`: A thematic grouping of content (e.g., Projects, Skills).
- `<article>`: A self-contained piece of content (e.g., a Single Project Card).
- `<aside>`: Content indirectly related to the main content (e.g., your "At a glance" card).

**Example Syntax:**
```html
<section id="projects">
  <h2>My Work</h2>
  <article class="project-card">
    <h3>Project Name</h3>
    <p>Description...</p>
  </article>
</section>
```

---

## 2. CSS3 (The Styling)
CSS (Cascading Style Sheets) controls how your HTML looks.

### CSS Variables (`:root`)
Variables allow you to store values and reuse them. This makes it easy to change colors across the entire site by updating just one line.
**Syntax:**
```css
:root {
  --brand-color: #6ee7b7;
}

h1 {
  color: var(--brand-color);
}
```

### Flexbox vs. Grid
- **Flexbox**: Best for rows or columns (1D layout). Used in your **Navigation** and **KPIs**.
- **Grid**: Best for complex layouts (2D layout). Used in your **Project Grid** and **Skills Stack**.

**Flexbox Example:**
```css
.nav-links {
  display: flex;
  justify-content: space-between; /* Spreads items out */
  gap: 20px;                      /* Space between items */
}
```

**Grid Example:**
```css
.projects-grid {
  display: grid;
  grid-template-columns: 1fr 1fr; /* Two equal columns */
  gap: 24px;
}
```

### Animations (`@keyframes`)
Animations bring the site to life. Your "Dot Pulse" and "Underline Grow" animations use this.
**Syntax:**
```css
@keyframes pulse {
  0% { transform: scale(1); }
  100% { transform: scale(1.1); }
}

.dot {
  animation: pulse 2s infinite alternate;
}
```

---

## 3. JavaScript (The Interactivity)
JavaScript makes your site respond to the user and their actions.

### DOM Manipulation
The **Document Object Model (DOM)** is the browser's representation of your HTML. JavaScript can "select" elements and change them.
**Syntax:**
```javascript
// Selecting an element and changing its text
const yearSpan = document.getElementById('year');
yearSpan.textContent = "2026";
```

### Intersection Observer (Scroll Effects)
This is a modern way to detect when an element enters the screen. We use it to trigger the "fade-in" of your skill cards and the "count-up" of your M.Sc. grade.
**Syntax:**
```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible'); // Trigger animation
    }
  });
});

observer.observe(targetElement);
```

### LocalStorage (Memory)
This allows your browser to remember small amounts of data even after a refresh. We use it for your **Theme Toggle** (Light/Dark mode).
**Syntax:**
```javascript
// Saving a value
localStorage.setItem('theme', 'dark');

// Loading a value
const savedTheme = localStorage.getItem('theme');
```

---

## Summary of Techniques Used
| Feature | Technology Used | Benefit |
| :--- | :--- | :--- |
| **Theme Toggling** | JavaScript + CSS Variables | User preference persistence |
| **Responsive Grid**| CSS Grid + Media Queries | Works on Phone, Tablet, and Desktop |
| **Smooth Loading** | Intersection Observer + Transitions | High-end, premium feel |
| **SEO Optimization**| Semantic HTML + Meta Tags | Better visibility on Google |

---

### How to Save as PDF
1. Open this file in your browser or a Markdown viewer.
2. Press **Ctrl + P** (Cmd + P on Mac).
3. Select **"Save as PDF"** as the destination.
