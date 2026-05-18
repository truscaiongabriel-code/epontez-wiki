# Ghid administrator

Acest ghid acoperă toate secțiunile dashboard-ului de administrare disponibile administratorilor companiei.

---

## Autentificare

Navigați la `/login` și introduceți emailul și parola. Dacă acest cont a fost dezactivat de un super admin, veți vedea un mesaj specific — resetarea parolei nu va funcționa cât timp contul este inactiv; contactați super adminul.

Pentru recuperarea unei parole uitate, folosiți linkul **Ai uitat parola?** de pe pagina de autentificare. Veți primi un email cu un link de resetare valabil pentru o perioadă limitată.

---

## Navigare

Bara de navigare de sus conține linkuri către toate secțiunile: **Dashboard, Pontaj, Angajați, Șantiere, Parteneri, Timesheets, Concedii, Setări**. Secțiunea activă este evidențiată. Un selector de limbă (EN/RO) se află în colțul din dreapta sus. Numele dvs. și opțiunea de deconectare apar în bara de jos.

---

## Dashboard

O vedere rapidă asupra forței de muncă pentru ziua curentă.

**Statistici — rândul 1**
- **Pontați azi** — angajați distincți cu orice eveniment de pontaj valid azi (în desfășurare sau finalizat)
- **Ore luna aceasta** — total ore finalizate pentru luna curentă (respectă programul de pauză dacă este configurat)

**Statistici — rândul 2**
- **Pontați acum** (accent) — angajați cu pontaj de intrare deschis în acest moment
- **Angajați activi** — numărul total de angajați activi

**Statistici expandabile — rândul 3** (click pe orice statistică pentru a extinde un tabel de detalii)
- **Nepontați în ultimele 5 zile lucrătoare** — angajați care nu au avut niciun eveniment de pontaj în ultimele 5 zile lucrătoare; tabelul afișează numele, funcția și șantierul implicit
- **Concediu azi** — angajați cu o cerere de concediu aprobată sau în așteptare care acoperă ziua de azi; tabelul afișează numele, tipul și statusul

**Grafice** (ultimele 30 de zile, defalcate pe șantier, cu o culoare distinctă pentru fiecare șantier)
- *Persoane pe zi* — angajați distincți cu eveniment de pontaj în fiecare zi
- *Ore pe zi* — total ore finalizate în fiecare zi

**Pontați în prezent** — tabel cu angajații care au un pontaj de intrare deschis azi; coloane: Angajat (cu badge de partener dacă este alocat), Ora de intrare, Notă.

**Ieșiri lipsă** — dacă există angajați cu pontaj de intrare deschis dintr-o zi anterioară, apare sus un banner de avertizare care îi listează pentru a putea corecta înregistrările.

---

## Pontaj

Înregistrează evenimente de intrare și ieșire pentru angajați.

> **Cerință:** trebuie să existe cel puțin un șantier activ înainte de a putea ponta pe cineva.

### Vizualizări

Comutați între vizualizările **Calendar** și **Tabel** folosind butonul din zona dreapta sus.

### Vizualizare Calendar

Un grid cu o coloană pentru fiecare angajat și un rând pentru fiecare zi a lunii selectate. Fiecare celulă afișează evenimentele de pontaj ale angajatului pentru ziua respectivă:

- Un eveniment finalizat afișează **HH:mm – HH:mm** — click pentru editare.
- Un eveniment în desfășurare afișează **HH:mm –** — click pentru pontare ieșire sau editare.
- O zi de concediu afișează un model diagonal hașurat — click pentru anularea cererii (cu notă opțională).
- Celulele din afara ferestrei editabile (controlată de setarea *Editare zile de pontaj anterioare*) sunt afișate cu gri.

Badge-urile de partener apar în anteturile coloanelor angajaților dacă angajatul este alocat unui partener.

