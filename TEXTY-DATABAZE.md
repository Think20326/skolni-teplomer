# Databáze textů — Školní teploměr

Kompletní přehled všech uživatelsky viditelných textů v `index.html`.

Legenda:
- 🏫 **ŠKOLNÍ:** — verze pro školní den (`isSchoolDay === true`)
- 🏖️ **VOLNÝ DEN:** — verze pro víkend / svátek / prázdniny
- 🔄 **UNIVERZÁLNÍ:** — použije se vždy, bez ohledu na typ dne

---

## 1. OBLEČENÍ — chipy na kartách

Generováno funkcí `getClothing(temp, feels, code)`. Rozhoduje **pocitová teplota** (`feels`).

| Chip | Podmínka |
|------|----------|
| `Zimní bunda` | feels ≤ −10 |
| `Čepice` | feels ≤ −10 nebo feels ≤ −3 nebo (sněží a feels > −3) |
| `Rukavice` | feels ≤ −10 nebo feels ≤ −3 nebo (sněží a feels > −3) |
| `Šála` | feels ≤ −10 |
| `Teplá bunda` | feels ≤ −3 (bez čepice/rukavic nad −3) |
| `Bunda` | feels ≤ 9 |
| `Lehká bunda` | feels ≤ 14 |
| `Mikina` | feels ≤ 19 |
| `Tričko` | feels ≤ 26 |
| `Lehké oblečení` | feels > 26 |
| `Deštník` | kód počasí = déšť / přeháňky / mrholení / bouřka |

---

## 2. KVALITA OVZDUŠÍ — krátké chipy na kartách

Funkce `randAqiChip(level, schoolDay)`. Zobrazí se na každé kartě pokud jsou data AQI.

### AQI 0–20 (Vynikající)
🔄 UNIVERZÁLNÍ: `Vzduch jako křišťál. Ven s dětmi!`
🔄 UNIVERZÁLNÍ: `Parádní vzduch — hurá ven!`
🔄 UNIVERZÁLNÍ: `Dýchá se božsky. Plný plyn na hřiště!`
🔄 UNIVERZÁLNÍ: `Vzduch z hor. Dneska patří děti ven!`
🔄 UNIVERZÁLNÍ: `Bomba vzduch. Kdo je doma, prodělává!`
🔄 UNIVERZÁLNÍ: `Čistota vzduchu na jedničku. Ven!`

### AQI 21–40 (Dobrá)
🔄 UNIVERZÁLNÍ: `Čistý vzduch. Klidně ven!`
🔄 UNIVERZÁLNÍ: `Dýchá se fajn. Ven se to vyplatí!`
🔄 UNIVERZÁLNÍ: `Dobrý vzduch, dobrý den na hřiště`
🔄 UNIVERZÁLNÍ: `Vzduch v pohodě. Kolo, park, cokoliv.`
🔄 UNIVERZÁLNÍ: `Čistý vzduch, jasná volba — ven!`
🏫 ŠKOLNÍ: `Vzduch OK — fotbálek po škole bez obav`
🏖️ VOLNÝ DEN: `Vzduch OK — fotbálek venku bez obav`

### AQI 41–60 (Přijatelná)
🔄 UNIVERZÁLNÍ: `Ven jo, ale pohodovým tempem`
🔄 UNIVERZÁLNÍ: `Vzduch ujde. Sport klidně, ale bez přehánění.`
🔄 UNIVERZÁLNÍ: `Procházka fajn, maraton radši ne`
🔄 UNIVERZÁLNÍ: `Dá se dýchat. Jen to nepřežeňte.`
🔄 UNIVERZÁLNÍ: `Venku OK, ale na pohodu`
🔄 UNIVERZÁLNÍ: `Jde to, ale nešlapte na plyn`

