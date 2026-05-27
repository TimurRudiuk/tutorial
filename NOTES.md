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

## Chapter 4 — Creating Layouts and Pages

### Що зробив:
- Створив `/app/dashboard/page.tsx` — сторінка `/dashboard`
- Створив `/app/dashboard/customers/page.tsx` — сторінка `/dashboard/customers`
- Створив `/app/dashboard/invoices/page.tsx` — сторінка `/dashboard/invoices`
- Створив `/app/dashboard/layout.tsx` з компонентом `<SideNav />`

### Ключові концепції:
- File-system routing — папки визначають роути, `page.tsx` робить роут доступним
- `layout.tsx` — спільний UI для кількох сторінок
- Partial rendering — при навігації оновлюється тільки `page.tsx`, layout не ре-рендериться
- Colocation — UI компоненти, тести і код можна тримати поряд з роутами
- Root layout (`/app/layout.tsx`) — обов'язковий, застосовується до всіх сторінок

### Нотатки:
- Зручно що layout автоматично огортає всі дочірні сторінки через `children`
- Partial rendering зберігає React state при переходах між сторінками

### Скріншоти:
![](image/image-05.png)
![](image/image-06.png)
![](image/image-07.png)

## Chapter 5 — Navigating Between Pages

### Що зробив:
- Замінив `<a>` теги на `<Link>` компонент в `nav-links.tsx`
- Додав `'use client'` directive бо використовується хук
- Додав `usePathname()` хук для отримання поточного шляху
- Використав `clsx` для підсвічування активного посилання синім

### Ключові концепції:
- `<Link>` — клієнтська навігація без повного перезавантаження сторінки
- `usePathname()` — хук для отримання поточного URL шляху
- Automatic code-splitting — Next.js ділить код по роутах, кожна сторінка ізольована
- Prefetching — в продакшні Next.js автоматично prefetch-ить код для посилань у viewport

### Нотатки:
- `'use client'` потрібен бо хуки працюють тільки на клієнті
- Prefetching робить навігацію майже миттєвою — код вже завантажений до кліку

### Скріншоти:
![](image/image-08.png)