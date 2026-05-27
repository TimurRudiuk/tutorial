# Next.js Dashboard Tutorial Notes

## Chapter 1 — Getting Started

### Що зробив:
- Встановив pnpm глобально через npm
- Створив Next.js проєкт через `create-next-app` зі starter example
- Запустив `pnpm approve-builds` щоб дозволити build scripts для `bcrypt` і `sharp`
- Встановив залежності через `pnpm i`
- Запустив dev сервер через `pnpm dev`
- Відкрив `http://localhost:3000` — з'явилась unstyled сторінка

### Структура проєкту:
- `/app` — роути, компоненти, логіка
- `/app/lib` — утиліти, функції для fetching даних, placeholder data
- `/app/ui` — UI компоненти
- `/public` — статичні файли

### Нотатки:
- Проєкт написаний на TypeScript — типи визначені вручну в `definitions.ts`
- Placeholder data в `placeholder-data.ts` імітує реальну базу даних
- pnpm швидший за npm/yarn

### Скріншоти:
![](image/image-01.png)
![](image/image-02.png)

## Chapter 2 — CSS Styling

### Що зробив:
- Додав `import '@/app/ui/global.css'` в `/app/layout.tsx`
- Протестував Tailwind — додав чорний трикутник в `page.tsx`
- Створив `/app/ui/home.module.css` з класом `.shape`
- Замінив Tailwind трикутник на CSS Module версію

### Ключові концепції:
- `global.css` з `@tailwind` директивами застосовує стилі глобально
- Tailwind — utility класи прямо в JSX (`className="text-blue-500"`)
- CSS Modules — scoped стилі, без конфліктів класів
- `clsx` — умовне перемикання класів залежно від стану

### Нотатки:
- Tailwind зручніший для швидкої розробки, але CSS Modules краще для ізоляції стилів
- `clsx` вирішує проблему умовних класів без шаблонних рядків

### Скріншоти:
![](image/image-03.png)

## Chapter 3 — Optimizing Fonts and Images

### Що зробив:
- Створив `/app/ui/fonts.ts` з шрифтами Inter (основний) і Lusitana (додатковий)
- Додав Inter до `<body>` в `layout.tsx` з класом `antialiased`
- Застосував Lusitana до `<p>` елемента в `page.tsx`
- Розкоментував компонент `<AcmeLogo />`
- Додав desktop hero image через `next/image` (прихований на мобільних)
- Додав mobile hero image (прихований на десктопі)

### Ключові концепції:
- `next/font` завантажує шрифти під час білду — без додаткових мережевих запитів
- Cumulative Layout Shift (CLS) — метрика Google для оцінки стабільності верстки
- `next/image` автоматично: lazy loading, resize, WebP формат, запобігає layout shift
- `width` і `height` в `<Image>` — розміри оригінального файлу для aspect ratio

### Нотатки:
- Next.js хостить шрифти разом зі статичними файлами — розумне рішення для продуктивності
- `hidden md:block` і `block md:hidden` — зручний Tailwind патерн для responsive зображень

### Скріншоти:
![](image/image-04.png)