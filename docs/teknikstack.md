# Teknikstack – förslag

Utgångsläge: enkel hosting, låg driftkostnad, möjlighet att senare koppla direkt mot ekonomisystemet.

| Del | Val | Varför |
|---|---|---|
| Webbapp | **Next.js (TypeScript, React)** | Ett enda kodprojekt för gränssnitt och server-API. Stort ekosystem för tabeller, Gantt och export. |
| Hosting | **Vercel** (eller Netlify) | Gratisnivå räcker i början, cirka 20 USD/mån för ett team. Ingen server att sköta. |
| Databas, inloggning, filer | **Supabase** (Postgres + Auth + Storage) | Riktig SQL-databas med radbaserad behörighet (RLS), vilket passar delning med läs- eller redigeringsrätt. Inloggning med e-post eller Microsoft-konto. Gratisnivå, sedan 25 USD/mån. Kan driftas i EU. |
| Anbudstolkning | **Claude API** från serversidan | Läser PDF, Word och Excel och returnerar strukturerad JSON med osäkerhetsmarkering. Kostnad några kronor per anbud. |
| Excel-export | **ExcelJS** | Skriver riktiga formler, format och flera flikar. |
| PowerPoint-export | **PptxGenJS** | Lägesrapport med tabeller och diagram som går att redigera i PowerPoint. |
| Gantt | Egen SVG-komponent (eller **Frappe Gantt** som start) | Behöver ekonomikolumner bredvid staplarna, vilket färdiga bibliotek sällan klarar bra. |
| MS Project-export | Egen XML-generator | MSPDI-formatet är väldokumenterat. |

**Utbyggnad.** Timrapporter importeras först som filer. Datamodellen har en tabell för tidrader med källa (fil eller API), så en direktkoppling till Visma, Maconomy eller Agresso blir ett schemalagt jobb som skriver till samma tabell. Prognos, Gantt och export påverkas inte.

**Uppskattad driftkostnad:** 0 kr i test, cirka 500 kr/mån för ett mindre team plus AI-kostnad per anbud.

## Prototyp under etapperna

Under etapp 1–6 visas varje etapp som en klickbar prototyp (`prototyp/index.html`) så att funktion och flöde kan testas innan produktionsappen byggs. Prototypen använder samma datamodell som Postgres-schemat kommer att få.