### AQI 61–80 (Zhoršená)
🔄 UNIVERZÁLNÍ: `Vzduch zlobí. Zvolněte.`
🔄 UNIVERZÁLNÍ: `Dnes spíš dovnitř. Hřiště počká.`
🔄 UNIVERZÁLNÍ: `Raději klid. Vzduch není kamarád.`
🔄 UNIVERZÁLNÍ: `Procházka OK, běhání ne`
🔄 UNIVERZÁLNÍ: `Vzduch dnes nespolupracuje`
🔄 UNIVERZÁLNÍ: `Zvolněte. Venku to dnes nevoní.`

### AQI 81–100 (Špatná)
🔄 UNIVERZÁLNÍ: `Hřiště dnes ne. Plíce řekly stop.`
🔄 UNIVERZÁLNÍ: `Špatný vzduch. Sport jen uvnitř.`
🔄 UNIVERZÁLNÍ: `Dnes zůstaňte pod střechou`
🔄 UNIVERZÁLNÍ: `Venku to dnes nefunguje. Dovnitř!`
🔄 UNIVERZÁLNÍ: `Vzduch je ošklivý. Všechno dovnitř.`
🔄 UNIVERZÁLNÍ: `Stop pro venkovní aktivity`

### AQI 100+ (Kritická)
🔄 UNIVERZÁLNÍ: `STOP. Ven dnes ani krok.`
🔄 UNIVERZÁLNÍ: `Nedýchatelno. Zůstaňte doma.`
🔄 UNIVERZÁLNÍ: `Červený alarm. Dveře zavřít!`
🔄 UNIVERZÁLNÍ: `Nebezpečný vzduch. Žádné ven.`
🔄 UNIVERZÁLNÍ: `Nouzový režim. Zůstaňte uvnitř.`
🔄 UNIVERZÁLNÍ: `Toxický vzduch. Absolutní stop.`

---

## 3. KVALITA OVZDUŠÍ — delší motivační texty (dolní rámeček)

Funkce `randAqiMot(level, schoolDay)`. Jeden náhodný text v panelu pod kartami.

### AQI 0–20 (Vynikající)
🔄 UNIVERZÁLNÍ: `Vzduch jako v lese! Ideální čas na pořádný trénink nebo odpoledne s dětmi na hřišti.`
🔄 UNIVERZÁLNÍ: `Vzduch je dnes jako z hor. Ven s dětmi, ať si to užijí!`
🔄 UNIVERZÁLNÍ: `Parádní vzduch — kola, koloběžky, hřiště, dneska je to bez limitu`
🔄 UNIVERZÁLNÍ: `Lepší vzduch dnes nenajdete. Ideální den vyběhnout ven.`
🔄 UNIVERZÁLNÍ: `Plíce si dnes zazpívají. Tohle je den na hřiště od rána do večera.`
🔄 UNIVERZÁLNÍ: `Vzduch jak na horské louce. Škoda sedět doma, ven s tím!`
🔄 UNIVERZÁLNÍ: `Dneska se dýchá jako v pohádce. Kdo nesportuje, ten prohloupí.`

### AQI 21–40 (Dobrá)
🔄 UNIVERZÁLNÍ: `Vzduch je v pohodě — klidně naplánujte odpolední kroužek venku`
🔄 UNIVERZÁLNÍ: `Čistý vzduch, žádné starosti. Fotbal, kolo, park — cokoliv.`
🔄 UNIVERZÁLNÍ: `Vzduch drží parádně. Družina venku, kroužek venku, všechno venku.`
🔄 UNIVERZÁLNÍ: `Žádný smog, žádné starosti. Klidně vyražte na delší procházku.`
🏫 ŠKOLNÍ: `Skvělá zpráva: Vzduch je čistý. Ideální na cestu do školy pěšky nebo fotbálek po družině.`
🏖️ VOLNÝ DEN: `Skvělá zpráva: Vzduch je čistý. Ideální na výlet pěšky nebo fotbálek venku.`
🏫 ŠKOLNÍ: `Dneska se venku dýchá dobře. Škola pěšky? Jasně!`
🏖️ VOLNÝ DEN: `Dneska se venku dýchá dobře. Na procházku nebo výlet? Jasně!`
🏫 ŠKOLNÍ: `Dýchá se fajn. Kolo do školy je dneska sázka na jistotu.`
🏖️ VOLNÝ DEN: `Dýchá se fajn. Na kole to dnes bude sázka na jistotu.`

