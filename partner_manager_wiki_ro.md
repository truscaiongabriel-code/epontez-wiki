# Ghid pentru managerul de parteneri

Acest ghid acoperă secțiunile dashboard-ului de administrare disponibile pentru managerii de parteneri.

---

## Ce este un manager de parteneri?

Un manager de parteneri este un cont de administrator restricționat, creat de administratorul companiei. Puteți vedea și gestiona doar angajații care aparțin partenerilor de afaceri care v-au fost alocați. Accesul este limitat la două pagini: **Pontaj** și **Angajați**.

---

## Autentificare

Navigați la `/login` și introduceți emailul și parola. Dacă acest cont a fost dezactivat, contactați administratorul companiei.

Pentru recuperarea unei parole uitate, folosiți linkul **Ai uitat parola?**. Veți primi un email de resetare valabil pentru o perioadă limitată.

---

## Navigare

Bara de navigare de sus afișează două linkuri: **Pontaj** și **Angajați**. Celelalte secțiuni nu sunt accesibile managerilor de parteneri. Un selector de limbă (EN/RO) este disponibil în colțul din dreapta sus. Numele dvs. și opțiunea de deconectare apar în bara de jos.

---

## Pontaj

Înregistrați și gestionați evenimentele de intrare și ieșire pentru angajații care aparțin partenerilor alocați.

### Vizualizări

Comutați între vizualizările **Calendar** și **Tabel** folosind butonul din zona dreapta sus.

### Vizualizare Calendar

Un grid cu o coloană pentru fiecare angajat (din partenerii alocați) și un rând pentru fiecare zi. Fiecare celulă afișează evenimentele de pontaj ale angajatului pentru ziua respectivă:

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

Folosiți butonul **+ Adaugă pontaj** pentru a înregistra o intrare istorică. Setați angajatul, ora de intrare, ora de ieșire opțională, șantierul și nota.

### Modal de editare zi (vizualizare Calendar)

Click pe o celulă cu eveniment finalizat deschide dialogul de editare. **Nota existentă** este afișată doar pentru citire; folosiți câmpul **Adaugă notă** pentru a adăuga text — o ștampilă de audit (numele dvs. + timestamp) este adăugată automat la salvare.

---

## Angajați

Vizualizați și gestionați angajații care aparțin partenerilor alocați.

> Importul CSV nu este disponibil pentru managerii de parteneri.

### Filtrare

Folosiți filtrele tip pill — **Activ / Inactiv / Toți** — pentru a restrânge lista.

### Adăugarea unui angajat

Click pe **Adaugă angajat** și completați numele, funcția, email/telefon/PIN opționale și șantierul implicit.

### Editarea unui angajat

Click pe **Editare** pentru a deschide pagina de editare a angajatului. Puteți actualiza numele, funcția, emailul, telefonul, data nașterii, șantierul implicit, PIN-ul, setările de pontaj automat și auto-locarea.

**Schimbările de status** (Activ / Inactiv) necesită un motiv, care este adăugat în notele de audit ale angajatului.

**Zonă periculoasă** (doar angajați inactivi) — butonul **Ascunde angajat** face angajatul invizibil; doar un super admin îl poate reafișa.

### Descărcare PDF

**↓ PDF** descarcă o listă A4 landscape cu angajații din aria dvs. de acces.

---

## Schimbarea parolei

Click pe numele dvs. din bara de jos, apoi **Schimbă parola**. Trebuie să introduceți parola curentă pentru a seta una nouă (minimum 8 caractere).
