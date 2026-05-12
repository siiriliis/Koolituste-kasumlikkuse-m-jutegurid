# Koolitusettevõtte müügitulu analüüs

## Ettevõtte  ja probleemi tutvustus
Ettevõte pakub digioskuste koolitusi (nii avalikke kui ka grupikoolitusi ettevõtetele ja asutustele), mis on jaotatud sihtgrupipõhistesse kategooriatesse. Koolitusi viivad läbi nii ettevõtte enda palgal olevad koolitajad kui ka külaliskoolitajad.
Algselt oli eesmärgiks analüüsida koolituste omadusi, mis mõjutavad kasumlikkust. Töö käigus selgus aga, et olemasolevate andmete põhjal ei ole võimalik kulusid projektide vahel täpselt jaotada (kuna üldkulud ja -tulud on koondatud eraldi kategooria alla ning neid ei ole võimalik jagada teiste kategooriate vahel). Seetõttu otsustasime analüüsida neid tegureid, mis mõjutavad koolituste müügitulu.
Leidsime, et analüüsi fookus võiks olla seatud akadeemilise tunni müügitulu uurimisele, sest eeldame, et kulu ühe AK/h ettevalmistamiseks ja läbiviimiseks on sarnane.


## Uurimisplaan
Analüüsi raames uurime koolitustegevuse tasuvust järgmiste küsimuste kaudu:

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
| Müügitulu AK/h kohta      	| Koolituste müügitulu jagatud koolituste akadeemiliste tundide arvuga                                                           	|
| Koolitaja AK/h müügitulu  	| Koolituse müügitulu jagatud koolitaja logitud töötundidega                                                                    	|
| Madalhooaeg               	| Jaanuar, mai-juuli                                                                                                            	|
| Kõrghooaeg                	| August-detsember, veebruar-aprill                                                                                             	|
| Koolitus                  	| Õppesündmus või kursus, millel on konkreetne teema, toimumisaeg ja määratud lektor                                             	|
| Allahindlus               	| Väärtus protsentides, algselt määratud kohamaksumuse ja tegelikult realiseerunud müügitulu suhe                               	|
| Koolitaja                 	| Inimene, kes viib koolitust läbi                                                                                               	|
| Töö kategooria            	| Koolitaja töötundide jagunemine: koolitustunnid ehk koolituse läbiviimiselele kulunud tunnid, töötunnid ehk ettevalmistusaeg. 	|
| Koolituse kategooria      	| Koolituste jagunemist iseloomustav lühend (SPE, KAS, PRO, DEV jne)                                                            	|
| Koolitaja kategooria      	| Oma koolitaja (koolitusettevõtte põhikohaga töötaja) või külaliskoolitaja(lepinguline partner)                                	|
| Koolitustundide osakaal   	| Koolitustundide osakaal kogu tundidest (ettevalmistus + koolitus)                                                             	|
| KAS                        	| Kasutajakoolitused                                                                                                             	|
| PRO                        	| Suured projektid                                                                                                               	|
| SPE                        	| Spetsialistikoolitused                                                                                                        	|
| DEV                       	| Juhikoolitused                                                                                                                 	|

### Andmesõnastik