### AQI 41–60 (Přijatelná)
🔄 UNIVERZÁLNÍ: `Pořád je to fajn. Venkovní kroužky i hřiště jsou v pohodě, jen se dneska nikam nežeňte.`
🔄 UNIVERZÁLNÍ: `Ven jít můžete, ale maraton dnes neběžte. Procházka nebo lehký sport stačí.`
🔄 UNIVERZÁLNÍ: `Vzduch není špatný, ale ani skvělý. Kratší výběh jo, závody ne.`
🔄 UNIVERZÁLNÍ: `Venku to jde, jen to dneska nepřehánějte s tempem`
🔄 UNIVERZÁLNÍ: `Hřiště v pohodě, ale nechte závodění na jindy. Dneska pohodový režim.`
🔄 UNIVERZÁLNÍ: `Ven klidně, ale bez výkonů na maximum. Tělo vám poděkuje.`
🔄 UNIVERZÁLNÍ: `Vzduch je tak napůl. Procházka super, sprint raději ne.`

### AQI 61–80 (Zhoršená)
🔄 UNIVERZÁLNÍ: `Dnes raději zvolněte. Místo běhání po hřišti zkuste klidnější procházku nebo hraní doma.`
🔄 UNIVERZÁLNÍ: `Vzduch dnes zlobí. Kratší procházka OK, ale sport raději přesuňte dovnitř.`
🔄 UNIVERZÁLNÍ: `Hřiště počká. Dneska je lepší stavebnice než fotbal.`
🔄 UNIVERZÁLNÍ: `Astmatici a alergici pozor — dnes raději vnitřní aktivity`
🔄 UNIVERZÁLNÍ: `Venku to dnes moc nevoní. Přesuňte hry dovnitř, plíce ocení klid.`
🔄 UNIVERZÁLNÍ: `Dneska vzduch nespolupracuje. Zkuste deskové hry místo hřiště.`
🔄 UNIVERZÁLNÍ: `Běhání venku dnes škrtněte. Krátká procházka OK, ale nic víc.`

### AQI 81–100 (Špatná)
🔄 UNIVERZÁLNÍ: `Dneska to na hřiště není. Sport i divoké hry raději přesuňte dovnitř, plíce vám poděkují.`
🔄 UNIVERZÁLNÍ: `Špatný den pro plíce. Nechte děti hrát si doma, venku to dnes nestojí za to.`
🔄 UNIVERZÁLNÍ: `Vzduch je dnes ošklivý. Tělocvična, bazén, cokoliv pod střechou.`
🔄 UNIVERZÁLNÍ: `Venkovní aktivity dnes škrtněte. Plíce budou vděčné.`
🔄 UNIVERZÁLNÍ: `Hřiště dnes zavřete. Aspoň v hlavě. Lego, knihy, vnitřní bazén — cokoliv uvnitř.`
🔄 UNIVERZÁLNÍ: `Dneska je venku dýchací past. Všechny aktivity přesuňte pod střechu.`
🔄 UNIVERZÁLNÍ: `Sport venku? Dnes fakt ne. Dejte přednost kinu, muzeu nebo domácí olympiádě.`

### AQI 100+ (Kritická)
🔄 UNIVERZÁLNÍ: `Stopka pro venkovní aktivity. Děti nechte raději doma, venku je dnes opravdu nedýchatelno.`
🔄 UNIVERZÁLNÍ: `Červený alarm. Žádné venkovní aktivity — ani procházka. Zůstaňte uvnitř.`
🔄 UNIVERZÁLNÍ: `Dnes platí: dveře zavřít, okna zavřít, ven ani krok. Vzduch je nebezpečný.`
🔄 UNIVERZÁLNÍ: `Absolutní stop. Venku se dnes nedýchá, zůstaňte s dětmi uvnitř.`
🔄 UNIVERZÁLNÍ: `Dnes je venku opravdu zle. Žádné výjimky — děti zůstávají uvnitř.`
🔄 UNIVERZÁLNÍ: `Vzduch je dnes toxický. Ani krátká cesta ven. Zůstaňte doma.`
🔄 UNIVERZÁLNÍ: `Nouzový režim pro plíce. Venku dnes nic, opravdu nic.`

