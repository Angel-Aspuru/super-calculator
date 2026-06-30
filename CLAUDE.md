# Super Calculator

## Project overview

A beginner-friendly Angular 19 calculator built for teaching purposes. Students practice implementing missing methods and writing unit tests. The core arithmetic (add, subtract, multiply, divide) is already working — the exercises focus on the utility functions and CSS theming.

## Tech stack

- Angular 19 (standalone components — no NgModule)
- TypeScript 5.7
- Karma + Jasmine for unit tests
- Node.js 20.x required — Angular 19 does not support Node 22+

## How to run

- Install dependencies: `npm install`
- Dev server: `npm start` → http://localhost:4200
- Run tests: `npm run ng -- test --watch=false --browsers=ChromeHeadless`
- Production build: `npm run build`

## Project structure

```
src/app/
├── app.component.ts    — component logic: state properties + button handlers
├── app.component.html  — template with Angular event and property bindings
├── app.component.css   — scoped styles + light mode overrides (.light class)
└── app.component.spec.ts — Karma/Jasmine test suite (24 tests)
```

## Exercises (already implemented)

All three exercises have been completed on branch `feature/parte-1-ejercicios`:

- **Exercise 1 — `pressToggleSign()`**: flips the sign of the displayed number (`5` → `-5`). Handles the `-0` edge case.
- **Exercise 2 — `pressPercent()`**: divides the displayed number by 100 (`50` → `0.5`).
- **Exercise 3 — `toggleTheme()`**: flips `isLightMode` boolean; the template binds `[class.light]="isLightMode"` so CSS updates automatically. Light mode colors are defined in `app.component.css` under the `.light` selectors.

## Coding conventions

- Button handler methods follow the `press<Action>()` naming pattern.
- `this.display` is always a `string`; use `parseFloat` to convert before arithmetic and `.toString()` to convert back.
- In tests, always call `fixture.detectChanges()` after mutating component state so the DOM re-renders before asserting.
- No comments explaining *what* the code does — only *why* when the reason is non-obvious.