| Tabel                 	| Allika veeru nimi 	| Lõplik veeru nimi  	| Tüüp           	| Kirjeldus                                                                                    	|
|-----------------------	|-------------------	|--------------------	|----------------	|----------------------------------------------------------------------------------------------	|
| kulud või tulud       	| kulud_tulud_id    	| kulud_tulud_id     	| VARCHAR(100)   	| Kulu/Tulu alamliigi unikaalne ID                                                             	|
| kulud või tulud       	| kulud_tulud_2     	| kulud_tulud_2      	| VARCHAR(100)   	| Kulude/tulude alamliikideks jagamine                                                         	|
| kulud või tulud       	| kulud_tulud_1     	| kulud_tulud_1      	| VARCHAR(100)   	| Kategoriseerimine kuludeks/tuludeks                                                          	|
| Töö ja koolitustunnid 	| Lektor            	| Koolitaja          	| VARCHAR(100)   	| Koolitaja anonüümne kood (tekst + nr)                                                        	|
| Töö ja koolitustunnid 	| Start             	| Start              	| DATE           	| Koolituse alguskuupäev (PP.KK.AAAA)                                                          	|
| Töö ja koolitustunnid 	| AK tunnid         	| AK tunnid          	| DECIMAL (6, 2) 	| Logitud töötundide kestus (akadeemilistes tundides)                                          	| 
| koolitused            	| Title             	| Koolituste nimetus 	| VARCHAR(100)   	| Koolituse nimetus                                                                            	|
| koolitused            	| Koolitaja         	| Koolitaja          	| VARCHAR(20)    	| Koolitaja anonüümne kood (tekst + nr)                                                        	|
| koolitused            	| KohaMaksumus      	| Kohamaksumus       	| DECIMAL(6, 2)  	| Alghind ühele osalejale (2 komakohaga)                                                       	|
| koolitused            	| KoolituseMahtAK   	| Koolituse maht     	| DECIMAL(4, 1)  	| Koolituse maht (akadeemiliste tundidena - 45min, 1 komakohaga)                               	|
| koolitused            	| Id                	| Id                 	| INTEGER        	| Koolituse toimumise unikaalne kood                                                           	|
| koolitused            	| ContentType       	| Tüüp               	| VARCHAR(15)    	| Koolituse tüüp: "avalik", "sise"                                                             	|
| koolitused            	| Käive kokku       	| Müügitulu          	| DECIMAL(5, 0)  	| Koolituse müügitulu                                                                          	|
| koolitused            	| Osalejaid kokku   	| Osalejate arv      	| INTEGER        	| Koolituse osalejate arv kokku                                                                	|
| EAT                   	| Summa             	| Summa              	| DECIMAL(12,2)  	| Tegelikud kulud ja tulud                                                                     	|
| EAT                   	| kulud_tulud_ID    	| kulud_tulud_ID     	| VARCHAR(20)    	| Välisvõti, mis seob tehingu klassifikaatorite tabeliga                                       	|
| EAT                   	| avalik või sise   	| avalik või sise    	| VARCHAR(50)    	| Määrab, kas tehing on seotud avaliku koolituse või ettevõttetele suunatud (B2B) koolitusega. 	|

