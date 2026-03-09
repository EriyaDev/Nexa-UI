# Nexa UI

A comprehensive collection of modern, accessible, and fully customizable UI components built with **Tailwind CSS**.

Nexa UI is designed to help developers build high-quality web interfaces faster. Instead of spending hours styling basic elements or wrestling with complex frameworks, leverage our pre-built components to focus on what truly matters: **building your application's logic and user experience.**

---

## Quick Start

Get up and running with Nexa UI in seconds. Since all components are built entirely with Tailwind CSS utility classes, the setup is straightforward.

### 1. Install Tailwind CSS

Ensure you have Tailwind CSS installed and configured in your project. If you haven't, follow the [official installation guide](https://tailwindcss.com/docs/installation/).

### 2. Install Remix Icon

Nexa UI uses [Remix Icon](https://remixicon.com/) for clean, consistent iconography.

```bash
npm install remixicon --save
```

Then add the following import to your CSS file:

```css
@import 'remixicon/fonts/remixicon.css';
```

### 3. Optimized Configuration

To achieve the best visual results and ensure full compatibility with Nexa UI components, update your CSS file with the following configuration:

```css
@import url('https://fonts.googleapis.com/css2?family=Hanken+Grotesk:ital,wght@0,100..900;1,100..900&family=Manrope:wght@200..800&family=Space+Mono:ital,wght@0,400;0,700;1,400;1,700&display=swap');
/* @import 'remixicon/fonts/remixicon.css'; goes here */
/* @import 'tailwindcss'; goes here */

/* Custom Variables */
@theme {
  --font-manrope: 'Manrope', 'sans-serif';
  --font-grotesk: 'Hanken Grotesk', 'sans-serif';
  --font-space-mono: 'Space Mono', 'monospace';
  --breakpoint-3xl: 120rem;

  --color-primary: #ffffff;

  --color-button-primary: #1d1d1d;
  --color-button-secondary: #ffffff;

  --color-text-primary: #1c1c1c;
  --color-text-secondary: #525252;

  --color-avocado-100: oklch(0.99 0 0);
  --color-avocado-200: oklch(0.98 0.04 113.22);
  --color-avocado-300: oklch(0.94 0.11 115.03);
  --color-avocado-400: oklch(0.92 0.19 114.08);
  --color-avocado-450: oklch(0.88 0.18 117.33);
  --color-avocado-500: oklch(0.84 0.18 117.33);
  --color-avocado-600: oklch(0.53 0.12 118.34);
  --color-avocado-700: oklch(0.45 0.12 118.34);
  --color-avocado-800: oklch(0.38 0.12 118.34);
  --color-avocado-900: oklch(0.3 0.12 118.34);
  --color-avocado-1000: oklch(0.2 0.12 118.34);
}
```

### 4. Copy & Paste

You're all set! Browse the component library, find what you need, and copy the code directly into your project files.
