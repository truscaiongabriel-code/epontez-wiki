# Ghid Manager de Șantier

Ce poate face un manager de șantier în epontez și unde sunt limitele.

> **Ancorele sunt stabile** și comune tuturor ghidurilor: un subiect are același
> `id` aici ca în `admin_wiki_ro.md` și ca în versiunile englezești. Un link către
> `site_manager_wiki_ro.md#clock-calendar` duce la același subiect.

**Cuprins** — [Ce este un manager de șantier](#role) · [Autentificare](#login) ·
[Navigare](#navigation) · [Status](#status) · [Pontaj](#clock) ·
[Angajați](#employees) · [Program](#program) · [Planificare](#planning) ·
[Șantiere](#sites) · [Incidente](#incidents) · [Parteneri](#partners) ·
[Fișe pontaj](#timesheets) · [Concedii](#timeoff) · [Terminale](#terminals) ·
[Plan](#plan) · [Parola dvs.](#password)

---

<a id="role"></a>

## Ce este un manager de șantier

Un administrator restrâns. Două lucruri separate stabilesc ce vedeți.

**1. Șantierele dvs.** Un administrator vă atribuie unul sau mai multe șantiere,
iar datele dvs. sunt limitate la ele — angajații al căror șantier implicit este
unul dintre ale dvs., pontajele lor, concediile lor.

**2. Secțiunile dvs.** Același administrator bifează care dintre cele zece
secțiuni le puteți deschide. Implicit sunt doar **Pontaj** și **Angajați**, deci
dacă o secțiune descrisă mai jos lipsește din bara de navigare, nu v-a fost
acordată și acea parte a ghidului nu vi se aplică.

Trei limite se aplică **oricare** ar fi secțiunile acordate:

| Limită | De ce |
|---|---|
| **Setările nu pot fi deschise** | Este locul unde se creează managerii de șantier |
| **Nicio descărcare de fișe** — PDF, Excel sau CSV salarizare | Fișierul de salarizare conține tarife orare. Restricția este pe server, nu prin ascunderea unui buton |
| **Niciun import CSV de angajați** | Scrie la nivelul întregii companii și poate schimba cine este activ, ocolind limitarea pe șantiere. Exportul funcționează |

O a patra se poate aplica: dacă **vizibilitatea partenerilor** este dezactivată
pentru contul dvs., vedeți doar angajații care **nu** sunt asociați unui partener.

Două secțiuni au putere la nivelul întregii companii când sunt acordate, deci se
poate ca ele să nu fie: **Program** (funcțiile și turele afectează pe toți) și
**Terminale** (asocierea unui cititor cu un șantier decide unde ajung pontările).

---

<a id="login"></a>

## Autentificare

Accesați `/login` cu emailul și parola.

- **Parolă uitată** — *Ați uitat parola?* trimite pe email un link de unică
  folosință, valabil o perioadă limitată.
- **Cont dezactivat** — primiți un mesaj specific, iar resetarea parolei nu ajută.
  Cereți unui administrator să vă reactiveze.
- Schimbarea parolei încheie sesiunile din celelalte browsere.
- **Rămâneți conectat cât timp lucrați.** Sesiunea durează o oră și se reînnoiește
  la fiecare pagină deschisă, deci munca continuă nu vă deconectează; o oră fără
  nicio acțiune o face.

Selectorul de limbă — **română, engleză, germană** — este în dreapta sus.

---

<a id="navigation"></a>

## Navigare

Apar doar secțiunile acordate:

| Română | Engleză |
|---|---|
| Status | Dashboard |
| Pontaj | Clock |
| Angajați | Employees |
| Program | Schedules |
| Șantiere / Sedii | Sites |
| Parteneri | Partners |
| Fișe pontaj | Timesheets |
| Concedii | Time off |
| Terminale | Terminals |
| Plan | Plan |

Unele companii sunt configurate să folosească **sediu** în loc de **șantier** în
toată interfața, deci ecranele dvs. pot diferi de cele ale unui coleg de la altă
companie.

Numele dvs., *Schimbă parola* și *Deconectare* sunt în bara de jos.

---

<a id="status"></a>

## Status

Ziua de azi pe scurt, **doar pentru șantierele dvs.**

- **Pontați azi** — angajați distincți cu un pontaj valid astăzi
- **Ore luna aceasta** — orele încheiate până acum, după scăderea pauzei
- **Pontați acum** — pontaje deschise în acest moment
- **Angajați activi** — efectivul din aria dvs.

Apăsați cardurile din rândul al treilea pentru a le extinde: **Nepontați în
ultimele 5 zile lucrătoare** și **În concediu azi**.

Graficele acoperă ultimele 30 de zile, câte o culoare per șantier. **Pontați în
acest moment** listează pontajele deschise, cu orele și notele.

**Pontaje neînchise** avertizează despre oricine are un pontaj deschis din altă
zi — de obicei o pontare uitată la plecare.

---

<a id="clock"></a>

## Pontaj

> Trebuie să existe cel puțin un șantier activ înainte de a putea ponta pe cineva.

Angajații sunt grupați în secțiuni după șantierul implicit, ordonate **alfabetic**
și mereu în același loc. Numele care conțin numere se ordonează natural, deci
*Sediu T5* apare înaintea lui *Sediu T13*.

<a id="clock-visiting"></a>

### Cineva care a lucrat la alt șantier

Un angajat care a pontat în altă parte decât la șantierul implicit — de obicei
prezentând amprenta la terminalul de acolo — apare **de două ori**: la șantierul
lui și la șantierul unde a lucrat, cu eticheta **(în vizită)**.

- Oricare rând afectează aceeași persoană.
- Eticheta apare doar dacă angajatul *are* un șantier implicit de unde să
  lipsească.
- Fiecare rând arată doar pontajele secțiunii sale, deci un șantier nu pare
  niciodată să aibă muncă petrecută în altă parte.
- Rândul unei persoane pontate în altă parte apare ca nepontat, cu o notă
  discretă, iar butonul este dezactivat.

<a id="clock-calendar"></a>

### Vizualizarea calendar

O coloană per angajat, un rând per zi.

| Celulă | Înseamnă |
|---|---|
| **HH:mm – HH:mm** | Încheiat — apăsați pentru editare |
| **HH:mm –** | Încă pontat — apăsați pentru ieșire sau editare |
| Dungi diagonale | Concediu |
| Gri | În afara intervalului editabil stabilit de un administrator |

<a id="clock-colours"></a>

### Ce înseamnă culorile

| Culoare | Înseamnă |
|---|---|
| **Verde** | O zi obișnuită |
| **Mov** | Peste plan — vezi mai jos |
| **Roz / ambră** | Weekend / sărbătoare legală |
| **Triunghi galben în colț** | Intrare după începerea turei sau ieșire înainte de final |

**Movul** înseamnă ore suplimentare față de programul companiei, ore de weekend
sau sărbătoare, **sau** muncă în afara turei repartizate — intrare cu peste **15
minute** mai devreme sau ieșire cu peste 15 minute mai târziu.

Într-o zi fără tură repartizată, ultima regulă este măsurată față de **cel mai
larg interval pe care îl lucrează vreodată funcția respectivă**, deci cineva aflat
la o tură de după-amiază neplanificată nu este marcat doar pentru că a fost în
afara celei de dimineață.

Movul înseamnă *mai mult* decât s-a planificat; întârzierea sau plecarea devreme
apar prin **triunghiul galben**. Treceți cursorul peste o celulă pentru motiv.

<a id="clock-select"></a>

### Selectarea celulelor

Apăsați celule pentru a le selecta (devin albastre), apoi alegeți **Pontare
intrare**, **Pontare ieșire**, **Final** (ambele capete ale unei zile trecute) sau
**Concediu**. Zilele cu concediu aprobat și persoanele deja pontate nu pot fi
selectate.

Un pontaj **invalidat** nu este prezență și este ignorat de calendar, de statusul
rândului, de selecție și de totaluri. Un pontaj *deschis* contează totuși ca în
curs, fiindcă este singurul mod de a ponta persoana la ieșire.

<a id="clock-table"></a>

### Vizualizarea tabel

O listă per șantier cu statusul, ultima pontare, șantierul și nota. **Pontare
intrare** cere un șantier (cel implicit este preselectat) și o notă opțională;
**Pontare ieșire** cere o notă. Etichetele de deasupra fiecărui tabel numără
**Încheiate**, **În curs** și **Nepontate**.

<a id="clock-manual"></a>

### Adăugarea manuală a unui pontaj

**+ Adaugă pontaj** înregistrează o intrare istorică — soluția pentru o pontare
ratată. Stabiliți intrarea, opțional ieșirea, șantierul și o notă.

<a id="clock-shift-times"></a>

### Completarea orelor din tură

Deasupra câmpurilor de ore apare un rând de **etichete de tură** — `Tura B ·
08:00–16:00` — cu turele funcțiilor angajaților selectați. Apăsați una și orele se
completează, rămânând editabile. Ieșirea unei ture de noapte ajunge în ziua
următoare. Dacă firma nu definește ture, nu apar etichete și câmpurile revin la
programul de lucru al companiei sau la 08:00–17:00.

<a id="clock-edit"></a>

### Editarea unei zile

Apăsarea unei celule încheiate deschide dialogul; alegeți pontajul dacă sunt mai
multe. Puteți corecta ambele ore. **Nota existentă nu poate fi modificată** —
scrieți în **Adaugă notă**, iar numele dvs. și ora sunt marcate automat. Notele se
completează, nu se suprascriu.

<a id="clock-bulk"></a>

### Acțiuni în masă

| Tip | Ce face |
|---|---|
| Pontare intrare | O intrare în fiecare zi selectată |
| Pontare ieșire | Închide pontajul deschis din fiecare zi |
| Final | Ambele capete în fiecare zi |
| Concediu | O cerere de concediu per zi |

**Acordarea concediului fără a selecta celule** — apăsați *Adaugă concediu* cu
nimic selectat și datele de început și sfârșit devin editabile, deci un interval
poate fi acordat direct. Dacă selectați mai întâi celule, datele sunt needitabile,
fiindcă acolo grila este intervalul.

Un singur șantier, ore și notă pentru tot lotul. Conflictele sunt raportate înainte
de a se salva ceva.

<a id="clock-lock"></a>

### Bannerul roșu de blocare

Dacă un administrator a blocat pontarea, apare un banner roșu: pontarea în masă
este limitată la ziua de azi și editările pe zile trecute sunt refuzate. De obicei
înseamnă că luna a plecat la salarizare.

---

<a id="employees"></a>

## Angajați

Angajații al căror șantier implicit este unul dintre ale dvs., grupați după
șantier.

<a id="employees-filter"></a>

### Filtrare

Etichete — **Activi / Inactivi / Toate** — plus un filtru de partener dacă există
parteneri și aveți dreptul să îi vedeți. Ambele se păstrează în adresă.

<a id="employees-columns"></a>

### Coloanele se adaptează singure

**O coloană pe care niciun angajat nu o folosește este ascunsă.** Dacă nimeni nu
are tarif orar, nu există coloana Tarif orar. Nume, Status, Creat și Acțiuni se
afișează mereu. O notă sub tabele spune ce este ascuns și cum se readuce. Setul nu
se schimbă când comutați eticheta Activi/Inactivi/Toate.

<a id="employees-fingerprint"></a>

### Coloana Amprentă

| Afișat | Înseamnă |
|---|---|
| **Inactiv** | Nu are voie să înregistreze un dispozitiv |
| **Înrolare în așteptare** (ambră) | Are voie, nimic înregistrat — **PIN-ul îl pontează în continuare** |
| **2 dispozitive** | Înregistrat, iar PIN-ul **nu mai funcționează pentru pontare** |

<a id="employees-add"></a>

### Adăugarea unui angajat

**Nume de familie** și **Prenume** sunt obligatorii. Apoi funcția, emailul,
telefonul, data nașterii, șantierul implicit, partenerul, tariful orar, zilele de
concediu anual și un **PIN Kiosk** (4–6 cifre, opțional, se poate seta ulterior).
Un nume duplicat în companie este refuzat.

> Pentru a muta un angajat existent la alt șantier, folosiți **Transfer** din
> listă, nu acest formular.

<a id="employees-edit"></a>

### Editarea unui angajat

- **ID sistem** este needitabil și este singurul identificator al unui angajat.
- **Numele** este editabil doar în **48 de ore** de la creare, pentru că
  exporturile se potrivesc pe el.
- **Activ** cere un **Motiv**, scris în jurnalul de activitate cu numele dvs. și
  data.
- **Pontaj automat** creează automat pontajul zilei — are nevoie de șantier,
  început și final; doar zile lucrătoare, sărind pe cine este deja pontat sau în
  concediu aprobat.
- **Localizare auto** captează GPS-ul la pontarea de la kiosk. **Cu aceasta
  activă, coordonatele sunt obligatorii** — cine blochează locația nu se poate
  ponta.
- **PIN Kiosk** poate fi setat sau șters.
- **Șterge datele de localizare** elimină GPS-ul din pontajele acestui angajat
  pentru o cerere GDPR, păstrând pontajele.

<a id="employees-passkey"></a>

### Autentificare cu amprenta pe telefonul angajatului

Activarea **Amprentă** permite unui angajat să se autentifice la kiosk cu senzorul
propriului telefon. Înrolarea cere **două elemente**: PIN-ul lui *și* un cod de
unică folosință emis de dvs. aici, afișat **o singură dată**. Angajatul deschide
apoi `/kiosk`, alege *Configurează amprenta pe acest dispozitiv* și le introduce pe
ambele.

- **Odată ce un dispozitiv este înregistrat, PIN-ul nu mai funcționează pentru
  pontare**, dar funcționează în continuare pentru vizualizarea orelor și cererile
  de concediu. Un PIN poate fi dat altcuiva; o amprentă, nu.
- **Dezactivarea Amprentei șterge toate dispozitivele înregistrate** — o revocare,
  nu o pauză.
- **Revocarea unui dispozitiv restabilește imediat PIN-ul** — calea de întoarcere
  pentru un telefon pierdut, împreună cu pontarea de către dvs. din panou.
- Este gândită pentru **telefoane personale**. Pe o tabletă comună orice amprentă
  înrolată deblochează orice passkey de pe ea, deci nu ar împiedica un angajat să
  ponteze un altul.

<a id="employees-csv"></a>

### Export CSV

**Export** oferă Activi, Inactivi sau Toate, cu titluri fixe în engleză.

> **Importul nu este disponibil managerilor de șantier.** Scrie la nivelul
> întregii companii și poate schimba cine este activ, ocolind limitarea dvs. pe
> șantiere.

<a id="employees-pdf"></a>

### PDF

**↓ PDF** descarcă angajații dvs. activi, grupați după șantier.

---

<a id="program"></a>

## Program

Doar dacă este acordată — această secțiune afectează toată companiia, nu doar
șantierele dvs.

<a id="program-roles"></a>

### Funcții

Posturile companiei, fiecare cu turele sale și cu numărul de angajați care le
ocupă. Adăugați, redenumiți (o redenumire peste un nume existent oferă
**unificarea**) sau dezactivați. Ștergerea este refuzată cât timp cineva ocupă
funcția. Un card ambră listează angajații activi **fără funcție**, lucru care
merită rezolvat, fiindcă funcția leagă o persoană de ture.

<a id="program-shifts"></a>

### Biblioteca de ture

Turele aparțin **companiei**, iar o funcție poate lucra mai multe, în timp ce o
tură poate deservi mai multe funcții. Creați tura o dată, apoi atașați-o
funcțiilor din oricare parte.

- Un final egal sau anterior începutului înseamnă că tura **trece peste miezul
  nopții**; permis și marcat *peste noapte*.
- Două ture pot avea același nume — selectoarele arată `nume · 07:00–16:00`. Doar
  același nume **și** aceleași ore este refuzat.
- Turele sunt **informative**: niciun calcul de ore, suplimentare sau costuri nu
  citește o tură. Ele alimentează planificarea, marcajele de respectare și fișele
  PONTAJ.
- Nimeni nu are o tură permanentă; este un fapt **zilnic**, stabilit în
  [Planificare](#planning).
- Ștergerea unei ture șterge repartizările ei pe zile, deci acele zile devin
  goale.

<a id="program-export"></a>

### Exportul PONTAJ

Selectorul de lună, butonul verde **Descarcă Excel** și două filtre sunt în antet:
**Funcție** (*Toate funcțiile* implicit) și **Partener** (*Fără partener*
**implicit**, *Toți partenerii* sau unul anume).

> Implicit, partenerul **exclude colaboratorii**, pentru că o fișă PONTAJ este un
> document de salarizare pentru personalul propriu. Verificați ce este selectat
> înainte de a trimite fișierul.

Două foi cu structuri identice: **Vedere planificare**, planul lunii; și **Vedere
pontaj**, același plan trunchiat la ziua de azi și adnotat cu prezența — o zi
programată în care nu s-a lucrat înregistrează **0 ore** și este desenată roșu
închis cu o notă *Absent*. Ambele raportează orele **planificate**; o zi fără nimic
planificat este goală în ambele, chiar dacă cineva a pontat. Titlurile sunt mereu
în română, pentru că structura fișierului este un contract cu cel care o primește.
Concediul aprobat scrie codul în *Inceput* și înregistrează 0 ore. Limitat la 450
de angajați.

---

<a id="planning"></a>

## Planificare

> **Acum puteți edita.** Acordarea secțiunii Program lăsa Planificarea lizibilă
> dar inutilă pentru dvs. — orice modificare era refuzată. Acum puteți repartiza,
> goli, schimba și repartiza în masă ture pentru **angajații al căror șantier
> implicit este unul dintre ale dvs., plus oricine nu are deloc un șantier
> implicit**. Partea a doua contează: fără ea, un angajat neatribuit nu ar putea
> fi planificat de nimeni în afară de un administrator complet, iar aceia sunt
> exact oamenii care au cel mai des nevoie de acoperire.
>
> Un angajat de la alt șantier este refuzat pe nume. Un **schimb necesită ambele
> părți** în aria dvs., fiindcă rescrie zilele a două persoane, iar a avea una
> dintre ele nu înseamnă autoritate asupra celeilalte.
>
> Numele dvs. este înregistrat pe tot ce modificați, în repartizare și în
> jurnalul companiei.
>
> Biblioteca de **ture** rămâne doar pentru administratori. O tură aparține
> companiei, deci crearea sau ștergerea ei afectează fiecare șantier și nu poate
> fi limitată la ale dvs. — repartizați ture, nu le definiți.

Se ajunge din butonul **Planificare** de pe o funcție din Program. Se acordă
împreună cu Program.

<a id="planning-grid"></a>

### Grila

Angajații pe verticală, zilele pe orizontală — forma care răspunde la *este
acoperită fiecare noapte?*. Fiecare tură are o culoare stabilă, weekendurile sunt
roz, sărbătorile ambră, iar un **✓** mov marchează o zi lucrată **fără nimic
planificat**. Opțiunea **Toate funcțiile** arată pe toți, cu fiecare tură listată o
singură dată în legendă.

<a id="planning-automation"></a>

### Două etichete în partea de sus

Deasupra grilei, două etichete arată dacă mecanismele automate sunt active — verde
pentru activ, gri pentru inactiv. Ambele scriu în planificare fără ca nimeni să
apese nimic, deci dacă o grilă s-a schimbat peste noapte, ele spun care ar fi
putut să o facă.

| Etichetă | Ce face |
|---|---|
| **⊕ Completare automată a turei la pontare** | Repartizează o zi **goală** când cineva pontează în ea |
| **◎ Detectare schimbare tură** | Mută o zi **deja repartizată** când pontajul se potrivește mai bine cu altă tură |

Ambele se activează per companie de către un administrator, în Setări — pe care nu
le puteți deschide, deci etichetele sunt modul în care aflați.

<a id="planning-cells"></a>

### Citirea unei celule

Fiecare celulă poartă culoarea turei sale și afișează numele scurt peste orele de
început și final. Trecerea cursorului arată toată ziua: tura și orele ei, data, ce
s-a pontat efectiv (sau **Fără pontaj**) și verdictul de respectare a programului.
Simbolul din colț este acel verdict — ✓ verde la timp, ✓ ambră întârziat sau
plecat devreme, ✗ roșu absent.

<a id="planning-select"></a>

### Selectarea mai multor celule

**Celulele libere pot fi apăsate pentru a construi o selecție**, apoi
**Repartizează tura (n)** aplică o singură tură tuturor.

- Doar celulele libere intră în selecție; una cu tură sau concediu deschide
  dialogul ca înainte.
- **O singură funcție pe rând** — o tură aparține unei funcții, deci apăsarea
  într-alta începe o selecție nouă.
- Nimic selectat? Totul se comportă ca înainte.
- Se aplică aceeași limitare pe șantiere: o selecție poate conține doar angajați
  pe care îi puteți planifica.

<a id="planning-assign"></a>

### Repartizarea unei ture

Apăsați o celulă sau folosiți De la/Până la pentru un interval.

- **Un interval este împărțit în serii de zile lucrătoare** — 2–13 februarie
  devine două repartizări, lăsând weekendurile și sărbătorile goale dacă nu bifați
  *include zilele nelucrătoare*.
- **O zi singură este respectată mereu ca atare**, așa puneți pe cineva într-o
  sâmbătă.
- O repartizare **fără dată de final** acoperă fiecare zi, inclusiv weekendurile.
- **Suprapunerile sunt remodelate, nu refuzate**: nopți de pe 10 încheie o
  repartizare de dimineață fără final pe 9.
- Primiți o **previzualizare** și o confirmare oricând s-ar schimba ceva.

<a id="planning-switch"></a>

### Schimbul între două persoane pentru o zi

Pentru o singură zi, **Schimbă tura** listează colegii aflați în altă tură în acea
zi. Un schimb decupează **o singură zi** fiecăruia, lasă neatins restul ambelor
planificări și marchează ambele **Schimbat**, cu o notă despre cine a făcut
schimbul și cu cine. Cei doi trebuie să ocupe aceeași funcție și să fie în ture
diferite. O zi schimbată nu este niciodată suprascrisă de detectarea automată.

<a id="planning-clear"></a>

### Golirea unei zile

**Golește ziua** decupează o zi din repartizarea din jur, împărțind-o dacă ziua
este la mijloc. Nu readuce ce a fost remodelat anterior.

<a id="planning-timeoff"></a>

### Alocarea concediului din planificare

**Alocă concediu** acoperă un interval pentru mai mulți angajați; în dialogul
celulei, un comutator **Tură / Concediu** acoperă ziua apăsată. O zi deja în
concediu aprobat oferă **Elimină concediul**, care **anulează**, nu șterge — pista
de audit supraviețuiește și tura de dedesubt revine singură. Puteți repartiza o
tură într-o zi deja în concediu; planificarea de dedesubt se editează în
continuare.

<a id="planning-table"></a>

### Tabelul de sub grilă

Câte un rând per **zi programată** — `Angajat | Tură | Zi | Intrare | Ieșire |
Status | Notă`, unde Intrare și Ieșire sunt prima pontare și ultima ieșire din acea
zi.

**Fiecare angajat este restrâns**; apăsați pe rândul său pentru a-i deschide
zilele. Antetul păstrează totalurile — ✓ la timp, ✓ întârziat, ✗ absent, ✓
neplanificat — și numărul de zile ascunse, deci cineva cu un ✗ roșu rămâne o linie
vizibilă.

Coloana **Status** spune cum a ajuns ziua să fie repartizată: gol pentru o
persoană, **⇄ Schimbat** pentru un schimb de o zi, **⊕ Completat automat** când o
pontare a repartizat-o, **◎ Detectat automat** când detectarea a mutat-o.

**Tabelul se oprește la ziua de azi**, în timp ce grila arată toată luna: toate
coloanele în afară de Tură raportează ce s-a întâmplat, iar o zi viitoare nu are
nimic din asta. O lună trecută este completă; o lună viitoare arată un tabel gol și
o grilă plină. Apăsarea unei celule viitoare din grilă deschide tot dialogul de
repartizare.

| Nuanță | Înseamnă |
|---|---|
| **Roșu** | Planul a fost încălcat — intrare târzie, ieșire devreme sau niciun pontaj într-o zi a cărei tură începuse deja |
| **Mov** | Nu exista plan — **Neplanificat**, cu opțiunea *Repartizează tura* |

„Începuse deja” înseamnă că ziua a trecut sau că este azi și ora de început a
trecut. Concediul aprobat nu este absență și are prioritate față de ambele.

---

<a id="sites"></a>

## Șantiere

Șantierele atribuite dvs.

<a id="sites-coords"></a>

### Coordonatele

Punctul de pe hartă al unui șantier face posibilă verificarea prezenței. Fără el, o
pontare nu poate fi evaluată, oricât de strâmtă ar fi raza, deci acele rânduri sunt
marcate ambră cu **Fără coordonate**. Prezența în afara șantierului este
**înregistrată, nu blocată** — o dovadă pentru cel care verifică fișa, nu o
barieră.

<a id="sites-autoclockout"></a>

### Pontare automată de ieșire per șantier

O oră la care oricine este încă pontat la acel șantier este pontat la ieșire. Are
prioritate față de regula companiei.

<a id="sites-status"></a>

### Activ, inactiv, ascuns

Etichetele filtrează **Active / Inactive / Toate**. Un șantier trebuie să fie
inactiv înainte de a putea fi ascuns, iar **doar un super administrator poate
anula ascunderea**. Fiecare modificare adaugă o linie de audit în notele
șantierului.

---

<a id="incidents"></a>

## Incidente

Un registru per șantier pentru Legea 319/2006, disponibil oricărui rol care poate
vedea Șantiere.

<a id="incidents-add"></a>

### Înregistrarea unui incident

| Câmp | Opțiuni |
|---|---|
| **Tip** | Accident · Eveniment evitat · Întâmplare periculoasă · Boală profesională |
| **Gravitate** | Minor · Moderat · Grav · Mortal |
| **Data incidentului** / **Data înregistrării** | Când s-a petrecut / a fost consemnat |
| **Descriere** | Obligatorie |
| **Angajați implicați** | Dintre angajații repartizați la acel șantier |
| Martori, Măsuri corective | Opționale |
| **Raportat autorităților** | Da/nu |

<a id="incidents-pdf"></a>

### PDF-ul registrului

**PDF incidente** cere o lună și produce un registru A4 landscape pentru acel
șantier și acea lună, spunându-vă dacă nu există nimic de raportat în loc să
producă un fișier gol.

---

<a id="partners"></a>

## Parteneri

Doar dacă este acordată. Firme colaboratoare, fiecare cu șantierele sale ca
subrânduri.

Asocierea unui angajat cu un partener are două consecințe: **nu poate cere
concediu** (este treaba angajatorului său, refuzat atât în panou, cât și la kiosk)
și **câmpurile de concediu îi sunt dezactivate**.

De reținut că **filtrul de partener** din paginile Angajați și Pontaj filtrează
*angajați*, nu pagini — este diferit de dreptul de a deschide această secțiune.
Dacă vizibilitatea partenerilor este dezactivată pentru contul dvs., vedeți doar
angajații fără partener.

---

<a id="timesheets"></a>

## Fișe pontaj

Doar dacă este acordată. Ore lună cu lună, pentru șantierele dvs.

<a id="timesheets-filters"></a>

### Ce vedeți

Selector de lună plus filtre pentru **șantier**, **angajat** și **partener**.

<a id="timesheets-read"></a>

### Citirea tabelului

Fiecare angajat este un bloc cu pontajele sale, cu subtotaluri zilnice și un total
lunar.

| Marcaj | Înseamnă |
|---|---|
| Eticheta **Auto** | Creat de sarcina de pontaj automat |
| **Rând mov** | Suplimentare, weekend, sărbătoare sau în afara turei — [aceleași reguli](#clock-colours) ca în calendar |
| Tăiat | Marcat invalid; nu se numără |
| Eticheta partenerului | Asociat unui colaborator |

<a id="timesheets-gps"></a>

### Indicatoarele de locație

O tură are **două** poziții, deci un rând poate arăta indicatoare **Intrare** și
**Ieșire**, fiecare ducând la OpenStreetMap în acel punct.

| Indicator | Înseamnă |
|---|---|
| **Verde** | Pe șantier |
| **Roșu** | În afara șantierului |
| **Gri** | Există o poziție, dar șantierul nu avea coordonate față de care să fie evaluată |
| Niciunul | Nu s-a captat nicio poziție |

**Verdictul este înghețat în momentul pontării** — modificarea razei ulterior
afectează doar pontările noi. Coordonatele se șterg după 180 de zile sau la cerere
din pagina angajatului.

<a id="timesheets-edit"></a>

### Corectarea unui pontaj

Apăsați un rând pentru a-i corecta orele sau a-l marca invalid. Notele se adaugă,
cu marcă de audit. Revalidarea unei intrări invalide reia verificarea de
suprapunere.

<a id="timesheets-download"></a>

### Descărcări

> **Nu sunt disponibile managerilor de șantier.** PDF-ul, Excelul și CSV-ul de
> salarizare sunt toate refuzate pentru acest rol, pentru că fișierul de salarizare
> conține tarife orare. Restricția este pe server, deci nici un link direct nu
> funcționează. Cereți fișierul unui administrator.

---

<a id="timeoff"></a>

## Concedii

Doar dacă este acordată. O cerere în așteptare pune un asterisc pe tabul din
navigare.

<a id="timeoff-types"></a>

### Tipuri

`CO` concediu de odihnă · `CFP` fără plată · `MEDICAL` medical · `MARRIAGE`
căsătorie · `BLOOD_DONATION` donare de sânge · `SPECIAL_EVENTS` evenimente
speciale · `MILITARY` militar · `FUNERAL` deces · `CHILD_BIRTH` naștere ·
**`MATERNITY` maternitate** · `EXCUSED` motivat · `ABSENT` absent.

**Maternitatea** este separată de *Naștere copil*: aceasta din urmă este perioada
de câteva zile din jurul nașterii, maternitatea este perioada statutară lungă, iar
un pontaj le raportează separat.

<a id="timeoff-read"></a>

### Citirea tabelului

Concediul se stochează **câte un rând per zi lucrătoare**, deci există coloane
separate **Data**, **Ziua** și **Zile**, iar etichetele de sumar numără zile
lucrătoare. O cerere peste un weekend nu umflă numărul.

<a id="timeoff-actions"></a>

### Acțiuni

**Aprobă**, **Respinge** sau **Anulează**; se înregistrează cine a depus cererea.

**Doar concediul aprobat înlocuiește o tură programată.** O cerere în așteptare
păstrează tura vizibilă în planificare, marcată cu un punct mic. Înlocuirea are loc
la citirea planificării și a fișelor, niciodată scrisă definitiv, deci anularea
concediului readuce tura singură. Există un **PDF** per cerere, pentru semnare.

---

<a id="terminals"></a>

## Terminale

Doar dacă este acordată — această secțiune are putere la nivelul companiei, fiindcă
asocierea unui cititor cu un șantier decide unde ajung pontările lui.

<a id="terminals-why"></a>

### De ce un terminal și nu o tabletă

Un terminal face **identificare 1:N**: angajatul prezintă un deget și dispozitivul
răspunde *cine este*, fără ca nimeni să fi fost selectat înainte. Este singura
soluție care împiedică efectiv un angajat să ponteze un altul. În plus, face
**șantierul sigur**, pentru că cititorul este fixat pe el, și **nicio amprentă nu
părăsește dispozitivul** — se stochează doar un număr care leagă o poziție din
terminal de un angajat.

<a id="terminals-mappings"></a>

### Asocierea angajaților cu dispozitivul

Tabelul listează fiecare ID de utilizator din dispozitiv, angajatul asociat și dacă
terminalul deține un **card RFID** pentru el (numărul este în indiciu). Rândurile
sunt marcate când cele două părți nu coincid: *asociat aici, absent pe terminal*,
*asociat aici cu «nume» — asociere greșită* sau *neasociat* (de obicei contul
instalatorului).

<a id="terminals-fixname"></a>

### Corectarea unui nume greșit

Dacă modificați numele unui angajat după ce a fost trimis, cititorul păstrează
scrierea veche. Folosiți **Corectează numele pe terminal** pe rândul marcat.

> **Nu** trimiteți angajatul din nou pentru a rezolva asta. O retrimitere este
> refuzată ca ID ocupat și asocierea este ștearsă, după care pontajele lui nu se
> mai potrivesc. *Corectează numele pe terminal* schimbă doar numele și lasă
> amprentele înrolate neatinse.

<a id="terminals-push"></a>

### Trimiterea angajaților către un terminal

**Alege angajați…** deschide o listă cu bifare și căutare; persoanele deja prezente
pe cititor sunt gri, cu ID-ul alocat, iar *Selectează tot* se aplică doar
rândurilor arătate de căutare. **Trimite toți angajații neasociați** este pentru
punerea în funcțiune a unui cititor nou. ID-urile sunt alocate de platformă, peste
cel mai mare număr cunoscut de oricare parte, deci un ID reciclat nu poate atașa
pontajele unui deținător anterior unui angajat nou.

**Amprenta în sine se înrolează manual la cititor** — se trimite doar identitatea.
Comenzile se pun la coadă, pentru că un cititor din rețeaua unui șantier de obicei
nu poate fi apelat din exterior.

<a id="terminals-punchlog"></a>

### Jurnalul de pontări

Cele mai recente zece pontări, iar **Arată încă 10** aduce următoarele zece doar
când este cerut.

| Rezultat | Înseamnă |
|---|---|
| **Intrare / Ieșire** | Normal. Direcția este dedusă, nu preluată din dispozitiv |
| **Utilizator necunoscut** | De la un ID neasociat nimănui |
| **Respins** | Un deget care nu a corespuns nimănui — nu identifică pe nimeni, deci nu poate deveni prezență, dar este consemnat |
| **Duplicat ignorat** | O repetare a unei pontări deja înregistrate |
| **Prea rapid** | O a doua atingere în 60 de secunde |
| **Pontaj deschis vechi** | O pontare mult după o intrare neînchisă: se deschide o tură nouă, iar cea veche este lăsată de corectat |
| **Dispozitiv inactiv** | Dezactivat în aplicație |

O serie de **Respins** fără reușite între ele înseamnă un senzor murdar, un cititor
defect sau cineva neînrolat.

<a id="terminals-offline"></a>

### Online / offline

Eticheta trece pe offline după **5 minute** fără contact sau după trei intervale
proprii de interogare, oricare este mai mare.

---

<a id="plan"></a>

## Plan

Doar dacă este acordată. Logistica muncitorilor — mașini, cazare și cine doarme
unde — cu navigare proprie și autentificare proprie la `/plan/login`.

<a id="plan-cars"></a>

### Mașini

Parcul auto: marcă, model, an, număr de înmatriculare, culoare, locuri, cutie de
viteze, combustibil și data achiziției.

<a id="plan-accommodation"></a>

### Cazare

Nume, adresă, camere, capacitate în persoane și un punct opțional pe hartă. Fiecare
cazare are **camere** numerotate unic în cadrul ei, iar angajații sunt repartizați
pe camere. Export și import CSV disponibile.

<a id="plan-assign"></a>

### Ecranul Planificare

Alegeți un șantier și vedeți angajații lui alături de cazările disponibile, cu
**distanța în km** și ocuparea fiecărei camere. Capacitatea apare ca *locuri* și
*ocupate*, o cameră plină este marcată **Plin**, una goală afișează **Niciun
rezident repartizat**, iar angajații fără șantier apar la **Fără șantier**.
**Exportă repartizările** și **Importă repartizările** mută toată alocarea ca CSV.

<a id="plan-directories"></a>

### Angajați și Șantiere

Registre doar pentru citire, pentru a căuta ceva fără a părăsi această zonă.

---

<a id="password"></a>

## Parola dvs.

**Schimbă parola** este în bara de jos. Aveți nevoie de parola actuală și de
minimum 8 caractere. Schimbarea ei **încheie sesiunile din celelalte browsere**,
ceea ce este și scopul.

---

*Acest ghid descrie aplicația așa cum este instalată. Dacă un ecran nu corespunde
cu ce este scris aici, aplicația are dreptate și această pagină trebuie
actualizată.*
