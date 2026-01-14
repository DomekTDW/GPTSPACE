# Runbook (operacje i komendy)

## Cel
Ten plik ma pozwolić:
- szybko wystartować środowisko od zera,
- wrócić do pracy po przerwie,
- diagnozować typowe problemy.

---

## 0) Ustawienia
Domyślnie pracujemy w:
- `~/TRADAI/mentor-ai-dashboard-full`

---

## 1) Firebase login
```bash
firebase --version
firebase login
firebase projects:list | head
```

---

## 2) Ustaw projekt
```bash
cd ~/TRADAI/mentor-ai-dashboard-full
firebase use
```

Jeśli brak aliasu:
```bash
firebase use --add
```

---

## 3) Deploy Firestore rules/indexes
```bash
firebase deploy --only firestore:rules,firestore:indexes
```

---

## 4) Emulatory (Auth/Firestore/Functions)
```bash
firebase emulators:start --only auth,firestore,functions
```

---

## 5) Build functions
```bash
cd ~/TRADAI/mentor-ai-dashboard-full/functions
npm install
npm run build
ls -la lib | head
```

---

## 6) Seed Firestore emulator
W osobnym terminalu:
```bash
cd ~/TRADAI/mentor-ai-dashboard-full
npm i firebase-admin
export FIRESTORE_EMULATOR_HOST="127.0.0.1:8080"
export FIREBASE_PROJECT_ID="mentor-ai-dashboard"
node scripts/seed.mjs
```

---

## 7) Next dev
```bash
cd ~/TRADAI/mentor-ai-dashboard-full/web
npm install
npm run dev -- --port 3000
```

---

## Typowe problemy
### Next tarball 404
- zmiana wersji `next` w `web/package.json` (np. 13.5.6)

### Strona 404
- brak `src/pages/index.tsx`

### “missing required error components”
- sprawdź logi w terminalu `npm run dev`, zwykle brak plików / CSS

### Functions emulator nie ładuje
- brak `functions/lib/index.js`
- fix: `npm run build`
