## Додаток NoteHub

Виконано рефакторинг проекту з https://github.com/id753/05-notehub . </br>
У попередній версії NoteHub був односторінковим додатком (SPA). Тепер  реалізовано багатосторінкову структуру з використанням маршрутизації Next.js.</br>

Глобальний Layout </br>
API-запити, env змінні </br>
Сторінка списку нотатків. Реалізовано сторінковий компонент Notes у маршруті /notes як SSR-компонент, де заздалегідь виконується prefetch (попереднє завантаження даних через TanStack Query) з гідратацією кешу. Усю клієнтську логіку (отримання списку нотаток за допомогою useQuery та їх відображення) винесено в окремий файл компонента app/notes/Notes.client.tsx.</br>
Обробка помилок і завантаження</br>
Сторінка з деталями однієї нотатки.  Створено динамічний маршрут для сторінки з деталями однієї нотатки за її id. Реалізовано сторінковий компонент NoteDetails у маршруті /notes/[id] як SSR-компонент</br>
Для отримання динамічного id в клієнтському компоненті використано хук useParams().</br>
Створено в components\TanStackProvider\TanStackProvider.tsx компонент, який додає QueryClientProvider. Підключено його глобально в app/layout.tsx, щоб забезпечити правильну роботу кешування та роботи з запитами через TanStack Query в усіх компонентах додатка.</br>
.................................................................................</br>
Проект розгорнуту на Vercel.</br>
Проєкт створено за допомогою Next.js (App Router).</br>
  Усі компоненти, які не прив'язані безпосередньо до маршруту та їх частин, зберігаються в папці components.</br>
    Загальні типи та інтерфейси винесені до файлу types/note.ts.</br>
    Функції роботи з API винесені в lib/api/ у вигляді окремих модулів.</br>
    Для HTTP-запитів використовується бібліотека axios.</br>
    Стан запитів у CSR-компонентах керується через TanStack Query (React Query).</br>
    Усі компоненти типізовані з використанням TypeScript.</br>
    Код має бути відформатований за допомогою Prettier.</br>
    Стилізація – за допомогою CSS Modules.</br>
    У проєкті реалізована підтримка SSR та CSR, відповідно до завдання.</br>
    .................................................................................</br>
This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