### Doplňkové poznámky k časování AQI (připojí se za motivační text)
Podmínka: ráno AQI ≥ 61, odpoledne < 60:
🔄 UNIVERZÁLNÍ: ` Odpoledne se to vybere — nechte si hřiště až na potom!`
Podmínka: ráno AQI < 60, odpoledne ≥ 61:
🔄 UNIVERZÁLNÍ: ` Ráno je vzduch nejlepší — využijte dopoledne na sport!`
Podmínka: ráno i odpoledne AQI ≥ 60:
🔄 UNIVERZÁLNÍ: ` Dnes to venku nebude celý den. Plánujte uvnitř.`

---

## 4. KVALITA OVZDUŠÍ — sport chipy

Jeden chip ve spodní části AQI panelu. Závisí na **maximálním** AQI ze všech 3 slotů.

| Chip | Podmínka | Styl |
|------|----------|------|
| `Sport venku bez obav` | maxAQI ≤ 40 | zelený |
| `Sport venku s opatrností` | maxAQI ≤ 60 | žlutý |
| `Raději sport dovnitř` | maxAQI ≤ 80 | červený |
| `Stop pro venkovní aktivity` | maxAQI > 80 | červený |

---

## 5. VÍTR — texty a tipy

Funkce `getTip()`, sekce vítr. Závisí na **maximální rychlosti větru** ze všech 3 slotů.

### Silný vítr ≥ 14 m/s (vždy vybere 1 náhodný)
🔄 UNIVERZÁLNÍ: `⚠️ Pozor, silné nárazy větru (X m/s) — dejte pozor na cestě!`
🔄 UNIVERZÁLNÍ: `⚠️ Vichřice — vyhněte se stromořadím a parkům!`
🔄 UNIVERZÁLNÍ: `⚠️ Silné poryvy — na kolo raději ne`
🔄 UNIVERZÁLNÍ: `⚠️ Pozor na padající větve a předměty!`
🔄 UNIVERZÁLNÍ: `⚠️ Nárazy větru X m/s — zajistěte zahradní nábytek!`

Přidají se do poolu pokud platí podmínka:
🔄 UNIVERZÁLNÍ: `⚠️ Extrémní vítr — zvažte, jestli musíte ven` *(maxWind > 18)*
🔄 UNIVERZÁLNÍ: `⚠️ Deštník nechte doma, uletěl by` *(prší)*
🔄 UNIVERZÁLNÍ: `⚠️ Slunečník raději ukliďte` *(slunečno, duben–říjen)*
🔄 UNIVERZÁLNÍ: `⚠️ Je markýza stažená?` *(slunečno, duben–říjen)*

### Mírně silný vítr ≥ 10 m/s
🔄 UNIVERZÁLNÍ: `Dnes si držte klobouky!`
🔄 UNIVERZÁLNÍ: `Silný vítr — zapněte bundu až pod bradu`
🔄 UNIVERZÁLNÍ: `Vynechte les, můžou padat větve`
🔄 UNIVERZÁLNÍ: `Bacha ať vás to nesfoukne z kola!`
🔄 UNIVERZÁLNÍ: `Fouká dost — sušení prádla venku bude rekordní!`
🔄 UNIVERZÁLNÍ: `Silný vítr — menší děti raději za ruku`
🔄 UNIVERZÁLNÍ: `Na draky dnes radši ne — vítr je moc silný`
🔄 UNIVERZÁLNÍ: `Na badminton venku to není`

