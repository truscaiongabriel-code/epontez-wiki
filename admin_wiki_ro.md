# Ghid Administrator

Tot ce poate face un administrator de companie în epontez. Secțiunile apar aici în
aceeași ordine ca în bara de navigare.

> **Ancorele sunt stabile.** Fiecare secțiune are un `id` explicit (de exemplu
> `<a id="clock-calendar">`) **identic în ghidul românesc și în cel englezesc**.
> Un link către `admin_wiki_ro.md#clock-calendar` sau
> `admin_wiki_en.md#clock-calendar` duce la același subiect. Nu schimbați un `id`
> chiar dacă reformulați titlul — este posibil ca ceva să trimită la el.

**Cuprins** — [Autentificare](#login) · [Navigare](#navigation) ·
[Status](#status) · [Pontaj](#clock) · [Angajați](#employees) ·
[Program](#program) · [Planificare](#planning) · [Șantiere](#sites) ·
[Incidente](#incidents) · [Parteneri](#partners) · [Fișe pontaj](#timesheets) ·
[Raport întârzieri](#report-late) · [Concedii](#timeoff) · [Terminale](#terminals) · [Plan](#plan) ·
[Setări](#settings) · [Parola dvs.](#password)

---

<a id="login"></a>

## Autentificare

Accesați `/login` și introduceți emailul și parola.

- **Parolă uitată** — folosiți *Ați uitat parola?*. Primiți pe email un link
  valabil o perioadă limitată, utilizabil o singură dată.
- **Cont dezactivat** — primiți un mesaj specific, nu o eroare generică de
  autentificare. Resetarea parolei **nu** ajută cât timp contul este inactiv;
  cereți super administratorului să îl reactiveze.
- **Schimbarea parolei vă deconectează din celelalte sesiuni.** Este intenționat:
  dacă altcineva cunoștea parola veche, sesiunea lui dispare odată cu ea.
- **Rămâneți conectat cât timp lucrați.** Sesiunea durează o oră și se reînnoiește
  la fiecare pagină deschisă, deci munca continuă nu vă deconectează niciodată; o
  oră fără nicio acțiune o face. Astfel un ecran nesupravegheat se blochează
  singur, și de aceea un tab lăsat deschis peste noapte cere reautentificare.

Selectorul de limbă se află în colțul din dreapta sus.

---

<a id="navigation"></a>

## Navigare

Bara de sus duce la secțiunile pe care rolul dvs. le poate deschide. Un
administrator complet le vede pe toate:

| Română | Engleză | Ce este |
|---|---|---|
| Status | Dashboard | Ziua de azi pe scurt |
| Pontaj | Clock | Pontarea angajaților |
| Angajați | Employees | Personalul |
| Program | Schedules | Funcții, ture și exportul PONTAJ |
| Șantiere / Sedii | Sites | Locurile de muncă și registrul de incidente |
| Parteneri | Partners | Firme colaboratoare |
| Fișe pontaj | Timesheets | Ore, costuri și exporturi lunare |
| Concedii | Time off | Cereri de concediu |
| Terminale | Terminals | Cititoare de amprentă |
| Plan | Plan | Mașini, cazare și repartizări |
| Setări | Settings | Configurarea companiei (doar administratori) |

**Limba** — selectorul din dreapta sus oferă **română, engleză și germană**, iar
alegerea este reținută pentru fiecare browser.

Unele companii sunt configurate să folosească **sediu** în loc de **șantier** în
toată interfața românească. Un super administrator stabilește acest lucru per
companie, deci ecranele dvs. pot diferi de cele ale unui colega de la altă
companie.

Numele dvs., *Schimbă parola* și *Deconectare* sunt în bara de jos.

---

<a id="status"></a>

## Status

Ziua de azi pe scurt.

**Rândul 1**
- **Pontați azi** — angajați distincți cu un pontaj valid astăzi, încheiat sau în
  curs
- **Ore luna aceasta** — orele încheiate până acum, după scăderea pauzei dacă este
  configurată

**Rândul 2**
- **Pontați acum** — angajați cu un pontaj deschis în acest moment
- **Angajați activi** — efectivul actual

**Rândul 3 — apăsați un card pentru a-l extinde**
- **Nepontați în ultimele 5 zile lucrătoare** — nume, funcție, șantier implicit
- **În concediu azi** — nume, tip, status (aprobat sau în așteptare)

**Grafice** (ultimele 30 de zile, câte o culoare per șantier) — *Persoane pe zi*
și *Ore pe zi*.

**Pontați în acest moment** — angajatul (cu eticheta partenerului dacă este
asociat), ora pontării, nota.

**Pontaje neînchise** — un avertisment care listează pe oricine are un pontaj
deschis din altă zi, ca să puteți corecta înregistrarea. Acestea apar cel mai des
când un angajat uită să prezinte amprenta la plecare.

---

<a id="clock"></a>

## Pontaj

Aici pontați angajații și corectați ce s-a înregistrat.

> **Trebuie să existe cel puțin un șantier activ** înainte de a putea ponta pe
> cineva.

Angajații sunt grupați în **secțiuni după șantierul implicit**, iar secțiunile
sunt ordonate **alfabetic**, mereu în același loc. Un șantier cu număr în nume se
ordonează natural — *Sediu T5* apare înaintea lui *Sediu T13*.

<a id="clock-visiting"></a>

### Cineva care a lucrat la alt șantier

Dacă un angajat a pontat la un șantier care nu este cel implicit — cel mai des
pentru că a prezentat amprenta la terminalul de acolo — apare **de două ori**: o
dată la șantierul lui și o dată la șantierul unde a lucrat efectiv, cu eticheta
**(în vizită)**.

- Acțiunile pe oricare dintre rânduri afectează aceeași persoană; nu sunt două
  înregistrări.
- Eticheta **(în vizită)** apare doar dacă angajatul *are* un șantier implicit de
  unde să lipsească. Cineva fără șantier implicit apare pur și simplu la șantierul
  unde a lucrat, fără etichetă.
- Fiecare rând arată doar pontajele care aparțin **secțiunii sale**, deci un
  șantier nu pare niciodată să aibă muncă petrecută în altă parte.
- Rândul unei persoane pontate **la alt șantier** apare ca nepontat, cu o notă
  discretă, iar butonul de pontare este dezactivat — oricum o a doua pontare
  simultană ar fi refuzată.

<a id="clock-calendar"></a>

### Vizualizarea calendar

O coloană per angajat, un rând per zi a lunii selectate.

| Celulă | Înseamnă |
|---|---|
| **HH:mm – HH:mm** | Pontaj încheiat — apăsați pentru editare |
| **HH:mm –** | Încă pontat — apăsați pentru a-l ponta la ieșire sau a edita |
| Dungi diagonale | Concediu |
| Gri | În afara intervalului editabil (vezi [Zile editabile](#settings-editpast)) |

<a id="clock-colours"></a>

### Ce înseamnă culorile

| Culoare | Înseamnă |
|---|---|
| **Verde** | O zi obișnuită |
| **Mov** | Ceva peste plan — vezi mai jos |
| **Roz / ambră** | Weekend / sărbătoare legală |
| **Triunghi galben în colț** | Pontajul nu a respectat tura: intrare după începerea turei sau ieșire înainte de final |

O celulă devine **mov** pentru oricare dintre:

- **ore suplimentare** față de programul de lucru al companiei;
- ore de **weekend sau sărbătoare legală**;
- **muncă în afara turei repartizate** — intrare cu peste **15 minute** înainte de
  începerea turei *sau* ieșire cu peste 15 minute după finalul ei.

Într-o zi **fără tură repartizată**, ultima regulă se aplică totuși, măsurată față
de **cel mai larg interval pe care îl lucrează vreodată funcția respectivă** —
cea mai timpurie oră de început și cea mai târzie de final dintre toate turele
funcției. Astfel, cineva care vine la o tură de după-amiază neplanificată nu este
marcat doar pentru că a fost în afara turei de dimineață; se marchează doar munca
din afara a *tot* ce lucrează funcția.

Treceți cursorul peste o celulă mov și eticheta spune care dintre motive se
aplică.

Movul înseamnă *mai mult* decât s-a planificat. Întârzierea sau plecarea
devreme sunt opusul și se arată prin **triunghiul galben**.

> Turele de noapte nu sunt evaluate după regula de 15 minute. O ieșire la 05:00 nu
> poate fi deosebită de o plecare devreme fără o dată, deci sistemul refuză să
> ghicească în loc să marcheze muncă de noapte corectă.

<a id="clock-select"></a>

### Selectarea celulelor

Apăsați celule pentru a le selecta (se colorează în albastru), apoi alegeți o
acțiune: **Pontare intrare**, **Pontare ieșire**, **Final** (ambele capete ale
unei zile trecute) sau **Concediu**. Zilele acoperite deja de concediu aprobat și
angajații deja pontați nu pot fi selectați.

Un pontaj **invalidat** nu este prezență: este ignorat de calendar, de statusul
rândului, de selecție și de totalurile pe șantier. Un pontaj *deschis* contează
totuși ca în curs, fiindcă este singurul mod de a ponta persoana la ieșire.

<a id="clock-table"></a>

### Vizualizarea tabel

O listă per șantier cu statusul fiecărui angajat, ultima pontare, șantierul și
nota.

- **Pontare intrare** — alegeți șantierul (cel implicit este preselectat), notă
  opțională.
- **Pontare ieșire** — notă opțională.

Etichetele de deasupra fiecărui tabel numără **Încheiate**, **În curs** și
**Nepontate** pentru acel șantier.

<a id="clock-manual"></a>

### Adăugarea manuală a unui pontaj

**+ Adaugă pontaj** înregistrează o intrare istorică pentru orice angajat și
dată — soluția pentru o pontare ratată. Stabiliți intrarea, opțional ieșirea,
șantierul și o notă.

<a id="clock-shift-times"></a>

### Completarea orelor din tură

În dialogul de adăugare apare deasupra câmpurilor de ore un rând de **etichete de
tură** — de exemplu `Tura B · 08:00–16:00`. Ele listează turele care aparțin
**funcțiilor angajaților selectați**. Apăsați una și orele se completează; le
puteți edita în continuare.

- Pentru o intrare cu început și final se completează ambele capete; pentru una cu
  o singură oră, doar cea relevantă.
- Ieșirea unei ture de noapte este plasată în ziua următoare.
- Dacă selectați persoane din două funcții, primiți ambele seturi de etichete.
- Dacă firma nu are ture definite, nu apar etichete, iar câmpurile revin la
  programul de lucru al companiei sau la 08:00–17:00.

<a id="clock-edit"></a>

### Editarea unei zile

Apăsarea unei celule încheiate deschide dialogul de editare; dacă există mai multe
pontaje în ziua respectivă, alegeți unul. Puteți corecta ambele ore. **Nota
existentă nu poate fi modificată** — scrieți în **Adaugă notă** și se adaugă
automat o marcă de audit cu numele dvs. și ora. Notele se completează, nu se
suprascriu niciodată, deci istoricul unei corecții supraviețuiește.

<a id="clock-bulk"></a>

### Acțiuni în masă

| Tip | Ce face |
|---|---|
| Pontare intrare | O intrare în fiecare zi selectată |
| Pontare ieșire | Închide pontajul deschis din fiecare zi |
| Final | Ambele capete în fiecare zi |
| Concediu | O cerere de concediu pentru fiecare zi |

**Acordarea concediului fără a selecta celule** — apăsați *Adaugă concediu* cu
nimic selectat și primiți date de **început și sfârșit** editabile, plus bifele
pentru angajați, deci un interval poate fi acordat direct. Dacă selectați mai
întâi celule, datele devin needitabile: acolo grila *este* intervalul, iar niște
câmpuri editabile lângă zilele evidențiate le-ar contrazice.

Stabiliți un singur șantier, ore și notă pentru tot lotul. Conflictele — concediu
aprobat într-o zi selectată, un pontaj suprapus — sunt raportate înainte de a se
salva ceva.

<a id="clock-lock"></a>

### Bannerul roșu de blocare

Dacă [Pontaj blocat](#settings-lock) este activ, apare un banner roșu. Cât timp
este blocat, pontarea în masă este limitată la ziua de azi și editările pe zile
trecute sunt refuzate. Folosiți-l pentru a îngheța o lună deja trimisă la
salarizare.

---

<a id="employees"></a>

## Angajați

Personalul, grupat după **șantierul implicit**, cu angajații care nu au unul într-o
grupă *Fără șantier* la început.

<a id="employees-filter"></a>

### Filtrare

Etichete — **Activi / Inactivi / Toate**. Apare și un filtru de partener dacă
aveți parteneri. Ambele se păstrează în adresă, deci o reîncărcare sau un link
trimis păstrează filtrul.

<a id="employees-columns"></a>

### Coloanele se adaptează singure

**O coloană fără date în toată firma este ascunsă.** Dacă nimeni nu are tarif
orar, nu există coloana Tarif orar; dacă nimeni nu folosește localizarea
automată, coloana dispare. Nume, Status, Creat și Acțiuni se afișează mereu.

Sub tabele, o notă spune ce este ascuns și cum se readuce:

> Coloane ascunse deoarece niciun angajat nu le folosește încă: **Email, Telefon,
> Amprentă** — activează oricare dintre ele din pagina de editare a unui angajat
> și coloana reapare.

Setul **nu** se schimbă când comutați eticheta Activi/Inactivi/Toate, deci
coloanele nu apar și dispar pe măsură ce filtrați.

<a id="employees-fingerprint"></a>

### Coloana Amprentă

Trei stări, iar cea din mijloc este importantă:

| Afișat | Înseamnă |
|---|---|
| **Inactiv** | Nu are voie să înregistreze un dispozitiv |
| **Înrolare în așteptare** (ambră) | Are voie, dar nu a înregistrat nimic — **PIN-ul îl pontează în continuare** |
| **2 dispozitive** | Atâtea dispozitive înregistrate — iar PIN-ul **nu mai funcționează pentru pontare** |

<a id="employees-add"></a>

### Adăugarea unui angajat

**Adaugă angajat**, apoi:

| Câmp | Observații |
|---|---|
| **Nume de familie**, **Prenume** | Ambele obligatorii |
| Funcție | Aleasă din lista din [Program](#program-roles) |
| Email, Telefon | Opționale |
| Data nașterii | Opțională |
| Șantier implicit | Preselectează șantierul la kiosk și grupează angajatul în aceste liste |
| Partener | Îl asociază unui colaborator — vezi [Parteneri](#partners) |
| Tarif orar | Tariful de bază pentru salarizare; multiplicatorii sunt per companie în Setări |
| Concediu anual (CO) — zile permise | Dezactivat când este selectat un partener |
| PIN Kiosk | 4–6 cifre; lăsați gol dacă nu are nevoie de kiosk. Se poate seta ulterior |

Un nume duplicat în aceeași companie este refuzat.

> Pentru a muta un angajat existent la alt șantier, folosiți **Transfer** din
> listă, nu acest formular.

<a id="employees-edit"></a>

### Editarea unui angajat

Tot ce este mai sus, plus:

- **ID sistem** — needitabil. Este singurul identificator al unui angajat; nu
  există un număr de personal separat.
- **Numele** — editabil doar în **48 de ore** de la crearea angajatului, pentru că
  numele este cel pe care se potrivesc fișele și exporturile.
- **Activ** — schimbarea cere un **Motiv**, scris în jurnalul de activitate cu
  numele dvs. și data.
- **Jurnal de activitate** — istoric care se completează, nu se șterge.
- **Pontaj automat** — o sarcină zilnică creează automat pontajul zilei. Are nevoie
  de șantier, oră de început și de final; doar în zilele lucrătoare, sărind pe
  oricine este deja pontat sau în concediu aprobat. Orele sunt interpretate în
  Europe/Bucharest.
- **Localizare auto** — captează GPS-ul la pontarea de la kiosk și stabilește dacă
  persoana era pe șantier. **Cu aceasta activă, coordonatele devin obligatorii**:
  un angajat care blochează locația nu se poate ponta. O verificare care poate fi
  sărită nu este o verificare.
- **Amprentă (passkey)** — vezi mai jos.
- **PIN Kiosk** — setați-l sau ștergeți-l.
- **Șterge datele de localizare** — elimină toate coordonatele GPS din pontajele
  acestui angajat, pentru o cerere GDPR de ștergere. Pontajele se păstrează.

<a id="employees-passkey"></a>

### Autentificare cu amprenta pe telefonul angajatului

Activarea **Amprentă** permite angajatului să se autentifice la kiosk atingând
senzorul propriului telefon, în loc să își aleagă numele și să tasteze un PIN.

Înrolarea cere **două elemente**, intenționat — PIN-ul angajatului **și** un cod
de unică folosință emis de dvs. aici. Doar PIN-ul ar permite oricui a văzut un
coleg tastând patru cifre să își asocieze permanent propria amprentă contului
acelui coleg.

1. Apăsați butonul pentru a genera un cod de înrolare. **Este afișat o singură
   dată** — copiați-l.
2. Angajatul deschide `/kiosk`, alege *Configurează amprenta pe acest dispozitiv*
   și introduce PIN-ul și codul.
3. Dispozitivul apare apoi în lista de aici, cu data ultimei utilizări.

Consecințe importante:

- **Odată ce are un dispozitiv înregistrat, PIN-ul nu mai funcționează pentru
  pontare** — dar funcționează în continuare pentru vizualizarea orelor și
  cererile de concediu. Un PIN poate fi dat unui coleg în parcare; o amprentă, nu.
- **Dezactivarea Amprentei șterge toate dispozitivele înregistrate.** Este o
  revocare, nu o pauză.
- **Revocarea unui dispozitiv restabilește imediat PIN-ul** — aceasta este calea
  de întoarcere pentru un telefon pierdut sau descărcat, împreună cu pontarea de
  către dvs. din acest panou.
- Eticheta **Passkey sincronizat** înseamnă că acreditarea se află în brelocul
  platformei angajatului și poate apărea pe celelalte dispozitive ale lui.
- Este pentru **telefoane personale**. Pe o tabletă comună orice amprentă înrolată
  deblochează orice passkey de pe ea, deci nu ar împiedica un angajat să ponteze
  un altul — pentru asta sunt [Terminalele](#terminals).

<a id="employees-csv"></a>

### Import și export CSV

- **Export** — alegeți Activi, Inactivi sau Toate. Coloanele sunt titluri fixe în
  engleză (`lastName`, `firstName`, `position`, …) pentru că reprezintă un contract
  cu programul care citește fișierul. Notele nu se exportă.
- **Import** — **doar administratori**, nu manageri de șantier: scrie la nivelul
  întregii companii și poate schimba cine este activ, ceea ce ar ocoli limitarea
  pe șantiere aplicată de toate celelalte ecrane.
  - `lastName` și `firstName` sunt obligatorii; fișierul este respins fără ambele.
  - Angajații existenți se potrivesc după **nume** (indiferent de majuscule), iar
    în lipsă după **email**.
  - Primiți mai întâi o **previzualizare**: de adăugat, de actualizat,
    neschimbate și erorile — nu se scrie nimic până nu confirmați.
  - O schimbare de status scrie o linie în jurnalul angajatului.
  - Rândurile neschimbate sunt sărite.

<a id="employees-pdf"></a>

### PDF

**↓ PDF** descarcă lista angajaților activi grupată după șantier, cu antetul
companiei.

<a id="employees-hide"></a>

### Ascunderea unei persoane

Un angajat **inactiv** are o secțiune **Zonă periculoasă** cu **Ascunde
angajatul**. Angajații ascunși dispar din pagina de pontaj, din kiosk, din lista
de angajați și din sarcina de pontaj automat. **Doar un super administrator poate
anula ascunderea**, deci folosiți-o pentru persoane care au plecat, nu pentru o
absență temporară.

---

<a id="program"></a>

## Program

Programul oficial de lucru al companiei: funcțiile pe care le ocupă oamenii, turele
pe care le lucrează acele funcții și exportul lunar PONTAJ. **Doar
administratori.**

<a id="program-roles"></a>

### Funcții

Lista oficială de posturi. Fiecare rând arată turele sale și câți angajați o
ocupă.

- **Adăugați** o funcție; numele sunt unice per companie, indiferent de majuscule.
- **Redenumire** — redenumirea peste un nume existent oferă **unificarea**:
  angajații trec la cealaltă funcție, repartizările lor de tură se șterg, iar
  funcția veche este eliminată.
- **Dezactivați** în loc să ștergeți dacă funcția este încă folosită. Ștergerea
  este refuzată cât timp cineva o ocupă.
- Un card ambră listează **angajații activi fără nicio funcție** — merită
  rezolvat, fiindcă funcția este cea care leagă o persoană de ture.

<a id="program-shifts"></a>

### Biblioteca de ture

Turele aparțin **companiei**, nu unei singure funcții, iar o funcție poate lucra
mai multe ture, în timp ce o tură poate deservi mai multe funcții.

1. Creați tura o singură dată în bibliotecă — nume, început, final, notă opțională.
2. Atașați-o funcțiilor care o lucrează, din oricare parte: bifați funcții pe tură
   sau ture pe funcție. Debifarea o detașează.

Observații:

- Un final egal sau anterior începutului înseamnă că tura **trece peste miezul
  nopții**; este permis și marcat cu eticheta *peste noapte*.
- Două ture pot avea același nume — fiecare selector arată `nume · 07:00–16:00`,
  ceea ce le deosebește. Ce este refuzat este același nume **și** aceleași ore în
  aceeași companie, adică două rânduri imposibil de distins.
- Turele sunt **informative**. Nimic din calculul orelor, al suplimentarelor sau
  al costurilor nu citește o tură. Ele alimentează planificarea, marcajele de
  respectare a programului și fișele PONTAJ.
- Nimeni nu are o tură permanentă. Tura lucrată este un fapt **zilnic**, stabilit
  în [Planificare](#planning), fiindcă în practică se schimbă de la o zi la alta.
- Ștergerea unei ture șterge și repartizările ei pe zile, deci acele zile devin
  goale în Planificare.

<a id="program-export"></a>

### Exportul PONTAJ

Selectorul de lună și butonul verde **Descarcă Excel** se află în antetul paginii,
cu două filtre lângă ele.

| Filtru | Opțiuni |
|---|---|
| **Funcție** | *Toate funcțiile* (implicit) sau o funcție |
| **Partener** | *Fără partener* (**implicit**), *Toți partenerii* sau un partener |

> **Filtrul de partener exclude implicit colaboratorii.** O fișă PONTAJ este un
> document de salarizare pentru personalul propriu, iar oamenii unui colaborator
> sunt facturați prin partenerul lor. Alegeți *Toți partenerii* dacă doriți
> totuși pe toți — și verificați ce este selectat înainte de a trimite fișierul la
> salarizare.

Ambele filtre rămân în bara de adrese, deci o reîncărcare le păstrează și
descărcarea conține exact ce vedeți.

Două foi, identice în structură ca să se alinieze coloană cu coloană:

- **Vedere planificare** — planul pentru toată luna.
- **Vedere pontaj** — același plan **trunchiat la ziua de azi**, adnotat cu
  prezența. Într-o zi programată în care s-a lucrat, rândul arată normal; într-una
  în care nu s-a lucrat, orele devin **0** și celula este desenată roșu închis cu
  o notă *Absent*. O lună trecută merge până la final; o lună viitoare este goală,
  fiindcă nimeni nu poate lipsi de la o tură care nu s-a întâmplat.

Vederea **Pontaj** poartă și un rând per zi cu **locația pontată efectiv** —
etichetat *Șantier pontat* sau *Sediu pontat*, după vocabularul companiei. Este un
fapt diferit de coloana **Sediu**, care este șantierul *atribuit* angajatului și
arată o singură valoare pentru toată luna: o zi lucrată la alt șantier se vede
doar în acel rând, pentru că un terminal înregistrează locația pe care este fixat
cititorul. O zi împărțită între două locații arată prima cu un `+`.

Ambele raportează orele și **orele planificate** ale turei. O zi fără nimic
planificat este goală în ambele, chiar dacă cineva a pontat — fișa este orientată
pe program, deci nu există ore planificate față de care să raporteze munca.

Coloanele sunt `Nr.Crt | Nume | Functie | Sediu | Program de lucru | 1..n | total
| Bonus/RON`, cu `SUM()` activ per angajat. **Sediu** este șantierul implicit al
angajatului, o singură valoare unificată per persoană. Titlurile sunt **mereu în
română**, indiferent de limba interfeței, pentru că structura fișierului este un
contract cu cel care o primește. Limitat la 450 de angajați.

Concediul aprobat înlocuiește tura: codul (`CO`, `CM`, `CFP`, `CS`…) intră în
*Inceput*, finalul și pauza se golesc, iar ziua înregistrează **0 ore**, deci
totalul lunar numără în continuare doar orele lucrate.

---

<a id="planning"></a>

## Planificare

Se ajunge din butonul **Planificare** de pe o funcție din Program sau din butonul
colorat din antet. **Doar administratori.**

<a id="planning-grid"></a>

### Grila

Angajații pe verticală, zilele lunii pe orizontală — forma care răspunde la
întrebarea *este acoperită fiecare noapte?*, lucru pe care un calendar per
persoană nu îl arată.

- Fiecare tură are culoarea sa, stabilă în toată grila.
- Weekendurile sunt roz, sărbătorile legale ambră.
- Un **✓** mov marchează o zi în care cineva a lucrat **fără nimic planificat**.
- Opțiunea **Toate funcțiile** din selector arată pe toată lumea deodată, iar
  legenda listează fiecare tură o singură dată, chiar dacă mai multe funcții o
  împart.

<a id="planning-automation"></a>

### Două etichete în partea de sus: ce scrie singur în planificare

Deasupra grilei, atât în Program cât și în Planificare, două etichete arată dacă
mecanismele automate sunt active — verde pentru activ, gri pentru inactiv. Ambele
scriu în planificare fără ca nimeni să apese nimic, deci dacă o grilă s-a
schimbat peste noapte, ele vă spun care ar fi putut să o facă. Treceți cursorul
peste oricare pentru explicația completă.

| Etichetă | Ce face |
|---|---|
| **⊕ Completare automată a turei la pontare** | Repartizează o zi **goală** atunci când cineva pontează în ea |
| **◎ Detectare schimbare tură** | Mută o zi **deja repartizată** când pontajul se potrivește mai bine cu altă tură |

Sunt sarcini diferite în mod intenționat, iar o zi poate arăta întâi una, apoi
cealaltă — completată dimineața, corectată în noaptea următoare. Ambele se
activează per companie în [Setări](#settings-autofill).

<a id="planning-cells"></a>

### Citirea unei celule

Fiecare celulă este colorată cu culoarea turei și afișează numele scurt al turei
peste ora de început și cea de final:

```
  TB
07:00
16:00
```

Trecerea cursorului arată tot ce ține de acea singură zi:

```
Tura B · 07:00–16:00
2026-10-14
Pontaj: 07:12 – 16:03
Întârziere la intrare
```

O zi în care nimeni nu a pontat afișează **Fără pontaj** pe a treia linie, în loc
să o lase goală. Simbolul din colț este verdictul de respectare a programului —
✓ verde la timp, ✓ ambră întârziere sau plecare devreme, ✗ roșu programat dar
absent — și stă pe un fond alb, ca să rămână lizibil indiferent de culoarea
turei.

<a id="planning-select"></a>

### Selectarea mai multor celule

Repartizarea câte un dialog pe rând este lentă, de aceea **celulele libere pot fi
apăsate pentru a construi o selecție**, iar apoi **Repartizează tura (n)** aplică
o singură tură tuturor.

- **Doar celulele libere intră în selecție.** O celulă care are deja o tură sau
  concediu aprobat deschide dialogul ca înainte — editarea acelora este altceva
  decât repartizarea unei zile goale.
- **O singură funcție pe rând.** O tură aparține unei funcții, deci o selecție
  care cuprinde două nu ar putea fi satisfăcută de nicio tură; apăsarea într-o
  altă funcție începe o selecție nouă, în loc să eșueze la repartizare.
- **Nimic selectat?** Totul se comportă exact ca înainte.
- Zilele selectate sunt grupate în serii de date consecutive per angajat, deci
  două săptămâni pentru patru persoane sunt patru operații, nu cincizeci și șase.
  Fiecare zi aleasă este respectată, inclusiv weekendurile — le-ați ales
  deliberat.

Apăsarea pe *Repartizează* preia celulele și golește selecția; anularea
dialogului înseamnă reselectare.

<a id="planning-assign"></a>

### Repartizarea unei ture

Apăsați orice celulă — sau folosiți câmpurile De la/Până la pentru un interval,
singurul mod rezonabil de a introduce două săptămâni de nopți.

- **Un interval este împărțit în serii de zile lucrătoare.** 2–13 februarie devine
  două repartizări, nu una lungă care înghite weekendul. Sâmbetele, duminicile și
  sărbătorile legale rămân goale dacă nu bifați *include zilele nelucrătoare*.
- **O zi singură este respectată mereu ca atare** — așa puneți pe cineva într-o
  sâmbătă.
- O repartizare **fără dată de final** acoperă necesar fiecare zi, inclusiv
  weekendurile, fiindcă nu există o ultimă zi la care să se oprească. Dialogul o
  spune.
- **Suprapunerile sunt remodelate, nu refuzate.** Trecerea cuiva pe nopți de pe 10
  încheie repartizarea lui de dimineață fără final pe 9.
- Primiți mereu o **previzualizare** a ce s-ar schimba și un pas de confirmare
  oricând s-ar modifica ceva.

<a id="planning-switch"></a>

### Schimbul între două persoane pentru o zi

Pentru o singură zi, dialogul oferă un panou **Schimbă tura** cu colegii aflați
în altă tură în acea zi. Un schimb:

- decupează **o singură zi** din repartizarea fiecăruia, lăsând neatins restul
  ambelor planificări;
- marchează ambele zile **Schimbat**, cu o notă care spune cine a făcut schimbul
  și cu cine;
- cere ca cei doi să ocupe aceeași funcție și să fie în ture diferite în ziua
  respectivă.

O zi schimbată nu este niciodată suprascrisă de detectarea automată a turelor — o
decizie umană are prioritate față de detector.

<a id="planning-clear"></a>

### Golirea unei zile

**Golește ziua** decupează acea zi din repartizarea din jur, împărțind-o în două
dacă ziua se află la mijloc. Nu readuce ce a fost remodelat anterior pentru a face
loc.

<a id="planning-timeoff"></a>

### Alocarea concediului din planificare

- **Alocă concediu**, lângă *Repartizează tura*, acoperă un interval pentru mai
  mulți angajați.
- În dialogul celulei, un comutator **Tură / Concediu** acoperă ziua pe care ați
  apăsat.
- O zi deja în concediu aprobat oferă **Elimină concediul** în locul lui *Golește
  ziua*. Concediul se stochează câte un rând per zi lucrătoare, deci este un
  singur rând, iar el este **anulat, nu șters** — pista de audit supraviețuiește
  și, pentru că doar concediul aprobat are prioritate, tura de dedesubt reapare
  singură.
- Puteți repartiza o tură într-o zi deja acoperită de concediu; planificarea de
  dedesubt se editează în continuare, iar dialogul o spune.

Ambele căi trec prin aceleași verificări ca secțiunea Concedii, deci suprapunerile
și pontajul într-o zi de concediu se comportă identic oriunde.

<a id="planning-table"></a>

### Tabelul de sub grilă

Câte un rând per **zi programată** — `Angajat | Tură | Zi | Intrare | Ieșire |
Status | Notă` — unde Intrare și Ieșire sunt prima pontare și ultima ieșire din
ziua respectivă.

**Fiecare angajat este restrâns**, iar apăsarea pe rândul său îi deschide zilele.
O lună pentru o funcție ajunge la sute de rânduri, deci antetul poartă totalurile
care contează — ✓ la timp, ✓ întârziat, ✗ absent, ✓ neplanificat — și numărul de
zile ascunse. Cineva cu un ✗ roșu rămâne o linie vizibilă, deci restrângerea
ascunde detaliul, nu semnalul.

**Tabelul se oprește la ziua de azi**, în timp ce grila arată în continuare toată
luna. Toate coloanele în afară de Tură raportează ce s-a întâmplat efectiv, iar o
zi viitoare nu are nimic din asta, deci acele rânduri erau o pagină de spații
goale. O lună trecută este completă; o lună viitoare arată un tabel gol și o grilă
plină. Nu se pierde nimic — apăsarea unei celule viitoare din grilă deschide tot
dialogul de repartizare.

| Nuanță | Înseamnă |
|---|---|
| **Roșu** | Planul a fost încălcat: intrare după început, ieșire înainte de final sau niciun pontaj într-o zi a cărei tură începuse deja |
| **Mov** | Nu exista plan: s-a lucrat într-o zi fără nimic planificat. Statusul este **Neplanificat**, iar acțiunea oferă *Repartizează tura* în loc de *Golește ziua* |

Coloana **Status** arată și cum a ajuns ziua să fie repartizată:

| Status | Înseamnă |
|---|---|
| *(gol)* | Pusă de o persoană |
| **⇄ Schimbat** | Un schimb de o zi între doi colegi |
| **⊕ Completat automat** | Scrisă de [completarea automată](#settings-autofill) pentru că cineva a pontat într-o zi nerepartizată. Nota reține ora pontării și tura potrivită |
| **◎ Detectat automat** | Mutată de detectarea schimbării de tură; treceți cursorul pentru a vedea ce a înlocuit |

„Începuse deja” înseamnă că ziua a trecut sau că este azi și ora de început a
trecut — deci o tură de mai târziu astăzi nu este încă o absență.

Concediul aprobat **nu** este absență și are prioritate față de ambele.

---

<a id="sites"></a>

## Șantiere

Locurile dvs. de muncă.

<a id="sites-add"></a>

### Adăugarea unui șantier

Nume, adresă opțională și un **punct pe hartă** opțional. Căutați o adresă sau
apăsați pe hartă pentru a-l plasa.

<a id="sites-coords"></a>

### De ce contează coordonatele

Coordonatele fac posibilă verificarea prezenței pe șantier. Fără ele, o pontare nu
poate fi niciodată evaluată — oricât de strâmtă ar fi [raza](#settings-radius) —
deci acele rânduri sunt marcate ambră cu **Fără coordonate**. Altfel, lipsa rămâne
invizibilă până când cineva se întreabă de ce toate indicatoarele de locație sunt
gri.

Prezența în afara șantierului este **înregistrată, nu blocată**. Este o dovadă
pentru cel care verifică fișa, nu o barieră la pontare.

<a id="sites-autoclockout"></a>

### Pontare automată de ieșire per șantier

Activați-o și stabiliți o oră, iar oricine este încă pontat **la acel șantier**
este pontat la ieșire atunci. Regula șantierului are prioritate față de
[cea a companiei](#settings-autoclockout).

<a id="sites-partner"></a>

### Asocierea cu un partener

Un șantier poate aparține unui singur partener. Pagina Parteneri listează apoi
șantierul sub acel partener.

<a id="sites-status"></a>

### Activ, inactiv, ascuns

Etichetele filtrează **Active / Inactive / Toate**. Un șantier trebuie să fie
**inactiv înainte de a putea fi ascuns**, iar șantierele ascunse sunt invizibile
pentru administratori, kiosk și sarcina de pontaj automat — **doar un super
administrator poate anula ascunderea**.

Fiecare modificare adaugă o linie de audit în notele șantierului: *Actualizat de
«nume» · data (câmpuri modificate)*.

---

<a id="incidents"></a>

## Incidente

Un registru de incidente per șantier, pentru Legea 319/2006. Butoanele sunt pe
rândul fiecărui șantier și sunt disponibile oricărui rol care poate vedea
Șantiere.

<a id="incidents-add"></a>

### Înregistrarea unui incident

**Înregistrare incident**, apoi:

| Câmp | Opțiuni |
|---|---|
| **Tip** | Accident · Eveniment evitat · Întâmplare periculoasă · Boală profesională |
| **Gravitate** | Minor · Moderat · Grav · Mortal |
| **Data incidentului** | Când s-a petrecut |
| **Data înregistrării** | Când a fost consemnat |
| **Descriere** | Obligatorie |
| **Angajați implicați** | Aleși dintre angajații repartizați la acel șantier |
| Martori | Opțional |
| Măsuri corective | Opțional |
| **Raportat autorităților** | Da/nu |

<a id="incidents-pdf"></a>

### PDF-ul registrului

**PDF incidente** cere o lună și produce un registru A4 landscape pentru acel
șantier și acea lună. Dacă nu există nimic consemnat, vă spune, în loc să producă
un fișier gol.

---

<a id="partners"></a>

## Parteneri

Firme colaboratoare ai căror oameni lucrează pe șantierele dvs.

Câmpuri: nume, adresă, email, telefon, CUI, activ. Tabelul arată **șantierele**
asociate fiecărui partener ca subrânduri. Etichetele filtrează **Activi /
Inactivi / Toate**.

Două lucruri decurg din asocierea unui angajat cu un partener, ambele intenționat:

- **Nu poate cere concediu.** Concediul este treaba angajatorului său. Este
  refuzat atât în panou, cât și la kiosk.
- **Câmpurile de concediu anual sunt dezactivate** în formularul angajatului, din
  același motiv.

**Filtrul de partener** din paginile Angajați și Pontaj este altceva decât
secțiunea *Parteneri*: filtrează **angajați**, nu pagini. Separat, un manager de
șantier poate fi configurat să vadă doar angajații care **nu** sunt asociați unui
partener.

---

<a id="timesheets"></a>

## Fișe pontaj

Ore, costuri și exporturi, lună cu lună.

<a id="timesheets-filters"></a>

### Ce vedeți

Antetul are selectorul de lună și filtre pentru **șantier**, **angajat** și
**partener** (*Toți partenerii* sau *Fără partener*). Folosiți săgețile sau
câmpul de lună pentru a naviga.

<a id="timesheets-read"></a>

### Citirea tabelului

Fiecare angajat este un bloc cu pontajele lunii, cu subtotaluri zilnice și un
total lunar.

| Marcaj | Înseamnă |
|---|---|
| Eticheta **Auto** | Creat de sarcina de pontaj automat, nu de o persoană |
| **Rând mov** | Suplimentare, weekend, sărbătoare sau muncă în afara turei — aceleași reguli ca la [culorile din pontaj](#clock-colours) |
| Tăiat / estompat | Marcat invalid; nu se numără nicăieri |
| Eticheta partenerului | Angajatul este asociat unui colaborator |

Antetul angajatului arată `| șantier implicit: «nume»` când există unul.

<a id="timesheets-gps"></a>

### Indicatoarele de locație

O tură este o singură înregistrare cu **două** poziții, deci fiecare rând poate
purta două indicatoare: **Intrare** și **Ieșire**. Fiecare duce la OpenStreetMap
exact în acel punct.

| Indicator | Înseamnă |
|---|---|
| **Verde** | Pe șantier |
| **Roșu** | În afara șantierului |
| **Gri** | A fost înregistrată o poziție, dar șantierul nu avea coordonate față de care să fie evaluată — „nu se poate verifica” |
| Niciun indicator | Nu s-a captat nicio poziție |

Acesta este singurul loc unde se arată poziția unui **angajat**; orice alt link de
hartă din aplicație duce la un șantier.

**Verdictul este înghețat în momentul pontării.** Modificarea razei sau adăugarea
de coordonate la un șantier afectează doar pontările ulterioare — reevaluarea unei
luni încheiate prin schimbarea unei setări astăzi este exact ce ar face datele de
prezență imposibil de susținut.

Coordonatele se șterg automat după **180 de zile** și la cerere din pagina de
editare a angajatului.

<a id="timesheets-edit"></a>

### Corectarea unui pontaj

Apăsați un rând pentru a-i edita orele sau a-l marca invalid. Notele se adaugă, cu
marcă de audit, ca în pagina de pontaj. Revalidarea unei intrări invalide reia
verificarea de suprapunere, deci un pontaj recuperat nu poate ajunge să se
suprapună cu unul valid.

<a id="timesheets-download"></a>

### Descărcări

Meniul de descărcare oferă:

| Fișier | Conține |
|---|---|
| **PDF** | Fișa lunară, cu antetul și logoul companiei |
| **Excel** | Aceleași date, per angajat sau per șantier |
| **CSV salarizare** | Format pentru programe, **inclusiv tarifele orare** |
| **Raport întârzieri** | Cine a întârziat sau a plecat devreme, și cu câte minute — vezi mai jos |

Toate trei respectă filtrele setate.

> **Managerii de șantier nu pot descărca niciunul**, chiar dacă pot citi pagina.
> Fișierul de salarizare conține salarii, iar restricția este aplicată pe server,
> nu doar prin ascunderea butonului.

---

<a id="report-late"></a>

### Raportul de întârzieri

Disponibil și din *Descarcă Excel* în [Program](#program-export), respectând
filtrele setate pe pagina de pe care porniți.

Angajații în stânga, zilele deasupra, și șapte rânduri pentru fiecare persoană:
pontaj intrare, pontaj ieșire, minute întârziere, minute plecare devreme, început
tură, sfârșit tură și locația pontată. Trei totaluri urmează după ultima zi —
minute de întârziere, minute de plecare devreme și ore de tură planificate — iar
**cel cu cele mai multe este primul**, ceea ce este scopul raportului.

Capătul încălcat este colorat: roșu pentru întârziere, ambră pentru plecare
devreme, iar ora pontării este colorată împreună cu minutele pe care le-a produs.

Patru lucruri pe care nu le face, în mod intenționat:

- **Nicio perioadă de toleranță.** Raportul spune minutele; o toleranță ține de
  felul în care îl citiți, nu ascunsă în număr.
- **Angajații fără nicio abatere lipsesc.** Ordonarea este un clasament, iar o
  foaie plină de rânduri goale ar fi inutilizabilă.
- **O zi în care nimeni nu a pontat nu produce nimic** — aceea este absență, pe
  care vederea de pontaj PONTAJ o raportează deja cu un zero roșu.
- **Turele de noapte arată orele, dar nu minutele.** „HH:mm" nu conține o dată,
  deci o ieșire la 23:00 pentru o tură 22:00–06:00 s-ar calcula drept șase ore
  *mai devreme*. O notă pe celulă o spune.

O zi fără tură repartizată se raportează față de programul de lucru al companiei,
dacă este activat, fapt notat pe celulă.

Doar administratori, ca celelalte exporturi: fișierul numește persoane și
cuantifică întârzierile lor.

---

<a id="timeoff"></a>

## Concedii

Cereri de concediu, de la dvs. sau de la angajați prin kiosk. O cerere în
așteptare pune un asterisc pe tabul din navigare.

<a id="timeoff-types"></a>

### Tipuri

`CO` concediu de odihnă · `CFP` fără plată · `MEDICAL` medical · `MARRIAGE`
căsătorie · `BLOOD_DONATION` donare de sânge · `SPECIAL_EVENTS` evenimente
speciale · `MILITARY` militar · `FUNERAL` deces · `CHILD_BIRTH` naștere ·
**`MATERNITY` maternitate** · `EXCUSED` motivat · `ABSENT` absent.

**Maternitatea** este separată de *Naștere copil* în mod intenționat: aceasta din
urmă este perioada de câteva zile acordată în jurul nașterii, maternitatea este
perioada statutară lungă, iar un pontaj le raportează separat. Codul său de
salarizare este `CMAT`, fiindcă `CM` este deja concediu medical, iar `CS` deja
căsătorie.

<a id="timeoff-read"></a>

### Citirea tabelului

Concediul se stochează **câte un rând per zi lucrătoare**, deci tabelul are coloane
separate **Data**, **Ziua** și **Zile**, iar etichetele de sumar numără zile
lucrătoare, nu zile calendaristice. O cerere peste un weekend nu umflă numărul.

<a id="timeoff-actions"></a>

### Acțiuni

**Aprobă**, **Respinge** sau **Anulează**. Se înregistrează cine a depus cererea.

**Doar concediul aprobat înlocuiește o tură programată.** O cerere în așteptare nu
a fost acordată, deci planificarea arată în continuare tura și marchează celula cu
un punct mic.

Înlocuirea se aplică atunci când planificarea și fișele sunt *citite*, niciodată
scrisă definitiv — deci anularea concediului face ca tura de dedesubt să reapară
singură, fără niciun pas de reparare.

Există un **PDF** per cerere, pentru semnare.

---

<a id="terminals"></a>

## Terminale

Cititoare fizice de amprentă. **Doar administratori.**

<a id="terminals-why"></a>

### De ce un terminal și nu o tabletă

Un terminal face **identificare 1:N**: angajatul prezintă un deget și dispozitivul
răspunde *cine este*, fără ca nimeni să fi fost selectat înainte. Este singura
soluție care împiedică efectiv un angajat să ponteze un altul. Senzorul propriu al
unei tablete nu poate, pentru că sistemul de operare tratează orice amprentă
înrolată ca fiind egală.

Alte două avantaje vin gratuit: **șantierul este sigur**, pentru că cititorul este
fixat pe el — mult mai fiabil decât o alegere declarată în meniu — și **nicio
amprentă nu părăsește dispozitivul**. Se stochează doar un număr care leagă o
poziție din terminal de un angajat, ceea ce ține platforma în afara regulilor
privind datele biometrice.

<a id="terminals-add"></a>

### Înregistrarea unui cititor

Adăugați-l cu nume, serie, producător și model, apoi asociați-l unui **șantier** —
acea asociere atribuie pontajele, deci stabiliți-o înainte de a înrola pe cineva.
Un panou vă avertizează dacă un terminal nu are șantier.

<a id="terminals-setup"></a>

### Panoul de configurare

Un panou de copiat pentru cine instalează cititorul: host, port, adresa de intrare,
asocierea cu șantierul, o **listă de IP-uri permise** și **contul și cheia ISUP**
editabile, cu care terminalul sună către server.

- **Contul** se setează pe ecranul propriu al terminalului, *Comm. → EHome*, și
  **nu are legătură cu seria** — aveți nevoie de ambele.
- După schimbarea cheii EHome, așteptați până la **cinci minute**. Receptorul își
  citește lista de dispozitive periodic și, până se reîmprospătează, prezintă
  cheia veche, iar terminalul este refuzat. O serie de mesaje de respingere a
  cheii imediat după o schimbare este asta, nu o defecțiune.

<a id="terminals-mappings"></a>

### Asocierea angajaților cu dispozitivul

Tabelul listează fiecare ID de utilizator din dispozitiv, angajatul asociat și dacă
terminalul deține un **card RFID** pentru el. Eticheta de card înseamnă că
cititorul a raportat unul; numărul este în indiciu. Cardurile adăugate la tastatura
terminalului apar după următoarea reîmprospătare.

Rândurile sunt marcate când cele două părți nu coincid:

| Marcaj | Înseamnă |
|---|---|
| **asociat aici, absent pe terminal** | Avem o asociere pe care cititorul nu o cunoaște |
| **asociat aici cu «nume» — asociere greșită** | Cititorul deține alt nume pentru acel ID |
| **neasociat** | Un utilizator al dispozitivului care nu aparține nimănui — de obicei contul instalatorului |

<a id="terminals-fixname"></a>

### Corectarea unui nume greșit

Dacă modificați numele unui angajat după ce a fost trimis la un cititor, cititorul
păstrează scrierea veche și rândul este marcat ca asociere greșită. Folosiți
**Corectează numele pe terminal** pe acel rând.

> **Nu** încercați să rezolvați asta trimițând angajatul din nou. O retrimitere
> este refuzată ca ID ocupat și asocierea este ștearsă, după care pontajele lui nu
> se mai potrivesc cu nimeni. *Corectează numele pe terminal* schimbă doar numele,
> lăsând neatinse amprentele înrolate și drepturile de acces.

<a id="terminals-push"></a>

### Trimiterea angajaților către un terminal

Trimiterea **identității** de aici face ca instalatorul să aleagă o persoană deja
prezentă, cu nume, la cititor, în loc să inventeze un număr — ceea ce împiedică
orele unui angajat să ajungă pe numele altuia.

- **Alege angajați…** deschide o listă cu bifare și căutare. Persoanele deja
  prezente pe cititor sunt gri, cu ID-ul alocat. *Selectează tot* se aplică doar
  rândurilor arătate de căutare, deci nu poate include în liniște pe cineva aflat
  în afara ecranului.
- **Trimite toți angajații neasociați** este acțiunea potrivită la punerea în
  funcțiune a unui cititor nou.
- ID-urile sunt **alocate de platformă**, intenționat peste cel mai mare număr
  cunoscut de oricare parte, deci un ID reciclat nu poate atașa pontajele unui
  deținător anterior unui angajat nou.
- **Amprenta în sine se înrolează manual la cititor.** Niciun producător nu oferă
  înrolarea fără a predea șablonul, lucru pe care platforma nu îl cere.

Comenzile se pun la coadă în loc să ruleze instantaneu, pentru că un cititor din
rețeaua unui șantier de obicei nu poate fi apelat din exterior. Numărul de comenzi
în așteptare și eșuate se afișează pe dispozitiv.

<a id="terminals-punchlog"></a>

### Jurnalul de pontări

Cele mai recente zece pontări, iar **Arată încă 10** aduce următoarele zece doar
când este cerut — jurnalul crește cu fiecare pontare a fiecărui terminal, deci
încărcarea mai multor decât citiți ar deveni mai lentă săptămână de săptămână.
Când ajungeți la final, acest lucru este spus, în loc să se ofere un buton care nu
face nimic.

| Rezultat | Înseamnă |
|---|---|
| **Intrare / Ieșire** | Normal — direcția este dedusă, niciodată preluată din dispozitiv |
| **Utilizator necunoscut** | O pontare de la un ID neasociat nimănui |
| **Respins** | Un deget care nu a corespuns nimănui. Nu identifică pe nimeni, deci nu poate deveni prezență, dar este consemnat |
| **Duplicat ignorat** | O repetare a unei pontări deja înregistrate |
| **Prea rapid** | O a doua atingere în 60 de secunde |
| **Pontaj deschis vechi** | O pontare mult după o intrare neînchisă: se deschide o tură nouă și cea veche vă este lăsată de corectat, în loc să se inventeze o oră de ieșire plauzibilă |
| **Dispozitiv inactiv** | Terminalul este dezactivat în aplicație |

Citirea acestui jurnal este modul în care problemele devin vizibile: o serie de
**Respins** fără reușite între ele înseamnă un senzor murdar, un cititor defect
sau cineva neînrolat. O serie de **Prea rapid** în jurul orei de pontare automată
de ieșire înseamnă că sarcina înghite pontări reale.

<a id="terminals-offline"></a>

### Online / offline

Eticheta trece pe offline după **5 minute** fără contact — sau după trei intervale
proprii de interogare ale dispozitivului, oricare este mai mare, ca un cititor
interogat intenționat o dată la zece minute să nu oscileze.

Ștergerea unui terminal elimină asocierile și istoricul de pontări, dar
**păstrează pontajele deja create** — acelea sunt ore lucrate real.

---

<a id="plan"></a>

## Plan

O zonă separată pentru logistica muncitorilor: mașini, cazare și cine doarme unde.
Are navigare proprie și pagină proprie de autentificare la `/plan/login`. Managerii
de partener și angajații nu o pot deschide.

<a id="plan-cars"></a>

### Mașini

Parcul auto: marcă, model, an, număr de înmatriculare, culoare, locuri, cutie de
viteze (manuală sau automată), combustibil (benzină, diesel, hibrid, electric) și
data achiziției.

<a id="plan-accommodation"></a>

### Cazare

Locurile unde stau muncitorii: nume, adresă, număr de camere, capacitate în
persoane și un punct opțional pe hartă. Fiecare cazare are **camere**,
identificate prin număr și unice în cadrul acelei cazări, iar angajații sunt
repartizați pe camere.

Sunt disponibile export și import CSV pentru cazare.

<a id="plan-assign"></a>

### Ecranul Planificare

Alegeți un șantier și ecranul arată angajații lui alături de cazările disponibile,
cu **distanța în km** de la acel șantier și ocuparea fiecărei camere.

- Capacitatea se arată ca *locuri* și *ocupate*, iar o cameră plină este marcată
  **Plin**.
- Repartizați un angajat într-o cameră sau anulați repartizarea.
- O cameră fără nimeni afișează **Niciun rezident repartizat**.
- Angajații fără șantier apar la **Fără șantier**.

**Exportă repartizările** și **Importă repartizările** mută toată alocarea ca CSV.

<a id="plan-directories"></a>

### Angajați și Șantiere

Registre doar pentru citire, pentru a căuta ceva fără a părăsi această zonă.

---

<a id="settings"></a>

## Setări

**Doar administratori.** Managerii de șantier nu pot deschide această pagină — este
locul unde se creează managerii de șantier.

<a id="settings-company"></a>

### Detalii companie

Nume, adresă și un **logo**, care apare în eticheta din navigare, la kiosk și în
antetele PDF. Încărcați o adresă publică de imagine sau un PNG/JPEG de maximum
200 KB.

<a id="settings-radius"></a>

### Raza pe șantier

Cât de aproape de punctul de pe hartă al unui șantier trebuie să fie o pontare de
la kiosk pentru a conta ca fiind pe șantier, **în metri**, implicit **500**.

Per companie, pentru că un sediu în centrul orașului și un terasament de autostradă
au nevoie de toleranțe complet diferite. Minimul este **25 m** intenționat: GPS-ul
de consum are o precizie de aproximativ 5–20 m, mai slabă între clădiri înalte,
deci orice valoare mai strânsă ar marca oamenii ca fiind în afara șantierului în
timp ce stau pe el. Maximul este 50 000 m.

O modificare salvată se aplică pontărilor în până la **un minut**, lucru util de
știut când testați manual.

<a id="settings-selfie"></a>

### Fotografie la pontare

Activați-o și stabiliți un **procent**, iar acea proporție a pontărilor de la
kiosk cere o fotografie.

**Decizia este luată pe server și rămâne.** Anularea camerei, refuzul permisiunii
sau închiderea paginii doar *amână* aceeași fotografie, nu o evită — următoarea
încercare o cere din nou, până este făcută. Altfel, un angajat ar putea apăsa pur
și simplu din nou *Pontare* și ar reîncerca norocul.

Un administrator care pontează pe cineva din panou nu este niciodată întrebat, ceea
ce este și soluția pentru o cameră defectă.

<a id="settings-kiosk-code"></a>

### Codul de kiosk

Codul companiei pe care angajații îl tastează la kiosk, de forma `AB1234`. Este
generat la crearea companiei și poate fi regenerat aici — după care **toți trebuie
să folosească noul cod**.

<a id="settings-autoclockout"></a>

### Pontare automată de ieșire, global

O oră la care oricine este încă pontat oriunde în companie este pontat la ieșire,
cu o oră diferită opțională pentru weekend. [Regula unui
șantier](#sites-autoclockout) are prioritate.

Fiecare pontare automată de ieșire scrie o linie de audit în nota pontajului, cu
regula și ora pentru care a fost configurată, deci o închidere automată nu este
niciodată imposibil de deosebit de un angajat care își încheie singur tura.

<a id="settings-break"></a>

### Programul pauzei

Un interval neplătit scăzut din orice pontaj care îl cuprinde, păstrând orele
lucrate corecte fără ca nimeni să se ponteze la ieșire pentru masă.

<a id="settings-workschedule"></a>

### Programul de lucru

Ziua standard a companiei. Orice depășește acest program contează drept **ore
suplimentare** și este desenat mov în calendare și fișe. Este și valoarea de
rezervă pentru orele precompletate la adăugarea unui pontaj, dacă nu există ture
definite.

<a id="settings-autofill"></a>

### Completarea automată a turei la pontare

Când cineva pontează într-o zi **fără tură repartizată**, se scrie tura funcției
sale al cărei început este cel mai apropiat de ora pontării — înainte sau după.

- **Nu modifică niciodată o zi deja repartizată.** De acelea se ocupă detectarea
  schimbării de tură de mai jos, iar două mecanisme care scriu aceeași zi s-ar
  anula reciproc.
- **Doar turele propriei funcții** sunt candidate. Un *Recepționer* care pontează
  la 08:14 primește tura sa de la 08:30, nu cea de la 08:00 care aparține altei
  funcții.
- **Nu se scrie nimic dincolo de două ore** de la cel mai apropiat început. Cu
  ture la 08:00, 09:00, 12:30 și 13:30, o pontare la 20:00 este „cea mai
  apropiată" de 13:30 — la șase ore și jumătate — iar repartizarea aceea ar fi o
  presupunere. Ziua rămâne goală și jurnalul companiei consemnează motivul.
- Zilele cu **concediu aprobat** sunt sărite, fiindcă planificarea desenează
  oricum concediul peste tură.
- Se declanșează la o pontare de la kiosk sau terminal și când un administrator
  pontează pe cineva, dar **nu** când un administrator introduce un pontaj
  istoric cu ore explicite — acolo decideți deja dvs.

Zilele completate sunt marcate **⊕ Completat automat** în tabelul planificării, cu
ora pontării și tura potrivită în notă, deci fiecare este verificabilă.

> **Acest lucru schimbă exportul PONTAJ.** Ambele foi sunt orientate pe program,
> deci o zi fără repartizare este goală în ambele. Zilele pe care completarea
> automată le repartizează poartă acum ore planificate acolo unde înainte erau
> goale. De obicei acesta este chiar scopul activării — dar este un document de
> salarizare care își schimbă forma, deci activați-o deliberat, nu în mijlocul
> lunii.

<a id="settings-shiftdetect"></a>

### Detectarea schimbării de tură

O sarcină nocturnă care mută repartizarea de tură a unei zile atunci când pontajul
real se potrivește clar mai bine cu o **altă** tură.

Intenționat prudentă: se uită doar la pontaje încheiate, la funcții cu două sau mai
multe ture, nu atinge niciodată o zi **schimbată** manual și nu inventează
niciodată o repartizare acolo unde planificarea era goală — gol înseamnă *fără
plan*.

Deosebește structural o schimbare reală de tură de ore suplimentare sau de o
întârziere, nu prin praguri: suplimentarele produc un interval lucrat care
*cuprinde* tura repartizată, iar o întârziere produce unul *în interiorul* ei, deci
în ambele cazuri tura repartizată rămâne cea mai potrivită. Două ture aproape
identice (07–16 față de 08–17) nu sunt schimbate niciodată, ceea ce este corect,
fiindcă acolo distincția nu contează.

<a id="settings-lock"></a>

### Pontaj blocat

Îngheață pontarea: apare un banner roșu, pontarea în masă este limitată la ziua de
azi și editările pe zile trecute sunt refuzate. Folosiți-o după ce o lună a plecat
la salarizare.

<a id="settings-editpast"></a>

### Zile editabile în trecut

Câte zile în urmă poate fi adăugat sau corectat un pontaj. Celulele din afara
intervalului sunt gri în calendare.

<a id="settings-notifications"></a>

### Notificări

- **Avertizări de pontare pe șantier** și **rapoarte lunare pe email**, cu o
  limită zilnică de trimitere, ca rulările suplimentare să nu poată spama pe
  nimeni.
- **Notificări de autentificare din IP nou** — un email când un administrator se
  autentifică de la o adresă nemaivăzută.

<a id="settings-admins"></a>

### Conturi de administrator

Creați și editați administratori, dezactivați-i și resetați o parolă. Un
administrator dezactivat nu se poate autentifica și nu poate folosi resetarea
parolei pentru a reveni.

<a id="settings-site-managers"></a>

### Manageri de șantier

Un administrator restrâns, limitat la șantierele pe care le atribuiți.

- **Secțiuni** — bifați care dintre cele zece secțiuni le pot deschide. Implicit
  sunt *Pontaj* și *Angajați*. Setările nu pot fi acordate niciodată.
- **Vizibilitatea partenerilor** — dezactivată, văd doar angajații care **nu** sunt
  asociați unui partener. Aceasta filtrează *angajați*, nu pagini, și este diferită
  de dreptul de a deschide secțiunea Parteneri.
- Indiferent de secțiuni: **nu pot descărca nicio fișă de pontaj** și **nu pot
  importa CSV-ul de angajați**.

<a id="settings-partner-managers"></a>

### Manageri de partener

Limitați la partenerii pe care îi atribuiți, cu o pereche fixă de secțiuni —
**Pontaj** și **Angajați** — care nu poate fi modificată.

---

<a id="password"></a>

## Parola dvs.

**Schimbă parola** se află în bara de jos. Aveți nevoie de parola actuală, iar cea
nouă trebuie să aibă minimum 8 caractere.

Schimbarea ei **încheie sesiunile din celelalte browsere**. Acesta este scopul:
dacă parola veche fusese compromisă, și sesiunea deschisă cu ea dispare.

---

*Acest ghid descrie aplicația așa cum este instalată. Dacă un ecran nu corespunde
cu ce este scris aici, aplicația are dreptate și această pagină trebuie
actualizată.*
