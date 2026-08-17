# Studio Noir — Salon Website

Single page salon website: hero, services with detail modals, barber
profiles, gallery, and an appointment booking form that saves to
Supabase and hands off to WhatsApp.

## Edit your content

Everything you need to rebrand lives in `src/data.js` — salon name,
phone, address, services (name, price, description, image), barbers,
and gallery images.

## Run locally

```
npm install
npm run dev
```

## Connect Supabase

1. Create a project at supabase.com
2. Open the SQL Editor and run `supabase/schema.sql` — this creates
   the `appointments` table the booking form writes to.
3. In Project Settings → API, copy the Project URL and anon public key.
4. Copy `.env.example` to `.env` and paste them in:
   ```
   VITE_SUPABASE_URL=...
   VITE_SUPABASE_ANON_KEY=...
   ```

## Deploy to Vercel

1. Push this folder to a GitHub repo.
2. In Vercel, "Add New Project" → import that repo (framework auto
   detects as Vite).
3. Add the same two env vars (`VITE_SUPABASE_URL`,
   `VITE_SUPABASE_ANON_KEY`) in Vercel Project Settings → Environment
   Variables.
4. Deploy. Every push to the repo redeploys automatically.

## Where bookings go

Submitted bookings are saved in the `appointments` table in Supabase
(check it under Table Editor), and also open WhatsApp with the same
details prefilled so the front desk gets an instant message.
