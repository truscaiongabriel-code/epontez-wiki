# Ghid Manager de Partener

Ce poate face un manager de partener în epontez.

> **Ancorele sunt stabile** și comune celorlalte ghiduri: un subiect are același
> `id` aici ca în ghidul de administrator și cel de manager de șantier, precum și
> în versiunile englezești.

**Cuprins** — [Ce este un manager de partener](#role) · [Autentificare](#login) ·
[Navigare](#navigation) · [Pontaj](#clock) · [Angajați](#employees) ·
[Parola dvs.](#password)

---

<a id="role"></a>

## Ce este un manager de partener

Gestionați oamenii care aparțin unei sau mai multor firme **partenere** —
colaboratorii care lucrează pe șantierele unui client. Un administrator al acelei
companii vă atribuie partenerii de care răspundeți, iar tot ce vedeți este limitat
la angajații asociați lor.

**Secțiunile dvs. sunt fixe, două: Pontaj și Angajați.** Spre deosebire de un
manager de șantier, această pereche nu poate fi schimbată sau extinsă, deci pentru
acest rol nu există Fișe pontaj, Setări, Program, Terminale sau Plan.

O consecință merită știută înainte ca cineva să vă întrebe:

> **Angajații asociați unui partener nu pot cere concediu.** Concediul este treaba
> angajatorului lor, nu a companiei-client, deci este refuzat atât în acest panou,
> cât și la kioskul angajaților. Câmpurile de concediu anual le sunt dezactivate
> din același motiv.

---

<a id="login"></a>

## Autentificare

Accesați `/login` cu emailul și parola.

- **Parolă uitată** — *Ați uitat parola?* trimite pe email un link de unică
  folosință, valabil o perioadă limitată.
- **Cont dezactivat** — primiți un mesaj specific, iar resetarea parolei nu ajută
  cât timp contul este inactiv. Cereți administratorului companiei să vă
  reactiveze.
- Schimbarea parolei încheie sesiunile din celelalte browsere.

Selectorul de limbă — **română, engleză, germană** — este în dreapta sus.

---

<a id="navigation"></a>

## Navigare

Două secțiuni:

| Română | Engleză |
|---|---|
| Pontaj | Clock |
| Angajați | Employees |

Unele companii sunt configurate să folosească **sediu** în loc de **șantier** în
toată interfața, deci etichetele pot diferi între companiile cu care lucrați.

Numele dvs., *Schimbă parola* și *Deconectare* sunt în bara de jos.

---

<a id="clock"></a>

## Pontaj

Pontarea oamenilor partenerului dvs.

> Trebuie să existe cel puțin un șantier activ la compania-client înainte de a
> putea ponta pe cineva.

Angajații sunt grupați în secțiuni după șantierul implicit, ordonate **alfabetic**
și mereu în același loc. Numele care conțin numere se ordonează natural, deci
*Sediu T5* apare înaintea lui *Sediu T13*.

<a id="clock-visiting"></a>

### Cineva care a lucrat la alt șantier

Un angajat care a pontat în altă parte decât la șantierul implicit — de obicei
prezentând amprenta la terminalul de acolo — apare **de două ori**: la șantierul
lui și la șantierul unde a lucrat, cu eticheta **(în vizită)**.

- Oricare rând afectează aceeași persoană; nu sunt două înregistrări.
- Eticheta apare doar dacă angajatul *are* un șantier implicit de unde să
  lipsească.
- Fiecare rând arată doar pontajele secțiunii sale.
- Rândul unei persoane pontate în altă parte apare ca nepontat, cu o notă
  discretă, iar butonul este dezactivat.

<a id="clock-calendar"></a>

### Vizualizarea calendar

O coloană per angajat, un rând per zi a lunii selectate.

| Celulă | Înseamnă |
|---|---|
| **HH:mm – HH:mm** | Încheiat — apăsați pentru editare |
| **HH:mm –** | Încă pontat — apăsați pentru ieșire sau editare |
| Dungi diagonale | Concediu |
| Gri | În afara intervalului editabil stabilit de companie |

<a id="clock-colours"></a>

### Ce înseamnă culorile

| Culoare | Înseamnă |
|---|---|
| **Verde** | O zi obișnuită |
| **Mov** | Peste plan — vezi mai jos |
| **Roz / ambră** | Weekend / sărbătoare legală |
| **Triunghi galben în colț** | Intrare după începerea turei sau ieșire înainte de final |

**Movul** înseamnă ore suplimentare față de programul companiei, ore de weekend sau
sărbătoare, **sau** muncă în afara turei repartizate — intrare cu peste **15
minute** mai devreme sau ieșire cu peste 15 minute mai târziu. Într-o zi fără tură
repartizată, ultima regulă se măsoară față de cel mai larg interval pe care îl
lucrează vreodată funcția respectivă.

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

O listă per șantier cu statusul fiecărui angajat, ultima pontare, șantierul și
nota. **Pontare intrare** cere un șantier (cel implicit este preselectat) și o notă
opțională; **Pontare ieșire** cere o notă. Etichetele de deasupra fiecărui tabel
numără **Încheiate**, **În curs** și **Nepontate**.

<a id="clock-manual"></a>

### Adăugarea manuală a unui pontaj

**+ Adaugă pontaj** înregistrează o intrare istorică pentru oricare dintre
angajații dvs. și orice dată — soluția pentru o pontare ratată. Stabiliți intrarea,
opțional ieșirea, șantierul și o notă.

<a id="clock-shift-times"></a>

### Completarea orelor din tură

Deasupra câmpurilor de ore apare un rând de **etichete de tură** — de exemplu
`Tura B · 08:00–16:00` — cu turele care aparțin funcțiilor angajaților selectați.
Apăsați una și orele se completează; rămân editabile. Ieșirea unei ture de noapte
ajunge în ziua următoare. Dacă firma nu definește ture, nu apar etichete și
câmpurile revin la programul de lucru al companiei sau la 08:00–17:00.

<a id="clock-edit"></a>

### Editarea unei zile

Apăsarea unei celule încheiate deschide dialogul de editare; dacă există mai multe
pontaje în ziua respectivă, alegeți unul. Puteți corecta ambele ore. **Nota
existentă nu poate fi modificată** — scrieți în **Adaugă notă**, iar numele dvs. și
ora sunt marcate automat. Notele se completează, nu se suprascriu niciodată.

<a id="clock-bulk"></a>

### Acțiuni în masă

| Tip | Ce face |
|---|---|
| Pontare intrare | O intrare în fiecare zi selectată |
| Pontare ieșire | Închide pontajul deschis din fiecare zi |
| Final | Ambele capete în fiecare zi |
| Concediu | O cerere per zi — **refuzată pentru angajații asociați unui partener** |

Un singur șantier, ore și notă pentru tot lotul. Conflictele sunt raportate înainte
de a se salva ceva.

<a id="clock-lock"></a>

### Bannerul roșu de blocare

Dacă compania-client a blocat pontarea, apare un banner roșu: pontarea în masă este
limitată la ziua de azi și editările pe zile trecute sunt refuzate. De obicei
înseamnă că luna a plecat la salarizare.

---

<a id="employees"></a>

## Angajați

Angajații asociați partenerilor dvs., grupați după șantierul implicit.

<a id="employees-filter"></a>

### Filtrare

Etichete — **Activi / Inactivi / Toate** — plus un filtru de partener când
gestionați mai mulți. Ambele se păstrează în adresă, deci o reîncărcare sau un link
trimis le păstrează.

<a id="employees-columns"></a>

### Coloanele se adaptează singure

**O coloană pe care niciun angajat din companie nu o folosește este ascunsă.** Dacă
nimeni nu are tarif orar, nu există coloana Tarif orar. Nume, Status, Creat și
Acțiuni se afișează mereu, iar o notă sub tabele spune ce este ascuns și cum se
readuce. Setul nu se schimbă când comutați eticheta Activi/Inactivi/Toate.

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
telefonul, data nașterii, șantierul implicit, partenerul, tariful orar și un **PIN
Kiosk** (4–6 cifre, opțional, se poate seta ulterior). Un nume duplicat în companie
este refuzat.

**Câmpurile de concediu anual se dezactivează odată ce este selectat un partener**,
fiindcă angajații asociați unui partener își iau concediul prin propriul
angajator.

> Pentru a muta un angajat existent la alt șantier, folosiți **Transfer** din
> listă, nu acest formular.

<a id="employees-edit"></a>

### Editarea unui angajat

- **ID sistem** este needitabil și este singurul identificator al unui angajat.
- **Numele** este editabil doar în **48 de ore** de la creare, pentru că fișele și
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

Activarea **Amprentă** permite unui angajat să se autentifice la kiosk atingând
senzorul propriului telefon, în loc să tasteze un PIN.

Înrolarea cere **două elemente**: PIN-ul lui *și* un cod de unică folosință emis de
dvs. aici, care este **afișat o singură dată**. Angajatul deschide apoi `/kiosk`,
alege *Configurează amprenta pe acest dispozitiv* și le introduce pe ambele. Doar
PIN-ul ar permite oricui l-a văzut tastând patru cifre să își asocieze permanent
propria amprentă acelui cont.

- **Odată ce un dispozitiv este înregistrat, PIN-ul nu mai funcționează pentru
  pontare**, dar funcționează în continuare pentru vizualizarea orelor și cererile
  de concediu. Un PIN poate fi dat unui coleg; o amprentă, nu.
- **Dezactivarea Amprentei șterge toate dispozitivele înregistrate** — o revocare,
  nu o pauză.
- **Revocarea unui dispozitiv restabilește imediat PIN-ul** — calea de întoarcere
  pentru un telefon pierdut sau descărcat, împreună cu pontarea de către dvs. din
  acest panou.
- Este gândită pentru **telefoane personale**. Pe o tabletă comună orice amprentă
  înrolată deblochează orice passkey de pe ea, deci nu ar împiedica un angajat să
  ponteze un altul.

<a id="employees-csv"></a>

### Export CSV

**Export** oferă Activi, Inactivi sau Toate, cu titluri fixe în engleză, pentru că
reprezintă un contract cu programul care citește fișierul. Notele nu se exportă.

> **Importul nu este disponibil acestui rol.** Scrie la nivelul întregii companii
> și poate schimba cine este activ, ocolind limitarea pe parteneri aplicată de
> toate celelalte ecrane.

<a id="employees-pdf"></a>

### PDF

**↓ PDF** descarcă angajații dvs. activi, grupați după șantier, cu antetul
companiei.

---

<a id="password"></a>

## Parola dvs.

**Schimbă parola** se află în bara de jos. Aveți nevoie de parola actuală, iar cea
nouă trebuie să aibă minimum 8 caractere.

Schimbarea ei **încheie sesiunile din celelalte browsere**. Este intenționat: dacă
parola veche fusese compromisă, orice sesiune deschisă cu ea dispare.

---

*Acest ghid descrie aplicația așa cum este instalată. Dacă un ecran nu corespunde
cu ce este scris aici, aplicația are dreptate și această pagină trebuie
actualizată.*
