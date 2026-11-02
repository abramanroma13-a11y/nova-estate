# NOVA ESTATE

Адаптивный сайт агентства недвижимости на React, TypeScript, Vite, Tailwind CSS и Lucide React. Включает каталог и карточки недвижимости, фильтры, избранное, контактные формы и административную панель.

## Запуск

```bash
npm install
npm run dev
```

Для production-сборки: `npm run build`.

## Демо-режим

Без переменных Supabase каталог, заявки и избранное сохраняются в `localStorage` браузера. Административная панель доступна по адресу `/admin`.

Демо-вход: `admin@novaestate.ru` / `nova2026`. Это только локальная демонстрация — перед размещением в интернете настройте Supabase Auth и удалите демо-вход из `src/supabase.ts`.

## Supabase

1. Создайте проект Supabase и выполните [supabase/schema.sql](./supabase/schema.sql) в SQL Editor.
2. Создайте пользователя администратора в Supabase Auth.
3. Добавьте запись `profiles` с `id` этого пользователя и `is_admin = true`.
4. Скопируйте `.env.example` в `.env.local` и укажите URL и anon key проекта.
5. Перезапустите Vite. Каталог, заявки и загруженные в `property-images` фотографии будут сохраняться в Supabase.

RLS-политики в схеме разрешают публичное чтение каталога и отправку заявок, а управление объектами и просмотр заявок ограничивают аккаунтами с `profiles.is_admin = true`. Используйте только публичный anon key на клиенте — service role key не должен попадать в приложение.
"# nova-estate" 
