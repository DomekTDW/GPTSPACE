# Decyzje (Architecture & Process Decisions)

## Cel
Lista decyzji, które stabilizują projekt i proces pracy.
Każda decyzja ma:
- datę
- kontekst
- decyzję
- konsekwencje

---

## [YYYY-MM-DD] Cloud Shell jako główny terminal
### Kontekst
Workspace IDE nie zapewnia stabilnego terminala do długiej pracy.

### Decyzja
Cloud Shell jest jedynym terminalem do ops.

### Konsekwencje
- powtarzalność
- łatwiejsze debugowanie
- prostszy runbook

---

## [YYYY-MM-DD] Tryb: Komenda → wynik → następna komenda
### Kontekst
Zbyt dużo równoległych kroków generowało chaos.

### Decyzja
Pracujemy sekwencyjnie (terminal).

### Konsekwencje
- mniej błędów
- łatwiejsze cofanie

---

## [YYYY-MM-DD] Gemini jako akcelerator
### Kontekst
Potrzeba szybkiego generowania patchy i diagnoz.

### Decyzja
Gemini generuje patch, ale kontrola jakości i architektura = ChatGPT.

### Konsekwencje
- szybciej
- mniej błędnych refactorów
