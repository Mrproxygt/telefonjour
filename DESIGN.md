# DESIGN.md — telefonjour.se

Målfras: **"telefonjour företag"** + longtail ("telefonjour hantverkare", "telefonjour fastighetsskötsel", "jourtelefon företag pris"). Undvik att tävla om ensamma "telefonjour" — den SERPen äger kristelefon/arbetsrätt. Vinkel: jour/efter-stängning, svar dygnet runt utan jourbemanning.

## 1. Brand-identitet

- **Bakgrund** `#0d1220` (natt-navy), **panel** `#141b2e`, **linje** `#243050`
- **Text** `#e8ecf6` (ink), sekundär `#94a0b8` (ink2)
- **Accent** `#f59e0b` (amber) / hover `#fbbf24` (amber2) — enda färgaccent, används sparsamt (kicker, CTA, siffror, ikonstreck)
- Lägg till **success/akut-röd** `#ef4444` diskret för akut-badge i "Så funkar det" (finns inte idag — nytt)
- Typografi: `"Segoe UI", system-ui, sans-serif` för brödtext/UI (behålls). Rubriker samma stack men `font-weight:800`, `letter-spacing:-0.02em`, clamp(34px,5.5vw,56px) för H1. Georgia/serif används INTE — night/tech-ton kräver ren sans, inte varm serif (skiljer sig medvetet från Menodi-huvudsajtens warm-editorial-look).
- Ton: saklig, kort, "vi vet att telefonen ringer när ingen är där" — inga utropstecken, inga superlativ utan siffra bredvid.

## 2. Sektionsplan (uppifrån-ner)

1. **Sticky header** — halvtransparent (`background:rgba(13,18,32,.72);backdrop-filter:blur(8px)`), logo + 2 ankare ("Så funkar det", "Pris") + CTA-knapp inbyggd i navet (ny — saknas idag)
2. **Hero** — kicker "Öppet fast ni har stängt", H1 med företagsvinkel ("Telefonjour för företag — svar dygnet runt, utan jourpersonal"), subline, primär CTA ("Hör AI-jouren svara") + sekundär ("Se hur det funkar", scrollar ned), 2-3 trust-chips (t.ex. "Svensk AI", "Live på under en vecka", "Ingen bindningstid" — verifiera innan publicering)
3. **Problemagitation** — kort stycke: vad kostar ett missat kvällssamtal/akutärende, FÖRE funktionerna (mönster från Skaala/Telavox)
4. **"Ett dygn med AI-jour"** — behålls, blir feature-grid-variant: 4 klock-kort med inline-SVG-ikon per kort (klocka/skiftnyckel/kalender/sms) istället för bara siffra
5. **"Så funkar det"** — NY sektion, numrerade 01/02/03 (Samtalet kommer in → AI bedömer akut/rutin → Bokar, larmar eller sammanfattar)
6. **Jämförelsetabell** — behålls (bemannad jour vs AI-jour), lägg highlight-rad på AI-jour-kolumnen (amber-kantad)
7. **Stats-band** — NY, men ENDAST siffror vi kan källbelägga (t.ex. svarstid, antal branscher) med källrad under bandet; annars utelämna hellre än gissa
8. **"Vem behöver telefonjour"** — behålls, görs om till 4 klickbara branschkort (hantverkare, begravningsbyrå, veterinär/klinik, flytt/verkstad)
9. **FAQ accordion** — behålls som details/summary, styling uppgraderad (chevron-ikon, hover, öppen-state med amber-kant)
10. **Stor avslutande CTA-band** — behålls, gradient-panel
11. **Flerkolumnsfooter** — NY struktur: Produkt / Branscher / Om telefonjour / Menodi-länk, ersätter dagens enradsfooter

## 3. Behålls från nuvarande sida

- Hela "Ett dygn med AI-jour"-konceptet (23:04/06:45/12:30/Lördag) — stark, konkret, byggs bara om till kort-med-ikon
- Jämförelsetabellen bemannad vs AI-jour, inkl. "lagkrav på bemannad jour"-brasklappen (viktig juridisk hedge, ta INTE bort)
- Alla tre FAQ-svar ordagrant (redan sakliga, juli 2026-daterade uppskattningar med reservation)
- CTA-copy och UTM-struktur (`utm_source=telefonjour&utm_medium=satellite&utm_campaign=...`) mot menodi.se
- FAQPage JSON-LD — behålls, uppdatera bara om FAQ-text ändras
- Ingen kalkylator-JS finns i nuvarande version — inget att portera

## 4. Mockup-bildplan (placeholders)

- Hero, till höger om rubrik/CTA: telefonmockup/skärmdump av SMS-larm kl 23:04 (`<!-- MOCKUP: hero-sms-larm.png 480×600 -->`)
- I "Så funkar det", steg 2: mini-skärmdump av bedömningslogik/dashboard (`<!-- MOCKUP: steg2-dashboard.png 400×300 -->`)
- Branschkort: 4× ikon-placeholder (inline SVG räcker, inga foton krävs)
- Stats-band: ingen bild, ren typografi

## 5. Differentiering mot de 10 andra satelliterna

- Enda satelliten med **mörkt tema** (natt/jour-vinkel motiverar det visuellt — de andra ligger ljust/warm-editorial)
- Vinkel är **tidpunkt** (efter stängning) inte funktion (svarstjänst) eller pris (kostnad) eller kanal (växel) —ägs inte av `svarstjanster.se`, `telefonpassningpris.se`, `telefonvaxelforetag.se`
- Akutlarm/SMS-vidarekoppling är unikt fokus här — ingen av de andra siktar på "akut kontra rutin"-bedömning
- "Dygnsklocka"-formatet (tidsstämplade scenarier) är en visuell/informationsarkitektur ingen annan satellit använder
