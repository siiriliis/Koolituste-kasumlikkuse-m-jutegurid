# BCS Koolituse müügitulu analüüs (ak/h)
Selle projekti eesmärk on analüüsida tegureid, mis mõjutavad koolituste müügitulu ühe akadeemilise tunni (ak/h) kohta.

Algne püstitus ja muudatus analüüsi fookuses:
Algselt oli eesmärgiks analüüsida koolituste üldist kasumlikkust. Töö käigus selgus aga, et olemasolevate andmete põhjal ei ole võimalik kulusid projektide vahel täpselt jaotada (kuna üldkulud ja -tulud on koondatud projekti "AZZ" alla).

Sellest tulenevalt on fookus seatud müügitulule akadeemilise tunni kohta, mis on antud andmekogumi puhul kõige täpsem mõõdik koolituste efektiivsuse hindamiseks.

## Ettevõtte tutvustus
Ettevõte pakub erinevaid koolitusi (nii avalikke kui ka sisekoolitusi), mis on jaotatud kategooriatesse (nt IT, kasutajakoolitused). Koolitusi viivad läbi erinevad koolitajad, kelle panus sisaldab lisaks aktiivsele koolitamisele ka ettevalmistusaega.

## Probleem
Projekti raames otsime vastuseid järgmistele küsimustele:

1) Müügitulu analüüs: Millised tegurid (osalejate arv, maht, kategooria, formaat, hooajalisus) omavad suurimat mõju müügitulule akadeemilise tunni kohta? Kes on edukaimad lektorid ja millised on tulusaimad koolitused?

2) Lektorite tööefektiivsus: Kuidas mõjutab lektorite ajakulu (ettevalmistus vs. õppetöö) nende keskmist AK tunnihinda? Kas ja kelle puhul on see suhe ajas oluliselt muutunud?

## Plan

Analüüsi keskne küsimus on koolitustegevuse efektiivsus. Kuna üldkulud on koondatud ühe projekti alla ("AZZ") ja neid ei ole võimalik olemasolevate andmete põhjal üksikute koolituste vahel täpselt jaotada, kasutame peamise mõõdikuna müügitulu akadeemilise tunni (ak/h) kohta (käive kokku jagatuna koolitusmahuga).

Lisaks analüüsime lektorite ajakasutust. See võimaldab meil mõõta lektori töötunni tootlikkust — kui palju tulu genereeritakse iga töötaja poolt panustatud tunni kohta. Kasutame peamise mõõdikuna Lektori ak/h müügitulu (käive kokku/lektori töö ja koolitustundide summa)


## Andmekaitse kirjeldus - mis alustel andmeid töödeldakse
Antud projektis on andmete töötlemisel lähtutud järgmistest põhimõtetest:

Andmete anonümiseerimine ja pseudonümiseerimine: Kõik isikuandmed (lektorite nimed, klientide nimed jm tuvastamist võimaldav info) on andmestikust eemaldatud või asendatud unikaalsete koodidega (nt "Koolitaja 14"). See välistab füüsiliste isikute tuvastamise analüüsi käigus.

Töötlemise eesmärk: Andmeid töödeldakse üksnes õppe- ja analüütilisel eesmärgil, et selgitada välja koolitusvaldkondade tulusus ja lektorite ajakasutuse efektiivsus.

## Andmed

### Ärisõnastik

