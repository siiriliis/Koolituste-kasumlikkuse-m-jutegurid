# BCS Koolituse müügitulu analüüs

## Ettevõtte  ja probleemi tutvustus
Ettevõte pakub digioskuste koolitusi (nii avalikke kui ka grupikoolitusi ettevõtetele ja asutustele), mis on jaotatud sihtgrupipõhistesse kategooriatesse. Koolitusi viivad läbi nii ettevõtte enda palgal olevad koolitajad, kui ka külaliskoolitajad.

Algselt oli eesmärgiks analüüsida koolituste omadusi, mis mõjutavad kasumlikkust. Töö käigus selgus aga, et olemasolevate andmete põhjal ei ole võimalik kulusid projektide vahel täpselt jaotada (kuna üldkulud ja -tulud on koondatud kategooria "AZZ" alla). Seetõttu otsustasime analüüsida tegureid, mis mõjutavad koolituste müügitulu.

Leidsime, et analüüsi fookus võiks olla seatud akadeemilise tunni müügitulu uurimisele, sest eeldame, et kulu 1 AK/h ettevalmistamiseks ja läbiviimiseks on sarnane.

## Uurimisplaan
Analüüsi raames otsime vastuseid koolitustegevuse tulususele läbi järgmistele küsimuste:

1) Millised tegurid (osalejate arv, maht, kategooria, tüüp, hooajalisus jne) omavad mõju müügitulule? Võtame kasutusele mõõdikud: müügitulu AK/h kohta (müügitulu jagatuna koolitusmahuga) ja koolitaja AK/h müügitulu (müügitulu jagatuna koolitaja töö- ja koolitustundidega). Toome välja edukaimad koolitajad ja suurima müügituluga koolitused.
2) Kuidas mõjutavad ettevõtte enda koolitajate logitud töötunnid (ettevalmistus vs. õppetöö) nende keskmist AK tunnihinda? Kas ja kelle puhul on see suhe ajas oluliselt muutunud?

## Andmekaitse kirjeldus - mis alustel andmeid töödeldakse
Antud projektis on andmete töötlemisel lähtutud järgmistest põhimõtetest:

Andmete anonümiseerimine: kõik isikuandmed (koolitajate nimed, klientide nimed jm tuvastamist võimaldav info) on andmestikust eemaldatud või asendatud unikaalsete koodidega (nt "Koolitaja 14").

Töötlemise eesmärk: Andmeid töödeldakse üksnes õppe- ja analüütilisel eesmärgil.

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
| KAS                        	| Kasutajakoolitused                                                                                                             	|
| PRO                        	| Suured projektid                                                                                                               	|
| SPE                        	| Spetsialistikoolitused                                                                                                        	|
| DEV                       	| Juhikoolitused                                                                                                                 	|

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
Analüüs põhineb neljal andmetabelil, mis eksporditi ettevõtte infosüsteemidest (leitavad lingilt: https://github.com/siiriliis/Koolituste-kasumlikkuse-m-jutegurid/tree/main/algandmed):

koolitused.xlsx – Koolituste põhiandmed (CRM). 

EAT.xlsx – Raamatupidamise detailsed tehingud ja arved (ERP).

kulud või tulud.xlsx – Finantskannete klassifikaator (Excel).

Töö ja koolitustunnid.xlsx – Koolitajate tööaja logid (Outlook kalender).

### Andmemudel 
Andmemudel järgib täht-skeemi (Star Schema) loogikat:

Faktitabelid: koolitused, Töö ja koolitustunnid ja EAT hoiavad arvulisi andmeid.

Dimensioonitabelid: Date, Kategooriad, Lektorid ja kulud või tulud on seotud faktitabelitega one-to-many (1:*) seoste kaudu.

Seosed: Kõik peamised filtrid (aeg, kategooria, lektor) liiguvad dimensioonitabelitest faktitabelitesse, võimaldades ristanalüüsi eri allikate vahel.

<img width="1057" height="798" alt="Screenshot 2026-05-11 150916" src="https://github.com/user-attachments/assets/8959ed6b-9f2a-4e70-8409-37b9bf304945" />



### Andmevoog 

<img width="321" height="301" alt="data lineage drawio" src="https://github.com/user-attachments/assets/bc4865f5-839e-4b89-b779-ffd0f474d0b2" />


## Andmete puhastamine ja rikastamine
Andmete usaldusväärsuse tagamiseks viidi läbi järgmised puhastusprotsessid:

- Tühjade väärtuste eemaldamine: Välistasime andmestikust koolitused, mille müügitulu (Käive kokku) oli 0 või puudus (blank).

- Ajaperioodi piiramine: Analüüsis on kasutatud andmeid vahemikus 2024 kuni 31. märts 2026.

- Andmed algavad 2024. aastast, et tagada võrreldavus koolitused tabeliga.

- Andmed seisuga 01.04.2026 ja hiljem eemaldati, kuna tegemist oli tulevikuprognooside, mitte realiseerunud tehingutega.

- Projektide filtreerimine: Analüüsist jäeti välja projekt "AZZ". Kuna see sisaldas koondandmeid üldkulude ja -tulude kohta, mida ei saanud jagada konkreetsete koolituste vahel, oleks selle kaasamine moonutanud üksikute koolitusprojektide tulususe näitajaid.

Arvutuslikud väljad: 

Kuna algandmed ei sisaldanud otsest infot allahindluste kohta, lõime mudelisse arvutuslikud väljad Allahindlus ja Allahindlus %. See võimaldab analüüsida, kas suurem allahindlus toob kaasa suurema osalejate arvu ja kuidas see mõjutab lõppkokkuvõttes koolituse tunni tootlikkust.

## Andmete eksploratiivne analüüs

## Andmete statistiline analüüs

Andmete statistilise analüüsi käigus arvutasime välja keskmise müügitulu 1 AK tunni kohta, et võrrelda erinevate koolituskategooriate tulusust.



## Andmelugu, järeldused
Regressioonianalüüsist selgus, et kohamaksumus ega allahindlus ei mõjuta osalejate arvu. 
Sisekoolituse müügitulu AK/h kohta on suurem kui avalikel koolitustel. Kategooriates on AK/h müügitulu kõige suurem kategoorias DEV ja kõige madalam PRO.
