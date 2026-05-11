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

| Mõiste                    	| Selgitus                                                                                                                      	|
|---------------------------	|-------------------------------------------------------------------------------------------------------------------------------	|
| Müügitulu AK/h kohta      	| Koolituste müügitulu jagatud koolituste akadeemiliste tundide arvuga.                                                         	|
| Koolitaja AK/h müügitulu  	| Koolituse müügitulu jagatud koolitaja logitud töötundidega                                                                    	|
| Madalhooaeg               	| Periood jaanuar, mai-juuli                                                                                                    	|
| Kõrghooaeg                	| Periood august-detsember, veebruar-aprill                                                                                     	|
| Koolitus                  	| Õppesündmus või kursus, millel on konkreetne teema, toimumisaeg ja määratud lektor.                                           	|
| Allahindlus               	| Väärtus protsentides, algselt määratud kohamaksumuse ja tegelikult realiseerunud müügitulu suhe.                              	|
| Koolitaja                 	| Inimene, kes viib läbi koolitust.                                                                                             	|
| Töö kategooria            	| Koolitaja töötundide jagunemine: koolitustunnid ehk koolituse läbiviimiselele kulunud tunnid, töötunnid ehk ettevalmistusaeg. 	|
| Koolituse kategooria      	| Koolituste jagunemist iseloomustav lühend (SPE, KAS, PRO, DEV jne)                                                            	|
| Koolitaja kategooria      	| Oma koolitaja (koolitusettevõtte põhikohaga töötaja) või külaliskoolitaja(lepinguline partner)                                	|
| Koolitustundide osakaal   	| Koolitustundide osakaal kogu tundidest (ettevalmistus + koolitus)                                                             	|

### Andmesõnastik

| Mõiste                    	| Selgitus                                                                                                                      	|
|---------------------------	|-------------------------------------------------------------------------------------------------------------------------------	|
| Müügitulu AK/h kohta      	| Koolituste müügitulu jagatud koolituste akadeemiliste tundide arvuga.                                                         	|
| Koolitaja AK/h müügitulu  	| Koolituse müügitulu jagatud koolitaja logitud töötundidega                                                                    	|
| Madalhooaeg               	| Periood jaanuar, mai-juuli                                                                                                    	|
| Kõrghooaeg                	| Periood august-detsember, veebruar-aprill                                                                                     	|
| Koolitus                  	| Õppesündmus või kursus, millel on konkreetne teema, toimumisaeg ja määratud lektor.                                           	|
| Allahindlus               	| Väärtus protsentides, algselt määratud kohamaksumuse ja tegelikult realiseerunud müügitulu suhe.                              	|
| Koolitaja                 	| Inimene, kes viib läbi koolitust.                                                                                             	|
| Töö kategooria            	| Koolitaja töötundide jagunemine: koolitustunnid ehk koolituse läbiviimiselele kulunud tunnid, töötunnid ehk ettevalmistusaeg. 	|
| Koolituse kategooria      	| Koolituste jagunemist iseloomustav lühend (SPE, KAS, PRO, DEV jne)                                                            	|
| Koolitaja kategooria      	| Oma koolitaja (koolitusettevõtte põhikohaga töötaja) või külaliskoolitaja(lepinguline partner)                                	|
| Koolitustundide osakaal   	| Koolitustundide osakaal kogu tundidest (ettevalmistus + koolitus)                                                             	|

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

<img width="927" height="760" alt="Data Model" src="https://github.com/user-attachments/assets/34072a20-4baf-4ad6-80e2-c80f01250437" />


### Andmevoog - tee pildiks

<img width="321" height="301" alt="data lineage drawio" src="https://github.com/user-attachments/assets/bc4865f5-839e-4b89-b779-ffd0f474d0b2" />


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