### Lehký vítr ≥ 5 m/s
🔄 UNIVERZÁLNÍ: `Skvělý den na pouštění draků!`
🔄 UNIVERZÁLNÍ: `Budou dobře lítat draci!`
🔄 UNIVERZÁLNÍ: `Jděte pouštět draky!`
🔄 UNIVERZÁLNÍ: `Fouká — na kole vás to trochu osvěží`
🔄 UNIVERZÁLNÍ: `Vítr ve vlasech — nezapomeňte gumičku!`
🔄 UNIVERZÁLNÍ: `Fouká — kapuce bude lepší volba než čepice`
🔄 UNIVERZÁLNÍ: `Máš možnost vyrazit na plachetnici?`
🔄 UNIVERZÁLNÍ: `Vítr je tak akorát — skvělý na windsurfing nebo kite!`
🔄 UNIVERZÁLNÍ: `Bublifuk doletí až k sousedům!`

### Bezvětří < 5 m/s
🔄 UNIVERZÁLNÍ: `Bezvětří… frisbee?`
🔄 UNIVERZÁLNÍ: `Dnes vám vítr v zádech nepomůže, ale ani nepřekáží!`
🔄 UNIVERZÁLNÍ: `Klid, bezvětří - badminton půjde venku`
🔄 UNIVERZÁLNÍ: `Ani lístek se nehne — klidný den na piknik`
🔄 UNIVERZÁLNÍ: `Dnes to na pouštění draků určitě nebude`
🔄 UNIVERZÁLNÍ: `Bezvětří — svíčky na dortu venku nezhasnou!`
🔄 UNIVERZÁLNÍ: `Klidný den — ideální na malování venku`
🔄 UNIVERZÁLNÍ: `Vítr z hor to k vám dnes nestihne` *(maxWind ≤ 3)*

---

## 6. TIPY NA DNES / ZÍTRA — podmínkové texty

Funkce `getTip()`. Zobrazují se v panelu „Tipy na dnes" / „Tipy na zítra".

### Teplota ráno (pocitová)
🔄 UNIVERZÁLNÍ: `Ráno mráz — zimní bunda, čepice a rukavice` *(feels < 0)*
🔄 UNIVERZÁLNÍ: `Ráno bude chladno — čepice a teplá bunda` *(feels ≤ 5)*

### Rozdíl ráno vs. odpoledne
🔄 UNIVERZÁLNÍ: `Ráno X°C, odpoledne Y°C — ráno v bundě, odpoledne bude asi nacpaná v batohu` *(rozdíl ≥ 7°C)*
🔄 UNIVERZÁLNÍ: `Ráno příjemných X°C, ale odpoledne jen Y°C — přibalte bundu do batohu` *(rozdíl ≤ −7°C)*

### Déšť
🔄 UNIVERZÁLNÍ: `Pravděpodobnost deště X% — přibalte deštník nebo kapuci` *(maxPrecip > 50 %)*

### Sníh
🔄 UNIVERZÁLNÍ: `Sněží — rukavice a voděodolná obuv` *(kód = sněžení, feels ≥ 0)*

### UV záření
🔄 UNIVERZÁLNÍ: `UV index X — nezapomeňte opalovací krém a kšiltovku` *(maxUV > 5)*

### Mlha ráno
🔄 UNIVERZÁLNÍ: `Ráno mlha — oblečte reflexní vestu nebo aspoň pásky!` *(ranní viditelnost < 500 m)*

### Tma ráno
🔄 UNIVERZÁLNÍ: `Ráno je ještě tma — reflexní prvky!` *(východ slunce po 8:00)*

### Zhoršené ovzduší
🔄 UNIVERZÁLNÍ: `Zhoršená kvalita ovzduší — astmatici a alergici by měli omezit venkovní aktivity` *(maxAQI > 60)*

### Pyly — bříza / trávy / olše (zobrazí se pro každý typ zvlášť pokud ≥ 2/5)
Formát: `🌿 Bříza (X/5): [text]` — text se vybere náhodně z POLLEN_TEXTS dle úrovně.

