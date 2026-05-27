# Next.js Dashboard Tutorial Notes

## Chapter 1 — Getting Started

### What I did:
- Installed pnpm globally via npm
- Created Next.js project using `create-next-app` with the starter example
- Ran `pnpm approve-builds` to allow build scripts for `bcrypt` and `sharp`
- Installed dependencies with `pnpm i`
- Started dev server with `pnpm dev`
- Opened `http://localhost:3000` — unstyled home page appeared

### Project structure:
- `/app` — routes, components, logic
- `/app/lib` — utility functions, data fetching, placeholder data
- `/app/ui` — pre-styled UI components
- `/public` — static assets

### Notes & thoughts:
- The project uses TypeScript (`.ts`, `.tsx`) — types are manually defined in `definitions.ts`
- Placeholder data in `placeholder-data.ts` simulates a real database
- pnpm is faster than npm/yarn and is recommended for this course

### Screenshots:
![](image/image-01.png) 
![](image/image-02.png) 

## Chapter 2 — CSS Styling

### What I did:
- Added `import '@/app/ui/global.css'` to `/app/layout.tsx`
- Tested Tailwind by adding a black triangle div to `page.tsx`
- Created `/app/ui/home.module.css` with `.shape` class
- Replaced Tailwind triangle with CSS Module version
- Both approaches produce the same result

### Key concepts:
- `global.css` with `@tailwind` directives applies styles globally
- Tailwind — utility classes directly in JSX (`className="text-blue-500"`)
- CSS Modules — scoped styles, no class name conflicts
- `clsx` — conditionally toggle class names based on state

### Questions & thoughts:
- Tailwind є зручнішим для швидкої розробки, але CSS Modules краще для ізоляції стилів
- `clsx` вирішує проблему умовних класів без шаблонних рядків

### Screenshots:
![Styled home page](image/image-03.png)