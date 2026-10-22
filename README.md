# SuvHisob — Vite + React + Supabase

Mobilga mos boshlang‘ich frontend. Ushbu loyiha mavjud Supabase bazasiga jadval yaratmaydi, ma’lumot yozmaydi/o‘chirmaydi va RLS siyosatlarini o‘zgartirmaydi.

## Mahalliy ishga tushirish
1. Node.js 20+ o‘rnating.
2. `npm install`
3. `.env.example` faylidan `.env.local` yarating.
4. `.env.local` ichida `VITE_SUPABASE_PUBLISHABLE_KEY` ni Supabase Dashboard → Project Settings → API Keys dagi publishable keyga almashtiring.
5. `npm run dev`

**Frontendga hech qachon `service_role` yoki secret key qo‘ymang.**

## GitHub
GitHub `jmajidov388-jpg/suv-hisob` repozitoriyasida Add file → Upload files orqali ZIP ichidagi loyiha fayllarini yuklang. `node_modules`, `dist`, `.env.local` yuklanmasin.

## Render Static Site
- Repository: `jmajidov388-jpg/suv-hisob`
- Branch: `main`
- Build Command: `npm install && npm run build`
- Publish Directory: `dist`
- Environment Variables:
  - `VITE_SUPABASE_URL` = `https://bjmlyxdqkxfyqyifsruh.supabase.co`
  - `VITE_SUPABASE_PUBLISHABLE_KEY` = Supabase publishable key

## Holat va xavfsizlik
Bu hozircha boshlang‘ich UI va read-only ulanish diagnostikasi, ishlab chiqarishga tayyor hisob-kitob tizimi emas. Login `supabase.auth.signInWithPassword({phone,password})` orqali urinadi; Supabase loyihasida Phone login yoqilgan bo‘lishi kerak. Profiles jadvaliga faqat `select count` read-only tekshiruvi bor; RLS xatosi yuz bersa, u ko‘rsatiladi. Fermer biriktirish, suv taqsimoti va hisobotlar haqiqiy schema tasdiqlanmaguncha ulanmagan. Barcha amallar RLS va server tomonida himoyalanishi shart.