#### Úroveň 2/5 (mírné pyly)
🔄 UNIVERZÁLNÍ: `Lehký pylový nádech ve vzduchu. Nic dramatického, ale citlivé nosy to poznají.`
🔄 UNIVERZÁLNÍ: `Pyly trochu poletují. Kapesník do kapsy!`
🔄 UNIVERZÁLNÍ: `Mírné pyly v ovzduší. Alergici, hlídáme vám to (:`
🔄 UNIVERZÁLNÍ: `Pyly se probouzí. Nic vážného, ale kdo ví, ten nosí kapesník.`
🔄 UNIVERZÁLNÍ: `Lehký pylový koktejl ve vzduchu. Většině lidí to nevadí, alergici to ucítí.`

#### Úroveň 3/5 (střední)
🔄 UNIVERZÁLNÍ: `Alergici, kapesníky s sebou!`
🔄 UNIVERZÁLNÍ: `Alergici, držte se! Pyly dnes létají.`
🔄 UNIVERZÁLNÍ: `Pyly v akci — alergici, nezapomeňte na léky!`
🔄 UNIVERZÁLNÍ: `Nos bude dnes pracovat přesčas. Léky s sebou!`
🔄 UNIVERZÁLNÍ: `Pyly se probudily. Antihistaminika do batohu!`
🔄 UNIVERZÁLNÍ: `Alergici, dnes to bude výzva. Připravte se!`

#### Úroveň 4/5 (silné)
🔄 UNIVERZÁLNÍ: `Alergici, dnes je to hustý. Léky jsou nutnost!`
🔄 UNIVERZÁLNÍ: `Pylová smršť! Kapky do očí a kapesníky povinně.`
🔄 UNIVERZÁLNÍ: `Dnes pyly nelítají — řádí. Alergici, vyzbrojte se!`
🔄 UNIVERZÁLNÍ: `Pylový mejdan venku. Léky, kapesníky, odhodlání.`
🔄 UNIVERZÁLNÍ: `Nos a oči budou protestovat. Léky jsou základ!`
🔄 UNIVERZÁLNÍ: `Pyly dnes jedou naplno. Bez léků ani krok ven!`

#### Úroveň 5/5 (extrémní)
🔄 UNIVERZÁLNÍ: `Pylová apokalypsa! Alergici, zvažte zůstat uvnitř.`
🔄 UNIVERZÁLNÍ: `Pyly na maximu. Kdo může, zůstane doma.`
🔄 UNIVERZÁLNÍ: `Dnes je venku pylové peklo. Alergici, radši dovnitř!`
🔄 UNIVERZÁLNÍ: `Rekordní pyly. Okna zavřít, léky vzít, ven jen nutně.`
🔄 UNIVERZÁLNÍ: `Pylový armagedon. Alergici, dnes je den na Netflix.`
🔄 UNIVERZÁLNÍ: `Pyly šílí. Bez léků a roušky ani na zahradu!`

---

## 7. POPISKY KARET — školní den vs. volný den

Funkce `getSlotMeta(schoolDay)`. Tři karty = ráno, poledne, odpoledne.

### Nadpis slotu (card-lbl) — stejný pro oba typy dne
- `Ráno`
- `Poledne`
- `Odpoledne`

### Podtitulek slotu (card-desc)
| Slot | 🏫 ŠKOLNÍ | 🏖️ VOLNÝ DEN |
|------|-----------|--------------|
| Ráno | `Cesta DO školy` | `Ranní výprava` |
| Poledne | `Přestávka` | `Oběd` |
| Odpoledne | `Cesta ZE školy` | `Odpolední výlet` |

### Dynamické chipy na kartách (vždy zobrazeny)
- `⚠️ Vítr X m/s` *(wind ≥ 14 m/s, červený chip)*
- `Vítr X m/s` *(wind 5–13 m/s, modrý chip)*
- `Déšť X%` *(precip > 30 %)*
- `UV X` *(uv > 3)*
- `Pocitově X°C` *(pod teplotou, vždy)*

