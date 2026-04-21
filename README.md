# Koolituste-kasumlikkuse-m-jutegurid
Koolitusfirma BCS Koolitus soovib aru saada, mis koolituste omadused mõjutavad nende kasumlikkust. 

## Overiview of Company
Ettevõte pakub erinevaid koolitusi (nii avalikke kui ka sisekoolitusi), mis on jaotatud kategooriatesse (nt IT, kasutajakoolitused). Koolitusi viivad läbi erinevad lektorid/koolitajad, kelle panus sisaldab lisaks aktiivsele koolitamisele ka ettevalmistusaega.

## Problem
Koolitusfirma soovib aru saada, millised koolituste omadused (koolitaja, formaat, osalejate arv, maht, kategooria jne) mõjutavad kõige enam nende kasumlikkust. Antud projekt ühendab ettevõtte finantsandmed, koolituste metainfo ja koolitajate ajakulu, et luua terviklik pilt kasumlikkuse mõjuteguritest.

## Plan
Juhtkond soovib optimeerida ettevõtte portfelli ja ressursside kasutust. Peamised küsimused, millele soovitakse vastust leida:

Millised koolituste kategooriad ja formaadid toovad kõige suurema kasumimarginaali?

Kas suurem osalejate arv tagab alati suurema kasumi või kasvavad kulud proportsionaalselt?

Kuidas mõjutab lektorite ajakulu (ettevalmistus vs koolitustunnid) konkreetsete projektide ja koolituste tegelikku tasuvust?

Millistesse koolitustesse on mõistlik tulevikus enim investeerida?

Projekti lahendamiseks kasutatakse ELT (Extract, Load, Transform) metoodikat:

Extract & Load: Toorandmed (CSV/Excel) laetakse muutmata kujul PostgreSQL andmebaasi (Staging tabelid).

Transform: Andmete puhastamine, standardiseerimine ja ühendamine tehakse andmebaasisiseselt, kasutades SQL vaateid (Views).

Analyze & Visualize: Power BI ühendatakse SQL vaadetega, luuakse Tähtmudel (Star Schema), kirjutatakse DAX mõõdikud ning ehitatakse interaktiivsed töölauad (Dashboards).

## Andmekaitse kirjeldus - mis alustel andmeid töödeldakse


## Data 

### Data Sources
Analüüs põhineb viiel andmestikul, mis eksporditi ettevõtte infosüsteemidest:

koolitused.xlsx - Koolituste põhiandmed.

EA.xlsx - Raamatupidamise üldkanded.

EAT.xlsx - Raamatupidamise detailsed tehingud ja arved.

kulud või tulud.xlsx - Finantskannete klassifikaator.

Töö ja koolitustunnid.xlsx - Koolitajate tööaja logid.

### Data model - tee pildiks

Allikasüsteemid: Failid -> PostgreSQL Raw Tables (raw_koolitused, raw_ea, jne).

Andmebaasi kiht: SQL päringutega loodud Views, kus on ühendatud finantsid ja puhastatud dimensioonid.

Power BI kiht (Star Schema):

Faktitabelid: f_Finantsid (ühendatud EA ja EAT), f_Töötunnid.

Dimensioonitabelid: d_Koolitused, d_Koolitajad, d_Kalender, d_Kategooriad.

### Data lineage

### Data tables description

koolitused: Sisaldab infot iga koolituse kohta: ID, staatus, algusaeg, lektori nimi, kategooria (nt KAS, SPE), osalejate arv, akadeemiline maht ja käibeinfo (avalik vs sisekoolitus).

EA & EAT: Finantstabelid, mis sisaldavad kuupäeva, summat, projekti tunnust ja tehingu kirjeldust (EAT on detailsem, sisaldades arvete numbreid ja eristust, kas tegu on avaliku või siseostuga).

kulud või tulud: Lihtne abigraafik (Mapping table), mis seob kulud_tulud_ID väärtused (nt 3, 4, 7) selgelt kas Tuludeks, Otsekuludeks või Teisteks kuludeks.

Töö ja koolitustunnid: Ülevaade lektorite tegevustest. Sisaldab kuupäevi, lektori nime, tegevuse sisu (nt koolitus või töötuba/ettevalmistus), akadeemilisi tunde (AK tunnid) ja projekti tunnust.

### Data Cleaning
Peamised andmetöötluse sammud (teostatakse SQL-is):

Tabelite ühendamine: EA ja EAT liidetakse üheks finantside faktitabeliks. Tulemusele lisatakse kulud või tulud tabeli põhjal selge tunnus (Tulu/Kulu).

Kuupäevade vormindamine: Kõik kuupäevaveerud (nt Kuupv, StartDate, Start) teisendatakse ühtsesse DATE formaati, et neid saaks siduda keskse Kalendritabeliga.

Puuduvate andmete haldus: Tühjad väärtused kategooriates ja projektides asendatakse sildiga "Määramata" (Unknown), et vältida andmekadusid JOIN tegevuste käigus.

Teksti puhastamine: Lektorite nimede ja koolituste pealkirjade standardiseerimine (liigsete tühikute eemaldamine jne).

## Analysis

Key Metrics (DAX)
Kogutulu (Total Revenue): SUM(Summa) kus tüüp on "Tulud".

Kogukulu (Total Cost): SUM(Summa) kus tüüp on "Kulud".

Kasum (Profit): [Kogutulu] - [Kogukulu]

Kasumimarginaal % (Profit Margin): DIVIDE([Kasum], [Kogutulu])

Kasum per osaleja (Profit per Participant): DIVIDE([Kasum], SUM(Koolitused[OsalejateArv]))

Dashboard Structure
Executive Summary: Üldine finantsseis, kogukasum, marginaal ja tulude trendid ajas.

Profitability Drivers: Hajuvusdiagrammid ja tulpdiagrammid, mis võrdlevad kasumlikkust koolituse kategooria, mahu ja osalejate arvu lõikes.

Resource & Trainer Analysis: Lektorite töötundide (koolitus vs ettevalmistus) ja nende poolt läbiviidud koolituste kasumlikkuse võrdlus.

## Conclusion