**Selectarea celulelor pentru acțiuni în masă** — faceți click pe celule individuale pentru a le selecta (evidențiate cu albastru), apoi alegeți o acțiune din toolbar: **Intrare**, **Ieșire**, **Final** (setează și intrarea, și ieșirea pentru o zi trecută) sau **Concediu**.

### Vizualizare Tabel

O listă tradițională care afișează statusul curent al fiecărui angajat, ultima oră de intrare, șantierul și nota. Acțiuni:

- **Pontare intrare** — selectați șantierul (implicit, șantierul implicit al angajatului), notă opțională, confirmați.
- **Pontare ieșire** — notă opțională, confirmați.

### Adăugarea unui eveniment manual

Folosiți butonul **+ Adaugă pontaj** pentru a înregistra o intrare istorică pentru orice angajat și dată — util pentru pontaje omise. Setați ora de intrare, ora de ieșire opțională, șantierul și nota.

### Modal de editare zi (vizualizare Calendar)

Click pe o celulă cu eveniment finalizat deschide dialogul de editare. Dacă angajatul are mai multe evenimente în acea zi, alegeți evenimentul de editat. Puteți corecta orele de intrare și ieșire. **Nota existentă** este afișată doar pentru citire; scrieți în câmpul **Adaugă notă** pentru a adăuga text — o ștampilă de audit (numele dvs. + timestamp) este adăugată automat la salvare.

### Modal acțiuni în masă

După selectarea mai multor celule din calendar, alegeți tipul acțiunii:

| Tip | Ce face |
|-----|---------|
| Clock In | Înregistrează o intrare pentru fiecare zi selectată |
| Clock Out | Închide pontajul de intrare deschis pentru fiecare zi selectată |
| Final | Înregistrează atât intrarea, cât și ieșirea pentru fiecare zi selectată |
| Time Off | Creează o cerere de concediu pentru fiecare zi selectată |

Puteți seta un șantier comun, ora/orele și nota. Conflictele (de exemplu, un angajat are deja PTO aprobat într-o zi selectată) sunt raportate înainte de salvare.

### Banner blocare

Dacă **Pontaj blocat** este activat în Setări, în partea de sus a paginii apare un banner roșu. Cât timp este blocat, pontajul în masă este restricționat la ziua curentă, iar editările pentru zile anterioare sunt blocate.

---

## Angajați

Gestionați forța de muncă. Angajații sunt grupați după **șantierul implicit**; cei fără șantier implicit apar într-un grup "Fără șantier alocat" în partea de sus.

### Filtrare

Folosiți filtrele tip pill — **Activ / Inactiv / Toți** — pentru a restrânge lista. Dacă există parteneri, apare și un filtru dropdown pentru partener. Parametrii URL păstrează filtrul la reîncărcare.

### Adăugarea unui angajat

Click pe **Adaugă angajat** și completați:

- **Nume** (obligatoriu)
- **Funcție** (obligatoriu)
- Email, telefon (opționale)
- **Șantier implicit** — preselectează acest șantier în dropdown-ul de pontare din kiosk și grupează angajatul sub acel șantier în această listă
- **PIN** — un cod numeric folosit de angajat pentru autentificare în kiosk; lăsați gol dacă angajatul nu are nevoie de acces kiosk (poate fi setat ulterior)
- **ID angajat** este generat automat, dar poate fi setat manual; este unic în companie și nu poate fi modificat după creare

### Editarea unui angajat

Click pe **Editare** pentru a deschide pagina de editare a angajatului. Toate câmpurile de la creare sunt editabile, plus:

- **Data nașterii** — opțională; stocată pentru referință
- **Status** — comutarea Activ / Inactiv necesită un motiv, care este adăugat în notele de audit ale angajatului
- **Partener** — alocați angajatul unui partener de afaceri; apare ca badge mov în platformă
- **Pontaj automat** — activați pentru ca sistemul să înregistreze automat intrarea și ieșirea în fiecare zi lucrătoare:
  - Selectați șantierul, ora de început (HH:mm) și ora de sfârșit (HH:mm)
  - Începutul trebuie să fie înainte de sfârșit
  - Cât timp este activ, angajatul nu poate ponta manual din kiosk
  - Zilele cu concediu aprobat și weekendurile sunt sărite automat
