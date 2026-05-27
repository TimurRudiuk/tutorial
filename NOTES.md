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