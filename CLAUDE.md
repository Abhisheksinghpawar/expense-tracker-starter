# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install       # Install dependencies
npm run dev       # Start dev server at http://localhost:5173
npm run build     # Production build
npm run lint      # Run ESLint
npm run preview   # Preview production build
```

> Node.js 20.19+ or 22.12+ is required by Vite 7. Node 20.17 works with a warning but may cause issues.

## Architecture

This is a single-file React app — all logic lives in `src/App.jsx`. There are no external state management libraries, routing, or backend. State is managed with `useState` hooks only, and all data is in-memory (no persistence).

**Known issues in the starter code (intentional for the course):**
- `amount` is stored as a string, causing string concatenation instead of numeric addition in `totalIncome`/`totalExpenses` calculations.
- "Freelance Work" is miscategorized as `type: "expense"` with `category: "salary"`.
- No delete functionality despite `.delete-btn` CSS class existing in `App.css`.

**Data model** — each transaction has: `{ id, description, amount, type, category, date }` where `type` is `"income"` or `"expense"` and `category` is one of `["food", "housing", "utilities", "transport", "entertainment", "salary", "other"]`.

**Styling** — flat CSS in `src/App.css` (component styles) and `src/index.css` (global reset). Color conventions: income = green, expenses = red via `.income-amount` / `.expense-amount` classes.