- **Auto-locare** — când este activată, kiosk-ul solicită locația GPS a angajatului la intrare; serverul stochează coordonatele și înregistrează dacă angajatul era în raza șantierului
- **Șterge PIN** — elimină PIN-ul, astfel încât angajatul nu mai poate folosi kiosk-ul
- **Zonă periculoasă** (doar angajați inactivi) — **Ascunde angajat** face angajatul invizibil pentru toți administratorii și pentru kiosk; doar un super admin îl poate reafișa

### Badge partener

Un pill mov cu numele partenerului apare lângă numele angajatului în platformă (lista angajaților, timesheets, pagina de pontaj, dashboard).

### Import / Export CSV

**Export CSV** — descarcă un spreadsheet cu toți angajații care se potrivesc filtrului de status curent. Coloane: `employeeId, name, position, email, phone, dateOfBirth, active, autoClockEnabled, autoClockStart, autoClockEnd, autoClockSiteName, autoLocateEnabled, defaultSiteName`.

**Import CSV** — după selectarea unui fișier, se afișează un **preview** înainte de a se face modificări:
- **De adăugat** — rânduri care nu se potrivesc niciunui angajat existent
- **Cu modificări** — angajați existenți unde cel puțin un câmp diferă
- **Fără modificări** — angajați existenți cu date identice (săriți la import)

Erorile (nume de șantier necunoscut, valoare invalidă, câmpuri obligatorii lipsă pentru pontaj automat, ID angajat duplicat etc.) trebuie rezolvate înainte ca importul să fie confirmat. Schimbările de status activ sunt adăugate automat în notele de audit ale fiecărui angajat.

Logica de potrivire: `employeeId` este cheia principală, apoi numele (case-insensitive), apoi emailul. Rândurile noi necesită `employeeId` setat.

### Descărcare PDF

**↓ PDF** descarcă o listă A4 landscape cu angajații grupați pe șantier, incluzând nume, funcție, email, telefon și status PIN.

---

## Șantiere

Gestionați șantierele companiei. Șantierele active apar în dropdown-ul de pontare.

### Adăugarea unui șantier

Completați **numele șantierului** (obligatoriu) și opțional:

- **Adresă**
- **Locație pe hartă** — click pe **Setează locația pe hartă** pentru a deschide o hartă interactivă; mutați pinul sau căutați după adresă; coordonatele salvate sunt folosite pentru verificarea auto-locare pe șantier și apar ca link clicabil de hartă în administrare
- **Partener** — legați acest șantier de un partener de afaceri
- **Ieșire automată** — bifați caseta și setați o oră (HH:mm) pentru a ponta automat ieșirea oricărui angajat încă pontat pe acest șantier la ora respectivă

### Editarea unui șantier

Toate câmpurile de la creare sunt editabile. Fiecare salvare adaugă o linie în **istoricul de audit** al șantierului, indicând ce s-a schimbat, când și de către cine. Vedeți istoricul prin extinderea secțiunii de istoric din formularul de editare.

### Activare / Dezactivare

Un șantier inactiv nu mai apare în dropdown-ul de pontare sau în kiosk. Dezactivarea nu șterge istoricul de pontaj.

### Ascunderea unui șantier

Șantierele inactive pot fi ascunse folosind butonul **Ascunde** din coloana de acțiuni. Șantierele ascunse sunt invizibile pentru toți administratorii și pentru kiosk — doar un super admin le poate reafișa.

### Filtre tip pill

Folosiți **Activ / Inactiv / Toți** pentru a schimba vizualizarea.

---

## Parteneri

Gestionați partenerii de afaceri (subcontractori, clienți) asociați companiei.

### Adăugarea unui partener

Completați **numele partenerului** (obligatoriu) și opțional adresa, emailul, telefonul și CUI (cod fiscal românesc).

