# Ghid pentru managerul de șantier

Acest ghid acoperă toate secțiunile dashboard-ului de administrare disponibile pentru managerii de șantier.

---

## Ce este un manager de șantier?

Un manager de șantier este un cont de administrator restricționat, creat de administratorul companiei. Spre deosebire de un administrator complet, puteți vedea și gestiona doar angajații și datele care aparțin șantierelor care v-au fost alocate. Paginile la care aveți acces sunt configurate de administrator — puteți vedea unele sau toate dintre: **Status (Dashboard), Pontaj, Angajați, Șantiere, Timesheets, Concedii, Plan**.

---

## Autentificare

Navigați la `/login` și introduceți emailul și parola. Dacă acest cont a fost dezactivat, contactați administratorul companiei.

Pentru recuperarea unei parole uitate, folosiți linkul **Ai uitat parola?**. Veți primi un email de resetare valabil pentru o perioadă limitată.

---

## Navigare

Bara de navigare de sus afișează doar secțiunile activate de administrator pentru contul dvs. Secțiunea activă este evidențiată. Un selector de limbă (EN/RO) este disponibil în colțul din dreapta sus. Numele dvs. și opțiunea de deconectare apar în bara de jos.

---

## Status (Dashboard)

> Vizibil doar dacă administratorul v-a acordat acces la secțiunea **Status**.

Afișează o vedere rapidă asupra angajaților de pe șantierele alocate.

**Ce vedeți:**
- O listă cu șantierele alocate, cu link de hartă clicabil (dacă sunt setate coordonate) și numărul angajaților pontați în prezent pe fiecare șantier.
- **Pontați azi** — angajați distincți cu orice eveniment de pontaj azi pe șantierele dvs.
- **Ore luna aceasta** — total ore finalizate pentru luna curentă pe șantierele dvs.
- **Pontați acum** — angajați cu pontaj de intrare deschis în acest moment.
- **Angajați activi** — numărul angajaților activi al căror șantier implicit este unul dintre șantierele alocate.
- **Nepontați în ultimele 5 zile lucrătoare** — angajați din șantierele dvs. care nu au avut niciun eveniment de pontaj în ultimele 5 zile lucrătoare.
- **Concediu azi** — angajați din șantierele dvs. cu o cerere de concediu aprobată sau în așteptare pentru azi.
- **Grafice pe 30 de zile** — tendințe zilnice pentru persoane și ore, defalcate pe șantier.
- **Tabel pontați acum** — angajați pontați activ în acest moment, cu ora de intrare și nota.

Dacă nu aveți încă șantiere alocate, pagina afișează o notificare până când administratorul alocă șantiere contului dvs.

---

## Pontaj

Înregistrați și gestionați evenimentele de intrare și ieșire pentru angajații de pe șantierele alocate.

### Vizualizări

Comutați între vizualizările **Calendar** și **Tabel** folosind butonul din zona dreapta sus.

### Vizualizare Calendar

Un grid cu o coloană pentru fiecare angajat (din șantierele alocate) și un rând pentru fiecare zi. Fiecare celulă afișează evenimentele de pontaj ale angajatului pentru ziua respectivă:

- Un eveniment finalizat afișează **HH:mm – HH:mm** — click pentru editare.
- Un eveniment în desfășurare afișează **HH:mm –** — click pentru pontare ieșire sau editare.
- O zi de concediu afișează un model diagonal hașurat — click pentru anularea cererii (cu notă opțională).
- Celulele din afara ferestrei editabile sunt afișate cu gri.

**Selectarea celulelor pentru acțiuni în masă** — faceți click pe celule individuale pentru a le selecta, apoi alegeți o acțiune din toolbar: **Intrare**, **Ieșire**, **Final** (setează și intrarea, și ieșirea pentru o zi trecută) sau **Concediu**.

### Vizualizare Tabel

O listă care afișează statusul curent al fiecărui angajat, ultima oră de intrare, șantierul și nota.

- **Pontare intrare** — selectați șantierul, notă opțională, confirmați.
- **Pontare ieșire** — notă opțională, confirmați.

### Adăugarea unui eveniment manual

Folosiți butonul **+ Adaugă pontaj** pentru a înregistra o intrare istorică. Setați angajatul, ora de intrare, ora de ieșire opțională, șantierul și nota. Este util pentru corectarea pontajelor lipsă.

### Modal de editare zi (vizualizare Calendar)

Click pe o celulă cu eveniment finalizat deschide dialogul de editare. **Nota existentă** este afișată doar pentru citire; folosiți câmpul **Adaugă notă** pentru a adăuga text — o ștampilă de audit (numele dvs. + timestamp) este adăugată automat la salvare.

