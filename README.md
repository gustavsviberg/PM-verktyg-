# PM-verktyg

Webbaserat verktyg för projektledare: från anbud till budget, timuppföljning, prognos, Gantt-tidplan och export. Allt gränssnitt på svenska.

## Status

| Etapp | Innehåll | Status |
|---|---|---|
| 1 | Projektlista, nytt projekt, anbudsimport med namnförslag och fråga om fast/rörligt | Klar för granskning |
| 2 | Budget med låsfunktion och ändringslogg | – |
| 3 | Import av timrapporter och prognos | – |
| 4 | Gantt-tidplan med prognoskolumner | – |
| 5 | Export till Excel och PowerPoint | – |
| 6 | Delning och behörigheter | – |

## Etapp 1

`prototyp/index.html` är en fristående sida. Öppna den i en webbläsare för att prova:

- Rullista med projekt och knappen **Nytt projekt**.
- Dra in ett anbud (PDF, Word .docx, Excel .xlsx eller CSV). Texten läses i webbläsaren.
- Tolkning: när sidan körs som Claude-artefakt läser Claude anbudet. Fristående används en regelbaserad tolkning som klarar tydliga tabeller.
- Granskning innan något sparas: osäkra fält markeras, och om ersättningsformen inte framgår måste du välja fast pris eller löpande räkning.
- Kontroll att summan av momenten stämmer med anbudets totalsumma.

Fristående sparas projekten i webbläsarens lokala lagring. I artefaktversionen sparas de på servern.

## Säkerhet och riktiga filer

- Repot ska vara **privat**. Det innehåller bara kod och påhittade exempel.
- `.gitignore` stoppar PDF, Word, Excel och CSV utanför `exempel/`, och allt i `privat/`. Lägg riktiga anbud och timrapporter där när du testar lokalt.
- Prototypen läser filen i webbläsaren. Bara texten skickas till Claude för tolkning, och bara de godkända projektuppgifterna sparas, inte filen.

## Utseende

Färgerna ligger som variabler överst i stilmallen och logotypen i `BRAND` i skriptet. Byt dem mot värdena från företagets varumärkesportal.

## Exempeldata

`exempel/` innehåller påhittade anbud:

- `Exempelanbud_Ekbackens_forskola.docx` / `.pdf` – fast arvode, 10 moment i 4 faser, reserv och á-pris.
- `Exempelanbud_Dagvatten_Norra_hamnen.xlsx` – otydlig ersättningsform, så verktyget frågar.

`skapa_exempel.py` genererar filerna på nytt.

## Teknik

Se [docs/teknikstack.md](docs/teknikstack.md).
