# AI-Powered CEO Basics

**by Franciszek Georgiew & Automation House**

Repozytorium kontekstowe dla prezesa małej lub średniej firmy. Twój AI chief of staff — zna Twoją firmę, ludzi, strategię i otwarte sprawy. Działa w Claude Code.

Dostęp: wyłącznie dla członków 22 Community i uczestników webinarów AI Skills Days.

---

## Jak zacząć

### Krok 1 — Odpal `/_improve`

To jedyny krok, który musisz znać na start. AI zada Ci pytania o Twoją firmę — odpowiadaj swoimi słowami, wklejaj materiały, mów co masz. AI uzupełni pliki kontekstowe za Ciebie.

### Krok 2 — Pracuj z AI jak z chief of staff

Kiedy kontekst jest uzupełniony, AI zna Twoją firmę. Możesz:
- pytać o strategię, ludzi, finanse
- dyktować decyzje — AI zapisze je w odpowiednim miejscu
- prosić o napisanie wiadomości do zespołu w odpowiednim tonie
- wklejać notatki ze spotkań — AI wyciągnie z nich kontext
- monitorować otwarte sprawy (`open-loops.md`)

### Krok 3 — Kończ sesje przez `/_done`

Na koniec każdej produktywnej sesji odpal `/_done`. AI przeskanuje kontekst, zaktualizuje pliki i pokaże status otwartych spraw.

---

## Struktura repozytorium

| Plik | Co zawiera |
|------|-----------|
| `strategy.md` | Misja, wizja, pozycjonowanie, rynek, przewagi, kierunek strategiczny |
| `business.md` | Model biznesowy, oferta, pricing, finanse, cashflow, infrastruktura |
| `team.md` | Ludzie, role, odpowiedzialności, profile komunikacyjne |
| `growth.md` | Marketing, sprzedaż, kanały, klienci, pipeline |
| `open-loops.md` | Otwarte sprawy — max 10, z właścicielem i deadlinem |
| `CLAUDE.md` | Instrukcje dla AI — nie musisz edytować ręcznie |

---

## Jak to wykorzystać biznesowo

### Poziom 1 — Samo repo (zero integracji)

AI z pełnym kontekstem Twojej firmy. Bez podpinania czegokolwiek dostajesz:

- **Chief of staff na żądanie** — AI zna strategię, ludzi, finanse, otwarte sprawy. Pytasz — odpowiada z kontekstem, nie z pustki.
- **Pisanie wiadomości do zespołu** — AI wie, jak pisać do konkretnej osoby (formalnie do CFO, bezpośrednio do developera). Dyktuj intencję, AI napisze w odpowiednim tonie.
- **Monitoring otwartych spraw** — `/_done` na koniec sesji wymusza przegląd: co się otworzyło, co zmieniło status, co się blokuje.
- **Ingest surowych materiałów** — wklejasz notatki ze spotkania, prezentację, maila od klienta. AI wyciąga istotne informacje i proponuje update kontekstu.
- **Pamięć instytucjonalna** — decyzje, kontekst, relacje z klientami — wszystko w jednym miejscu, nie w głowie prezesa.

### Poziom 2 — Connectory dostępne w Claude Code

Claude Code ma wbudowane connectory, które możesz podłączyć bez pisania kodu:

| Connector | Co daje z tym repozytorium |
|-----------|---------------------------|
| **Google Calendar** | AI widzi Twój kalendarz. Wie, z kim masz spotkanie za godzinę i ładuje kontekst tej osoby z `team.md` lub `growth.md`. Po spotkaniu — pytasz "co z tego wynika?" i AI aktualizuje otwarte sprawy. |
| **Gmail** | AI przegląda inbox, flaguje maile wymagające akcji, drafutje odpowiedzi w kontekście Twojej firmy. Wie, że mail od klienta X dotyczy projektu Y, bo zna `growth.md`. |
| **Google Calendar + Gmail razem** | Poranny przegląd: "Co mam dziś, jakie maile przyszły, co jest otwarte?" — jeden prompt, pełny briefing. |

### Poziom 3 — Integracje po API / MCP z firmowym toolstackiem

Dla tych, którzy chcą pełną automatyzację:

| Integracja | Co daje |
|-----------|---------|
| **Task manager** (ClickUp, Linear, Asana, Monday) | AI widzi postęp zadań zespołu. Porównuje z `open-loops.md` — flaguje rozbieżności. "Maks miał to skończyć w piątek, task jest nadal in progress." |
| **CRM** (Airtable, HubSpot, Pipedrive) | AI zna pipeline sprzedażowy. Cross-referencuje z `growth.md`. "Klient X jest w demo stage od 3 tygodni — follow up?" |
| **Analytics** (PostHog, Mixpanel, GA4) | AI ściąga metryki produktowe i porównuje z celami w `business.md`. "Trialle spadły o 20% w/w — co się zmieniło?" |
| **Komunikacja** (Slack, Teams) | AI draftuje wiadomości do zespołu z właściwym tonem per osoba (z `team.md`). Może monitorować kanały i flagować tematy wymagające uwagi CEO. |
| **Księgowość** (Fakturownia, wFirma API) | AI porównuje rzeczywiste przychody/koszty z prognozą w `business.md`. Miesięczny cash review bez excela. |

**Jak podłączyć:** Każda integracja to MCP server w pliku `.mcp.json`. Szczegóły konfiguracji w dokumentacji Claude Code.

---

## Zasady

- Pliki kontekstowe to żywy dokument — aktualizuj regularnie
- AI nie nadpisuje bez Twojego potwierdzenia (poza `/_done` scanem)
- Surowe materiały wklejaj w sesji `/_improve` — AI wyciągnie kontekst
- Nie edytuj `CLAUDE.md` ręcznie — użyj `/_improve` jeśli chcesz zmienić zachowanie AI