| Mõiste    | Seletus                                                                       |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| Müügitulu ak/h kohta    | Arvutuslik väärtus: koolituse kogukäive jagatud akadeemiliste tundide arvuga.                                                                       |
| Lektori AK/h müügitulu  | Mõõdik, mis näitab, kui palju tulu toob üks lektori töötund (sh ettevalmistus).                                                                     |
| Kobarkoolitus           |  Koolitustüüp, mis koosneb mitmest moodulist (väli KasKobarkoolitus -True).                                                                         |
| Madalhooaeg             | Periood mai -august                                                                                                                                 |
| Kõrghooaeg              | Periood september - aprill                                                                                                                          |
| Koolitus                | Ühekordne õppesündmus või kursus, millel on konkreetne teema, toimumisaeg ja määratud lektor. Ärilises vaates on see peamine tulu genereeriv üksus. |
| Allahindlus             | Arvutuslik vahe standardse osalustasu ja tegelikult realiseerunud müügitulu vahel.                                                                  |
| Kobarkoolitus           | Mahukam koolitusprojekt, mis koosneb mitmest moodulist või korduvast koolitusest.                                                                   |
|                         |                                                                                                                                                     |

### Andmesõnastik
Andmesõnastik on leitav:....
(Näide andmesõnastikust)

### Andmeallikad
Analüüs põhineb viiel andmestikul, mis eksporditi ettevõtte infosüsteemidest (leitavad lingilt: https://github.com/siiriliis/Koolituste-kasumlikkuse-m-jutegurid/tree/main/algandmed):

koolitused.xlsx – Koolituste põhiandmed (CRM). 

EA.xlsx – Raamatupidamise üldkanded (ERP). 

EAT.xlsx – Raamatupidamise detailsed tehingud ja arved (ERP).

kulud või tulud.xlsx – Finantskannete klassifikaator (Excel).

Töö ja koolitustunnid.xlsx – Koolitajate tööaja logid (Outlook kalender).

### Andmemudel - tee pildiks
Andmemudel järgib täht-skeemi (Star Schema) loogikat:

Faktitabelid: koolitused, Töö ja koolitustunnid ja EAT hoiavad arvulisi andmeid.

Dimensioonitabelid: Date, Kategooriad, Lektorid ja kulud või tulud on seotud faktitabelitega one-to-many (1:*) seoste kaudu.

Seosed: Kõik peamised filtrid (aeg, kategooria, lektor) liiguvad dimensioonitabelitest faktitabelitesse, võimaldades ristanalüüsi eri allikate vahel.

![Data-Model.jpg](jb-image:img_1778070882980_f4497082486a48)

### Andmevoog - tee pildiks

![data-lineage.drawio.png](jb-image:img_1778070698514_8b5ae5d6712d1)


## Analüüs
### Andmete puhastamine ja rikastamine
Andmete usaldusväärsuse tagamiseks viidi läbi järgmised puhastusprotsessid:

- Tühjade väärtuste eemaldamine: Välistasime andmestikust koolitused, mille müügitulu (Käive kokku) oli 0 või puudus (blank).

- Ajaperioodi piiramine: Analüüsis on kasutatud andmeid vahemikus 2024 kuni 31. märts 2026.

- Andmed algavad 2024. aastast, et tagada võrreldavus koolitused tabeliga.

- Andmed seisuga 01.04.2026 ja hiljem eemaldati, kuna tegemist oli tulevikuprognooside, mitte realiseerunud tehingutega.

- Projektide filtreerimine: Analüüsist jäeti välja projekt "AZZ". Kuna see sisaldas koondandmeid üldkulude ja -tulude kohta, mida ei saanud jagada konkreetsete koolituste vahel, oleks selle kaasamine moonutanud üksikute koolitusprojektide tulususe näitajaid.

Arvutuslikud väljad: 

Kuna algandmed ei sisaldanud otsest infot allahindluste kohta, lõime mudelisse arvutuslikud väljad Allahindlus ja Allahindlus %. See võimaldab analüüsida, kas suurem allahindlus toob kaasa suurema osalejate arvu ja kuidas see mõjutab lõppkokkuvõttes koolituse tunni tootlikkust.

### Andmete eksploratiivne analüüs

### Andmete statistiline analüüs

Andmete statistilise analüüsi käigus arvutasime välja keskmise müügitulu 1 AK tunni kohta, et võrrelda erinevate koolituskategooriate tulusust


## Andmelugu, järeldused
