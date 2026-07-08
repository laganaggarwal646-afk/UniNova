# Project
UniNova is an AI-powered campus companion that unifies navigation, lost & found,
sports bookings, career resources, and an AI study assistant into one app for
students, faculty, campus administration, and visitors.

Full requirements: see SPEC.md at repo root.

Stack: React Native (Expo), Supabase (Auth + PostgreSQL), Google Maps API,
Firebase Cloud Messaging, Claude/OpenAI API.
Design source: tokens.css in repo root.

# Experience principles
Quiet · Trustworthy · Fast
If a screen breaks one of these, it does not ship.

# Conventions
- TypeScript strict.
- Real copy only — no Lorem ipsum, no placeholder button labels.
- One Supabase table per domain object (items, facilities, bookings, posts) —
  keep schema close to what's described in SPEC.md §5/§6.
- Every screen has empty, loading, error, and success states. No blank screens.
- AI features (Study Assistant) always include: a regenerate action, thumbs
  up/down feedback, a visible loading/streaming state, and a non-AI fallback
  for when the API call fails.

# Build order
1. Auth (Supabase Auth, email/password)
2. Dashboard (quick access to all modules + updates)
3. Campus Navigation (Google Maps)
4. Lost & Found (report / browse / contact)
5. Sports Hub (view facilities / book slots)
6. Career Hub (jobs / resources / events)
7. Study AI Assistant (Claude/OpenAI API) — build last, most complex

# Boundaries
- Do not change design tokens without asking.
- Do not add screens or features not listed in SPEC.md.
- Do not push to main — branch per feature (`feature/<name>`).
- Do not commit API keys, credentials, or Supabase secrets. Use `.env` and
  keep it in `.gitignore`.
- Do not invent npm/pip package names — verify against the registry before
  installing.

# When something breaks
State what was wanted vs. what was received, and ask for a fix to that one
thing only — do not refactor unrelated code in the same pass.