### Andmeallikad
Analüüs põhineb neljal andmetabelil, mis eksporditi ettevõtte infosüsteemidest (leitavad lingilt: https://github.com/siiriliis/Koolituste-kasumlikkuse-m-jutegurid/tree/main/algandmed):

koolitused.xlsx – koolituste põhiandmed (CRM). 

EAT.xlsx – raamatupidamise detailsed tehingud ja arved (ERP).

kulud või tulud.xlsx – finantskannete klassifikaator (Excel).

Töö ja koolitustunnid.xlsx – koolitajate tööaja logid (Outlook kalender).

### Andmemudel 
Andmemudel järgib täht-skeemi (Star Schema) loogikat:

- Faktitabelid: "Koolitused", "Töö ja koolitustunnid" ning "EAT" hoiavad arvulisi andmeid.

-	Dimensioonitabelid: „Date“, „Kategooriad“, „Koolitajad“ ja „Kulud või tulud“ on seotud faktitabelitega one-to-many (1:*) seoste kaudu..

- Seosed: kõik peamised filtrid (aeg, kategooria, lektor) liiguvad dimensioonitabelitest faktitabelitesse, võimaldades ristanalüüsi eri allikate vahel.

<img width="663" height="566" alt="image" src="https://github.com/user-attachments/assets/9ac9ffbb-a75f-4d2d-8644-1a95486dbf79" />


### Andmevoog 

<img width="577" height="338" alt="andmevoog" src="https://github.com/user-attachments/assets/0c65d915-8148-4ad0-88ec-42dcf3cb80d7" />


### Andmete puhastamine ja rikastamine
Andmete usaldusväärsuse tagamiseks viidi läbi järgmised puhastusprotsessid:
Eemaldasime: 
- müügitulu (Käive kokku) = 0 või tühi
- koolitusemaht ≤ 0

Analüüsitud periood 01.01.2024- 31.03.2026
- Andmed algavad 2024. aastast, et tagada võrreldavus koolitused tabeliga.
- Andmed seisuga 01.04.2026 ja hiljem eemaldati, kuna tegemist oli tulevikuprognooside, mitte realiseerunud tehingutega.

Projektide filtreerimine: 
- Analüüsist jäeti välja projekt "AZZ". Kuna see sisaldas koondandmeid üldkulude ja -tulude kohta, mida ei saanud jagada konkreetsete koolituste vahel, oleks selle kaasamine moonutanud üksikute koolitusprojektide tulususe näitajaid.

Arvutuslikud väljad: 
- Allahindlus ja Allahindlus %
- Kulud, tulud, kasum
- Müügitulu 1 osaleja kohta / Keskmine müügitulu 1 osaleja kohta (Avalik)
- Müügitulu AK/h kohta / Keskmine müügitulu AK/h kohta
- Koolitaja AK/h müügitulu
- Koolitustundide osakaal

## Andmete eksploratiivne analüüs

Andmete esmase uurimise käigus analüüsisime müügitulu kategooriate, koolitajate, hooajalisuse ja koolituse tüübi lõikes Power BI dashboardide abil.

Ilmnesid järgmised mustrid: 
- sisekoolitus toodab kõrgemat tunnihinda kui avalik koolitus, 
- kõrghooajal on käive kursuse kohta suurem kui madalhooajal, 
- DEV kategooria paistab silma kõrgeima tunnihinnaga ning 
- KAS kategoorias on allahindluse protsent teistest kategooriatest märkimisväärselt kõrgem. 
- Koolitajate vahel ilmnes suur erinevus nii tundide arvus kui koolitustundide osakaalus kogu tööajast.

## Andmete statistiline analüüs

Statistilise analüüsi eesmärk oli kontrollida, kas eksploratiivses analüüsis tuvastatud mustrid on statistiliselt usaldusväärsed. 

Kasutasime lineaarset regressiooni (OLS).

Regressioonanalüüs näitas, et kohamaksumus ei mõjuta statistiliselt oluliselt osalejate arvu üheski kategoorias ega aastas. 

Samuti analüüsisime kohamaksumuse ja koolituse mahu vahelist seost — pikematel koolitustel on kõrgem alghind osalejale, eriti SPE kategoorias. 

Allahindluse ja osalejate arvu vaheline regressioon näitas, et allahindlus ei mõjuta osalejate arvu — suurem allahindlus ei too rohkem osalejaid.


## Järeldused

- Regressioonianalüüsis selgus, et kohamaksumusel puudub mõju osalejate arvule. Samuti ilmnes mõju puudumine ka allahindluste korral.
- Koolituse tüüpidest, osutus müügitulu AK/h kohta kõige kõrgemaks sisekoolitustel. 
- Kategooriate lõikes osutus (müügitulu AK/h kohta) kõige tulusamaks juhikoolitused ehk DEV kategooria, mida mõjutas positiivselt väiksem allahindluse protsent ja väiksem koolituse maht,
- Kõige vähem tulusamaks osutus projektide (PRO) kategooria, mille kõrge koolituse maht kahandab selle müügitulu. 
- Hooajalisuse analüüs näitas erinevust keskmise müügitulu AK/h kohta kõrg- ja madalhooaja vahel DEV kategoorias — seda tasub ettevõttel edasi uurida. 
- Koolitajate vahel esineb suur varieeruvus müügitulus AK/h kohta — kõrgeim ja madalaim erinevad kümnekordselt.
- Koolitajad, kellel on suurem koolitustundide osakaal kogu logitud tööajast, toodavad üldjuhul kõrgemat müügitulu AK/h kohta.
- Koolitajate töö- ja koolitustundidest joonistus välja suur muutus „Koolitaja 8“ müügitulu AK/h kohta aastate 2024 ja 2025 võrdluses.

## Soovitused juhile

- Vähenda allahindlusi, eriti KAS kategoorias (hetkel keskmine 33%)
- Kasvatada B2B ehk sisekoolitusel põhinevat müüki (kõrgem AK/h hind)
- Kõrghooaja mahtude maksimeerimine
- PRO kategoorias kaaluda iseseisva õppe lisamist - kõrge koolitusmaht kahandab tunnihinda. Teoreetilise osa asendamine iseseisva õppega vabastab koolitaja aja praktiliseks tööks.
- Koolitajate efektiivsuse ülevaatus -vaadata üle, kas koolitajad logivad ettevalmistustunde korrektselt - praegused erinevused koolitustundide osakaalus võivad osaliselt peegeldada logimisharjumuste erinevusi, mitte tegelikku tööaja jaotust. 