### Editarea unui partener

Click pe **Editare** pentru a actualiza orice câmp. Puteți de asemenea **Dezactiva** sau **Activa** un partener din coloana de acțiuni.

### Asociere partener–șantier

Șantierele sunt legate de parteneri din pagina **Șantiere** (în formularul de editare al șantierului). Fiecare rând de partener din acest tabel afișează o sub-listă cu toate șantierele alocate în prezent.

### Filtre tip pill

Filtrele **Activ / Inactiv / Toți** se aplică și aici.

---

## Timesheets

Date lunare de salarizare pentru fiecare angajat.

### Navigarea între luni

Folosiți selectorul de lună (săgeți sau dropdown) pentru a comuta între luni.

### Filtre

- **Șantier** — afișează doar angajații pontați pe un anumit șantier
- **Angajat** — afișează un singur angajat
- **Partener** — afișează doar angajații care aparțin unui anumit partener (sau "Fără partener" pentru cei nealocați)

Implicit (fără filtru) se afișează un sumar compact. Folosiți butonul **Extinde tot** sau selectați un filtru pentru a încărca tabelul complet.

### Citirea tabelului

Fiecare angajat are o secțiune cu rânduri zilnice. Coloane: Dată, Zi, Intrare, Ieșire, Ore, Șantier, Pontat de, Ieșire pontată de, Notă.

Indicatori speciali:
- Pill **Auto** — evenimentul a fost creat de cron-ul de pontaj automat
- **pin 📍** — coordonatele GPS au fost capturate la intrare (hover pentru badge pe șantier / în afara șantierului)
- Badge **Void** — evenimentul este marcat invalid și exclus din totaluri

Totalurile pe zi, totalul general de ore și orele facturabile (respectând programul de pauză) sunt afișate pentru fiecare angajat.

### Editarea unui eveniment de pontaj

Click pe iconița creion de pe orice rând pentru a deschide dialogul de editare. Puteți corecta ora de intrare sau ieșire, comuta flagul **Valid** și adăuga o notă. O ștampilă de audit (numele dvs. + timestamp) este adăugată automat la salvare.

### Vizualizare Calendar (timesheets)

Comutați la vizualizarea calendar pentru un grid vizual al lunii. Click pe o celulă cu eveniment finalizat deschide un dialog de editare cu aceeași posibilitate de adăugare notă. Click pe o celulă de concediu deschide un dialog de anulare cu notă opțională.

### Descărcarea PDF-ului

Click pe **↓ PDF** pentru a descărca un timesheet A4 formatat pentru luna și filtrele selectate.

---

## Concedii

Revizuiți, aprobați și gestionați cererile de concediu ale angajaților.

### Tipuri de concediu

| Cod | Descriere |
|-----|-----------|
| CO | Concediu de odihnă plătit |
| CFP | Concediu fără plată |
| Medical | Concediu medical / certificat medical |
| Marriage | Eveniment căsătorie |
| Blood donation | Zi pentru donare de sânge |
| Special events | Alte evenimente speciale |
| Military | Serviciu militar |
| Funeral | Deces |
| Child birth | Concediu parental |

### Navigare și filtrare

Folosiți **selectorul de lună** pentru navigare. Un dropdown **tip** filtrează după categoria de concediu. Lunile cu cereri în așteptare sunt evidențiate deasupra selectorului, ca să puteți sări rapid la ele.

### Citirea tabelului

Cererile sunt listate pe zile lucrătoare (un rând pe zi). Pill-urile de sumar din partea de sus numără zilele lucrătoare pe status. Fiecare rând afișează: data, ziua săptămânii, tipul, badge-ul de status, trimis de și nota.

### Acțiuni

- **Aprobă** — acceptă cererea; zilele aprobate sunt sărite de cron-ul de pontaj automat
- **Respinge** — refuză cererea
- **Anulează** — anulează o cerere aprobată sau în așteptare

Toate cele trei acțiuni acceptă o notă opțională care este salvată pe cerere.

