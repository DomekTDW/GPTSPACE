# Kontekst startowy (Baseline)

## Cel
Ten plik zawiera minimalny i kompletny “snapshot” stanu pracy.
Nowy chat / model ma na jego podstawie od razu rozumieć:
- co zrobione
- co działa
- co jest celem
- jakim procesem pracujemy

---

## Projekt: Mentor AI Dashboard
Repo: `DomekTDW/TRADAI`  
Ścieżka: `TRADAI/mentor-ai-dashboard-full`

---

## Środowisko
- Terminal: **Google Cloud Shell**
- IDE: opcjonalnie (edycja/podgląd)
- Firebase CLI: zainstalowany i zalogowany jako `domektdw@gmail.com`

---

## Firebase
- Projekt: `mentor-ai-dashboard`
- Alias w `.firebaserc`: `default`

### Deploy wykonany
- `firebase deploy --only firestore:rules,firestore:indexes`

### Emulatory działają
- Auth Emulator
- Firestore Emulator
- Functions Emulator
Eksperyment: `firebase experiments:enable webframeworks`

### Seed
- `node scripts/seed.mjs`
- Dokument istnieje: `users/sampleUser`

---

## Frontend (Next.js)
Katalog: `mentor-ai-dashboard-full/web`

- `next` działa na porcie `3000`
- Dodano brakujące pliki:
  - `src/styles/globals.css`
  - `src/pages/index.tsx`
- Next wersja: `13.5.6`
- `.env.local`: tryb emulatorów

### Emulatory w frontend
`src/lib/firebase.ts`:
- łączy się z emulatorami przy `NEXT_PUBLIC_USE_EMULATORS=true`
- zabezpiecza multi-connect przez `globalThis.__FIREBASE_EMULATORS_CONNECTED__`

---

## Najbliższy cel
Auth + Login + Route Guards + CRUD goals:
- `src/lib/auth.tsx` (AuthProvider)
- `_app.tsx` wrap provider
- `pages/login.tsx`
- ochrona `pages/index.tsx`
- Firestore CRUD `goals`