---

## Angajați

Vizualizați și gestionați angajații al căror șantier implicit este unul dintre șantierele alocate.

> Importul CSV nu este disponibil pentru managerii de șantier.

### Filtrare

Folosiți filtrele tip pill — **Activ / Inactiv / Toți** — pentru a restrânge lista. Dacă administratorul a activat vizibilitatea partenerilor pentru contul dvs., apare și un filtru dropdown pentru partener.

### Adăugarea unui angajat

Click pe **Adaugă angajat** și completați numele, funcția, email/telefon/PIN opționale și șantierul implicit (precompletat cu primul șantier alocat).

### Editarea unui angajat

Click pe **Editare** pentru a deschide pagina de editare a angajatului. Puteți actualiza numele, funcția, emailul, telefonul, data nașterii, șantierul implicit, PIN-ul, setările de pontaj automat și auto-locarea. Dacă administratorul a activat **Vizualizare/Gestionare parteneri** pentru contul dvs., puteți vedea și actualiza și partenerul angajatului.

**Schimbările de status** (Activ / Inactiv) necesită un motiv, care este adăugat în notele de audit ale angajatului.

**Zonă periculoasă** (doar angajați inactivi) — butonul **Ascunde angajat** face angajatul invizibil; doar un super admin îl poate reafișa.

### Descărcare PDF

**↓ PDF** descarcă o listă A4 landscape cu angajații pentru șantierele dvs.

---

## Șantiere

> Vizibil doar dacă administratorul v-a acordat acces la secțiunea **Șantiere**.

Afișează șantierele care v-au fost alocate. Puteți vedea detaliile șantierului, edita adresa și locația și gestiona configurația de pontare automată la ieșire.

Fiecare modificare este înregistrată în istoricul de audit al șantierului (ce s-a modificat, când și de către cine).

---

## Timesheets

> Vizibil doar dacă administratorul v-a acordat acces la secțiunea **Timesheets**.

Date lunare de pontaj pentru angajații de pe șantierele alocate.

### Navigarea între luni

Folosiți selectorul de lună pentru a comuta între luni.

### Filtre

- **Șantier** — restrânge la un anumit șantier alocat
- **Angajat** — afișează un singur angajat
- **Partener** — filtrează după partener (dacă vizibilitatea partenerilor este activată pentru contul dvs.)

### Citirea tabelului

Fiecare angajat are o secțiune cu rânduri zilnice. Coloane: Dată, Zi, Intrare, Ieșire, Ore, Șantier, Pontat de, Ieșire pontată de, Notă.

Indicatori speciali:
- Pill **Auto** — evenimentul a fost creat de cron-ul de pontaj automat
- **pin 📍** — coordonatele GPS au fost capturate la intrare
- Badge **Void** — evenimentul este marcat invalid și exclus din totaluri

### Editarea unui eveniment de pontaj

Click pe iconița creion de pe orice rând pentru a deschide dialogul de editare. Puteți corecta orele de intrare/ieșire, comuta flagul **Valid** și adăuga o notă. O ștampilă de audit este adăugată automat la salvare.

### Vizualizare Calendar

Comutați la vizualizarea calendar pentru un grid vizual al lunii. Click pe o celulă cu eveniment finalizat deschide un dialog de editare cu aceeași posibilitate de adăugare notă. Click pe o celulă de concediu deschide un dialog de anulare.

> **Notă:** Descărcarea timesheet-ului PDF nu este disponibilă pentru managerii de șantier.

---

## Concedii

> Vizibil doar dacă administratorul v-a acordat acces la secțiunea **Concedii**.

Revizuiți, aprobați și gestionați cererile de concediu pentru angajații de pe șantierele alocate.

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

Folosiți **selectorul de lună** pentru navigare. Lunile cu cereri în așteptare sunt evidențiate ca să puteți sări rapid la ele. Un dropdown **tip** filtrează după categoria de concediu.

### Acțiuni

- **Aprobă** — acceptă cererea; zilele aprobate sunt sărite de cron-ul de pontaj automat
- **Respinge** — refuză cererea
- **Anulează** — anulează o cerere aprobată sau în așteptare

Toate cele trei acțiuni acceptă o notă opțională.

---

## Plan

> Vizibil doar dacă administratorul v-a acordat acces la secțiunea **Plan**.

Secțiunea Plan oferă vizualizări pentru planificarea resurselor. Consultați secțiunea Plan din wiki-ul administratorului pentru detalii complete.

---

## Schimbarea parolei

Click pe numele dvs. din bara de jos, apoi **Schimbă parola**. Trebuie să introduceți parola curentă pentru a seta una nouă (minimum 8 caractere).
