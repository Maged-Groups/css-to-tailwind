<div align="center">

# ✨ Portfolio → Tailwind CSS 4

### From plain HTML + CSS to a utility-first portfolio — built to last

<br />

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript_Later-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Dark Mode](https://img.shields.io/badge/Dark_Mode-0F172A?style=for-the-badge&logo=moonrepo&logoColor=white)

<br />

**A real portfolio project** — not a throwaway exercise.<br />
Convert the styling. Keep the structure. Wire JavaScript later in ~10 lines.

<br />

[📘 Open Migration Guide](./guides.html) · [🖥️ View Portfolio](./index.html)

<br />

</div>

---

## 🎯 At a Glance

| | |
|:---|:---|
| **Goal** | Convert the whole page to Tailwind utilities and delete `styles.css` |
| **Duration** | 2 – 3 hours of focused work |
| **Deliverable** | `index.html` + structure ready for JavaScript |
| **Layout system** | Flexbox only (responsive, no CSS Grid) |

---

## 💡 Why This Project Matters

You're not converting a throwaway design — you're building a **portfolio you will actually use**.

After you learn JavaScript, you come back and add a handful of lines to make the page **alive**:

- 🌙 Dark mode toggles with one click
- 🔍 Project filters work with one click

That's the difference between an exercise and a real project.

> **Architectural principle:** separate *presentation* (HTML + CSS / Tailwind) from *behavior* (JS).  
> Today you build the interface and leave “sockets.” Tomorrow you wire the electricity.

---

## 🗂️ Project Structure

```text
Taks Portfolio/
├── index.html          # 🖥️  The portfolio (plain HTML + CSS)
├── guides.html         # 📘  Interactive Tailwind 4 migration guide
├── README.md           # 📖  You are here
└── assets/
    ├── css/
    │   └── styles.css  # Design tokens + Flexbox layouts
    └── imgs/           # Avatar, project covers, logos
```

---

## 🚀 Quick Start

```bash
# Open the portfolio
open index.html

# Open the step-by-step migration guide
open guides.html
```

> Tip: use Live Server (VS Code) so dark mode / checklist `localStorage` works cleanly in the guide.

---

## 🗺️ Migration Roadmap

Follow the guide in order. Don’t move on until the current section **visually matches** the original.

```text
  ┌─────────────┐
  │  1. Setup   │  CDN + Tailwind browser script
  └──────┬──────┘
         ▼
  ┌─────────────┐
  │  2. @theme  │  Move :root tokens → @theme utilities
  └──────┬──────┘
         ▼
  ┌─────────────┐
  │ 3. Dark Mode│  @custom-variant dark (critical!)
  └──────┬──────┘
         ▼
  ┌────────────────────┐
  │ 4. Convert Sections │  Body → Header → Hero → About/Skills → Projects → Contact
  └──────┬─────────────┘
         ▼
  ┌─────────────┐
  │  Checklist  │  Verify every item before submit
  └──────┬──────┘
         ▼
  ┌─────────────┐
  │  JS Phase   │  Theme toggle + filters (later)
  └─────────────┘
```

### Section conversion order

| Step | Section | Key idea |
|:----:|:--------|:---------|
| 4.1 | Body & base | `bg-slate-50`, `dark:`, `font-sans` |
| 4.2 | Header | `flex` + `hidden md:flex` for nav |
| 4.3 | Hero | Centered Flex column + `rounded-full` avatar |
| 4.4 | About + Skills | `md:flex-row`, `flex-wrap`, equal-width children |
| 4.5 | Projects + filters | Flex wrap cards + `data-filter` / `data-category` sockets |
| 4.6 | Contact + Footer | Flex wrap links, responsive footer |

---

## 🧩 Features

<div align="center">

| 🖥️ Portfolio | 📘 Guide | 🔌 Ready for JS |
|:---:|:---:|:---:|
| Responsive Flex layouts | Step-by-step Tailwind 4 path | Theme toggle socket |
| Light / Dark CSS tokens | Live checklist + cheat sheet | Project filter sockets |
| Sticky header + sections | Theme & checklist in `localStorage` | `data-*` contracts |

</div>

---

## 🎨 Design Tokens (preview)

These start in `styles.css` as CSS variables, then move into Tailwind 4 `@theme`:

```css
@theme {
  --color-primary: #6366f1;
  --color-primary-light: #818cf8;
  --color-primary-dark: #4f46e5;
  --font-sans: "Inter", system-ui, sans-serif;
}

@custom-variant dark (&:where(.dark, .dark *));
```

Once inside `@theme`, tokens become utilities like `bg-primary`, `text-primary`, and `font-sans`.

---

## ⚡ Cheat Sheet (CSS → Tailwind)

| CSS | Tailwind 4 |
|:----|:-----------|
| `display: flex;` | `flex` |
| `flex-direction: column;` | `flex-col` |
| `flex-wrap: wrap;` | `flex-wrap` |
| `flex: 1 1 0;` | `flex-1` |
| `align-items: center;` | `items-center` |
| `justify-content: space-between;` | `justify-between` |
| `gap: 24px;` | `gap-6` |
| `border-radius: 999px;` | `rounded-full` |
| `transform: translateY(-4px);` | `hover:-translate-y-1` |
| `object-fit: cover;` | `object-cover` |

---

## ✅ Submission Checklist (HTML + Tailwind Phase)

Don't submit until every item is done:

- [ ] Added `@tailwindcss/browser@4` script in `<head>`
- [ ] Moved every `:root` variable into `@theme`
- [ ] Added `@custom-variant dark (&:where(.dark, .dark *));` — **the most important one**
- [ ] Manually toggled `<html class="dark">` and dark mode works
- [ ] Header converted — nav uses `hidden md:flex`
- [ ] Hero converted — avatar uses `rounded-full`
- [ ] About + Skills converted with **Flexbox**
- [ ] Filter bar converted — “All” active by default
- [ ] All project cards converted with `hover:-translate-y-1`
- [ ] Contact + Footer converted
- [ ] Responsive at **375px** (no horizontal scroll)
- [ ] Responsive at **768px** (nav appears, two columns)
- [ ] Responsive at **1280px** (projects in 3 columns)
- [ ] Kept every `id` and `data-*` attribute for the JS phase
- [ ] Deleted `styles.css` and every reference to it
- [ ] Final result matches the original in **light + dark**

Track progress interactively in [`guides.html`](./guides.html) — checklist state is saved to `localStorage`.

---

## 🔌 JavaScript Phase (Later)

Not required now — but the sockets are already in the HTML.

### Theme toggle (~3 lines)

```js
const toggle = document.getElementById('theme-toggle');

toggle.addEventListener('click', () => {
  document.documentElement.classList.toggle('dark');
});
```

### Project filters

Buttons expose `data-filter`. Cards expose `data-category`.  
JS only toggles classes / `hidden` — **no new styling in JavaScript**.

---

## 🛠️ Prerequisites

1. The original project files (`index.html`, `assets/`)
2. A modern browser + VS Code (recommended)
3. Working knowledge of semantic HTML — **don’t change tags**
4. Basics of **Flexbox** — used for all layouts

---

## 🐛 Troubleshooting

| Symptom | Likely cause |
|:--------|:-------------|
| `dark:` utilities do nothing | Missing `@custom-variant dark` |
| Horizontal scroll on mobile | Fixed widths without `w-full` / breakpoints |
| Nav missing on tablet+ | Forgot `hidden md:flex` |
| Theme flashes on guide reload | `localStorage` theme script must run before paint |

Full troubleshooting live in [`guides.html#troubleshooting`](./guides.html#troubleshooting).

---

## 📚 Learn More

| Resource | Link |
|:---------|:-----|
| Interactive migration guide | [`guides.html`](./guides.html) |
| Tailwind CSS 4 docs | [tailwindcss.com](https://tailwindcss.com/docs) |
| Flexbox reference | [CSS Tricks — Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) |

---

<div align="center">

<br />

**Built for Frontend learners** · Portfolio → Tailwind CSS 4

`HTML` · `CSS` · `Tailwind 4` · `Flexbox` · `Dark Mode` · `JS later`

<br />

⭐ Start with the guide → open [`guides.html`](./guides.html)

</div>
