# Tailwind CSS — Quick Setup Notes

Simple, copy-paste notes for setting up Tailwind CSS fast.

---

## Contents

- [1. Vite + React Setup](#1-vite--react-setup)
- [2. Next.js Setup](#2-nextjs-setup)
- [3. Plain HTML (CDN)](#3-plain-html-cdn)
- [4. Mental Model](#4-mental-model)
- [5. Why You Keep Losing Time](#5-why-you-keep-losing-time)
- [6. When You Need tailwind.config.js](#6-when-you-need-tailwindconfigjs)
- [7. Sanity Checklist](#7-sanity-checklist)
- [8. One-Liner Template](#8-one-liner-template)

---

## 1. Vite + React Setup

    npm create vite@latest my-app -- --template react
    cd my-app
    npm install -D tailwindcss @tailwindcss/vite

**vite.config.js**

    import { defineConfig } from 'vite'
    import react from '@vitejs/plugin-react'
    import tailwindcss from '@tailwindcss/vite'

    export default defineConfig({
      plugins: [react(), tailwindcss()],
    })

**src/index.css** (replace everything)

    @import "tailwindcss";

**src/main.jsx** — verify import:

    import './index.css'

Test:

    <h1 className="text-3xl font-bold text-red-500">Hello</h1>

---

## 2. Next.js Setup

    npx create-next-app@latest my-app

**Manual install:**

    npm install -D tailwindcss @tailwindcss/postcss postcss

**postcss.config.mjs**

    export default {
      plugins: { "@tailwindcss/postcss": {} },
    }

**app/globals.css**

    @import "tailwindcss";

---

## 3. Plain HTML (CDN)

    <script src="https://cdn.tailwindcss.com"></script>

Prototyping only. Never in production.

---

## 4. Mental Model

Tailwind v4 needs only 2 things:

| Piece | Purpose |
|---|---|
| Tailwind engine | Generates utility classes |
| CSS entry point | Where `@import "tailwindcss";` lives |

**5-step rule:**

1. Install `tailwindcss`
2. Add build-tool plugin (Vite / PostCSS / Next)
3. Add `@import "tailwindcss";` to main CSS
4. Import that CSS in app entry
5. Restart dev server

No `tailwind.config.js` needed — v4 auto-detects files.

---

## 5. Why You Keep Losing Time

| Problem | Fix |
|---|---|
| Mixing v3 tutorials with v4 installs | v4 has no `init` command |
| Forgetting CSS import in main.jsx / layout.tsx | Verify the import path |
| Not restarting dev server | Kill and restart |
| Using `npx tailwindcss init -p` on v4 | That's v3 only |
| Installing postcss + autoprefixer for v4 | Not needed unless using PostCSS path |
| Old `content: []` config | v4 auto-detects files |

---

## 6. When You Need tailwind.config.js

Only for custom theme, plugins, or content overrides.

    npm install -D tailwindcss @tailwindcss/postcss

**tailwind.config.js**

    export default {
      content: ["./index.html", "./src/**/*.{js,jsx,ts,tsx}"],
      theme: { extend: {} },
      plugins: [],
    }

**src/index.css**

    @import "tailwindcss";
    @config "../tailwind.config.js";

Note: `@config` is only required if the config is in a non-default location or migrating from v3.

---

## 7. Sanity Checklist

- [ ] `tailwindcss` in devDependencies
- [ ] Plugin added to build tool
- [ ] `@import "tailwindcss";` in CSS entry
- [ ] CSS entry imported in app root
- [ ] Dev server restarted
- [ ] Test: `<div className="p-4 bg-blue-500">test</div>`

If it fails:

- DevTools → check if `.p-4` exists in loaded CSS
- If not → content path isn't detecting files
- Hard refresh (Ctrl+Shift+R)

---

## 8. One-Liner Template

Vite + React:

    npm create vite@latest . -- --template react && npm i && npm i -D tailwindcss @tailwindcss/vite

Then paste the 3 snippets from Section 1. Done in ~90 seconds.

---

## Links

- [Tailwind v4 Docs](https://tailwindcss.com/docs/installation)
- [Vite Guide](https://tailwindcss.com/docs/installation/using-vite)
- [Next.js Guide](https://tailwindcss.com/docs/installation/framework-guides/nextjs)

---

*Tailwind v4.x · Save this file. Stop re-Googling.*
