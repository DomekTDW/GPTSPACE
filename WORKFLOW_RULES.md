# System współpracy (Workflow Rules)

## Cel dokumentu
Ten dokument definiuje zasady naszej współpracy oraz sposób pracy nad projektami.
Ma zapewniać:
- powtarzalność działań,
- bezpieczeństwo,
- brak chaosu,
- możliwość łatwego wznowienia pracy po przerwie / nowym czacie.

---

## Zasady nadrzędne
1) **Tryb pracy w terminalu: Komenda → wynik → następna komenda**
2) **Cloud Shell = jedyny terminal operacyjny**
   - install / deploy / build / emulators / debug
3) IDE/Workspace = edycja kodu + podgląd, bez polegania na terminalu IDE
4) Gemini w Cloud Shell = akcelerator (patch / diagnostyka), ale:
   - architektura i kolejność prac = ChatGPT
5) Zawsze pracujemy na minimalnym, kontrolowanym zakresie zmian (small commits).
6) Jeśli błąd: wklejamy pełny log i naprawiamy krokowo.

---

## Protokół pracy w terminalu
### Standard
- Ja (ChatGPT) podaję **jedną komendę** lub blok komend.
- Użytkownik wkleja **output z terminala**.
- Dopiero wtedy dostajesz następny krok.

### Dopuszczalne łączenie komend
Można wkleić kilka komend naraz, jeśli:
- są w tym samym katalogu roboczym,
- nie ma ryzyka utraty danych,
- nie zależą od outputu poprzedniej.

---

## Bezpieczeństwo zmian
### Zakazane / wymagają ostrzeżenia
- `npm audit fix --force`
- masowe upgrady dependency bez powodu
- `firebase init` bez planu (ryzyko nadpisania configów)
- deploy bez upewnienia się, na jakim projekcie Firebase jesteśmy

### Zasada
Jeśli operacja jest destrukcyjna → zawsze ostrzegamy i uzasadniamy.

---

## Źródło prawdy (hierarchia informacji)
1) Pliki `.md` w projekcie (stan, decyzje, runbook)
2) Wiadomości w czacie
3) Screenshoty jako materiał pomocniczy

---

## Status / Zdanie kontrolne
Jeżeli proces się rozjeżdża:
- wracamy do Runbook
- robimy retrospektywę
- dopisujemy nową zasadę