### Popis počasí (card-wx-text) — funkce `weatherText()`
`Jasno` · `Převážně jasno` · `Polojasno` · `Zataženo` · `Mlha` · `Mrholení` · `Mrznoucí déšť` · `Déšť` · `Sněžení` · `Přeháňky` · `Sněhové přeháňky` · `Bouřka` · `Bouřka s krupobitím`

### Popis AQI v panelu (labely)
`Vynikající` · `Dobrá` · `Přijatelná` · `Zhoršená` · `Špatná` · `Kritická`

### Pyly v AQI panelu (vždy zobrazeny pokud jsou data)
`🌿 Bříza X/5 · Trávy X/5 · Olše X/5`

---

## 8. PODTITULEK — pod datem v záhlaví

Element `#hdr-subtitle`, aktualizuje se při každém přepnutí tabu.

🏫 ŠKOLNÍ: `Teplota pro cestu do školy a ze školy`
🏖️ VOLNÝ DEN: `Počasí na celý den`

---

## 9. PEVNÉ TEXTY — hlavička, patička, modal, bannery

### Záhlaví
- `Načítám…` — placeholder lokace při startu
- `Zjišťuji polohu…` — během geolokace
- `Vaše poloha` — fallback pokud reverzní geokódování selže
- `Název města…` — placeholder v inputu pro hledání
- `Hledat` — tlačítko formuláře
- `Město nenalezeno, zkuste jiný název.` — chyba hledání

### Taxy
- `Dnes` / `Zítra` — popisky tabů

### Datum pod tabem
- Formát: `sobota 4. dubna` (generuje `formatDate()`)

### Název státního svátku (`#hdr-holiday`)
- Zobrazí se pod datem pokud je státní svátek (viz sekce 10)
- Skryto pokud není svátek

### Panel tipů
- `📋 Tipy na dnes` / `📋 Tipy na zítra` — nadpis panelu

### Načítání a chyby
- `Načítám předpověď počasí…` — spinner text
- `⚠️ Nepodařilo se načíst počasí.` — chybová zpráva
- `🔄 Zkusit znovu` — tlačítko retry
- `Aktualizováno: HH:MM` — patička

### Nastavení časů (modal)
- `⏰ Nastavit časy` — titulek modalu
- `🌅 Ráno` — label
- `☀️ Poledne` — label
- `🌆 Odpoledne` — label
- `Časy musí být v rostoucím pořadí.` — validační chyba
- `Zrušit` — tlačítko
- `Uložit` — tlačítko

### Patička
- `Data: Open-Meteo` — odkaz na zdroj dat
- `Sledujte nás pro tipy a novinky` — social text

### PWA install banner
- `📱 Tip: Mějte Školní teploměr jako appku na ploše!` — titulek
- iOS: `Klikněte na [sdílet] (sdílení dole) → „Přidat na plochu"` — instrukce
- Android: `Klikněte na [⋮] → (Více →) „Přidat na plochu"` — instrukce
- `Pak stačí kliknout na nejhezčí ikonku T a je to 😊` — patička banneru

---

## 10. SVÁTKY — názvy zobrazované pod datem

Funkce `getCzechHoliday(date)`. Zobrazí se v `#hdr-holiday` pokud platí datum.

| Datum | Název |
|-------|-------|
| 1. 1. | `Nový rok` |
| Pohyblivý (pátek před Velikonocemi) | `Velký pátek` |
| Pohyblivý (pondělí po Velikonocích) | `Velikonoční pondělí` |
| 1. 5. | `Svátek práce` |
| 8. 5. | `Den vítězství` |
| 5. 7. | `Den slovanských věrozvěstů Cyrila a Metoděje` |
| 6. 7. | `Den upálení mistra Jana Husa` |
| 28. 9. | `Den české státnosti` |
| 28. 10. | `Den vzniku samostatného československého státu` |
| 17. 11. | `Den boje za svobodu a demokracii` |
| 24. 12. | `Štědrý den` |
| 25. 12. | `1. svátek vánoční` |
| 26. 12. | `2. svátek vánoční` |

---

*Soubor vygenerován z `index.html`. Při změně textů v kódu je třeba aktualizovat i tento soubor.*