---

## Setări

Configurația companiei. Accesibilă doar administratorilor.

### Detalii companie

Actualizați **numele, emailul, telefonul, adresa, CUI-ul** și numele **managerului** companiei. Acestea apar în anteturile PDF.

**Logo** — încărcați un PNG sau JPEG de până la 200 KB. Logo-ul apare în chip-ul de navigare din stânga sus și în toate anteturile PDF.

### Kiosk angajați

**Codul de acces kiosk** este codul pe care angajații îl introduc la `/kiosk` pentru a identifica firma. Îl puteți actualiza aici.

### Ieșire automată globală

Pontează automat ieșirea tuturor angajaților încă pontați la o oră setată.

- Comutați **Activare** pornit sau oprit.
- Setați o **oră de ieșire** (HH:mm, Europe/Bucharest). Toți angajații cu pontaj de intrare deschis la exact acel minut sunt pontați automat la ieșire.

> **Sfat:** orele de ieșire automată pe șantier pot fi setate pe pagina **Șantiere**, pentru a viza doar angajații pontați pe un anumit șantier.

### Program pauză

Activați și configurați o fereastră zilnică de pauză (ora de început și ora de sfârșit). Când este activată, orele care se suprapun cu pauza sunt excluse din totalurile facturabile în timesheets și dashboard.

### Program de lucru

Activați și configurați orele standard de lucru (ora de început și ora de sfârșit). Folosit pentru calculul orelor suplimentare — orele din afara acestei ferestre sunt considerate ore suplimentare în totalurile timesheet.

### Blocare pontaj

Când **Pontaj blocat** este activat, toate editările pentru zile anterioare sunt blocate, iar pontajul în masă este restricționat la ziua curentă. Un banner roșu este afișat pe pagina Pontaj cât timp blocarea este activă.

### Editare zile de pontaj anterioare

Controlează câte zile în urmă poate fi editat un eveniment de pontaj (implicit: 5). Evenimentele mai vechi decât această limită nu pot fi modificate de utilizatori care nu sunt super admin.

### Utilizatori admin

Listează toate conturile de administrator ale companiei. Puteți:

- **Adăuga** un administrator nou (nume, email, parolă — minimum 8 caractere)
- **Edita** numele și emailul
- **Reseta parola**
- **Dezactiva / Activa** administratori existenți

Administratorii dezactivați nu se pot autentifica și resetarea parolei nu funcționează pentru ei. Conturile super admin sunt marcate cu un badge **Super** și nu pot fi dezactivate din această pagină.

### Manageri de șantier

Listează toate conturile de manager de șantier. Managerii de șantier au acces restricționat — pot vedea doar angajații al căror șantier implicit corespunde șantierelor alocate.

- **Adăugați** un manager de șantier (nume, email, parolă)
- **Acces aplicație** — alegeți ce secțiuni poate vedea managerul: Status, Pontaj, Angajați, Șantiere, Timesheets, Concedii, Plan. Pontaj și Angajați sunt întotdeauna active implicit.
- **Vizualizare/Gestionare parteneri** — checkbox în profilul managerului; când este activat, managerul poate vedea coloana Parteneri și badge-urile de partener pe angajați
- **Alocare șantiere** — selectați șantierele pentru care acest manager este responsabil
- **Editare**, **resetare parolă**, **dezactivare / activare**

### Manageri de parteneri

Listează toate conturile de manager de parteneri. Managerii de parteneri pot accesa doar paginile Pontaj și Angajați și văd doar angajații care aparțin partenerilor alocați.

- **Adăugați** un manager de parteneri (nume, email, parolă)
- **Alocare parteneri** — selectați partenerii pentru care acest manager este responsabil
- **Editare**, **resetare parolă**, **dezactivare / activare**

---

## Schimbarea parolei

Click pe numele dvs. din bara de jos, apoi **Schimbă parola**. Trebuie să introduceți parola curentă pentru a seta una nouă (minimum 8 caractere).
