# Ghid Kiosk Angajat

Cum vă pontați, cum vă verificați orele și cum cereți concediu.

> **Ancorele sunt stabile** și comune cu versiunea engleză: un subiect are același
> `id` în ambele, deci `employee_wiki_ro.md#clock-in` și
> `employee_wiki_en.md#clock-in` sunt același subiect.

**Cuprins** — [Accesarea kioskului](#kiosk) · [Autentificare](#login) ·
[Autentificare cu amprenta](#passkey) · [Ecranul principal](#home) ·
[Pontare intrare](#clock-in) · [Pontare ieșire](#clock-out) ·
[Locație și fotografii](#location) · [Pontajele mele](#myclocking) ·
[Cerere de concediu](#timeoff) · [Concediile mele](#mytimeoffs) ·
[Deconectare](#signout) · [Probleme](#problems)

---

<a id="kiosk"></a>

## Accesarea kioskului

Deschideți `/kiosk` în browser — pe tableta de la șantier sau pe propriul telefon.
Kioskul este un ecran complet, pe fond închis, separat de panoul de birou, și
preia culorile și logoul companiei dvs. odată ce află de care companie aparțineți.

---

<a id="login"></a>

## Autentificare

<a id="login-code"></a>

### Pasul 1 — codul companiei

Tastați codul primit de la angajator. Arată ca **AB1234** — două litere și patru
cifre. După acceptare, ecranul afișează logoul companiei.

Dacă codul este refuzat, verificați-l cu administratorul; poate fi regenerat, caz
în care toți primesc un cod nou.

<a id="login-pin"></a>

### Pasul 2 — numele și PIN-ul

Alegeți-vă numele din listă și tastați **PIN-ul** (4 până la 6 cifre).

În listă apar doar angajații cărora li s-a setat un PIN. Dacă numele dvs. lipsește,
cereți administratorului să vă seteze unul.

<a id="login-return"></a>

### La următoarele accesări

Codul companiei este reținut pe acel dispozitiv, deci data viitoare treceți direct
la alegerea numelui.

---

<a id="passkey"></a>

## Autentificare cu amprenta

Dacă angajatorul a activat această opțiune pentru dvs., vă puteți autentifica
atingând senzorul de amprentă al propriului telefon, în loc să vă alegeți numele și
să tastați un PIN. Butonul **Autentificare cu amprenta** apare la **ambii** pași de
autentificare — inclusiv la primul, înainte de orice cod de companie, pentru că
amprenta dvs. identifică deodată și persoana și compania.

<a id="passkey-setup"></a>

### Configurarea, o singură dată per dispozitiv

Aveți nevoie de două lucruri, intenționat: **PIN-ul dvs.** și un **cod de înrolare
de unică folosință** de la administrator. Doar PIN-ul nu este suficient, pentru că
altfel oricine v-a văzut tastând patru cifre și-ar putea asocia definitiv propria
amprentă contului dvs.

1. Cereți administratorului un cod de înrolare. El îl poate vedea o singură dată,
   deci vi-l va citi sau trimite.
2. Pe **propriul telefon**, deschideți `/kiosk` și alegeți **Configurează amprenta
   pe acest dispozitiv**.
3. Introduceți codul companiei, numele, PIN-ul și codul de înrolare.
4. Confirmați cu amprenta sau deblocarea facială a telefonului când vi se cere.

Amprenta dvs. **nu părăsește niciodată telefonul**. Se folosește doar o cheie
păstrată în cipul securizat al telefonului, iar angajatorul nu primește niciodată
amprenta dvs.

<a id="passkey-pin-rule"></a>

### Odată configurată, PIN-ul nu vă mai pontează

Acest lucru îi surprinde pe mulți, deci merită spus clar:

| Acțiune | PIN | Amprentă |
|---|---|---|
| Pontare intrare și ieșire | **Nu mai funcționează** | Da |
| Vizualizarea orelor | Da | Da |
| Vizualizarea concediilor | Da | Da |
| Cererea de concediu | Da | Da |

Motivul este că un PIN poate fi dat altcuiva — predat unui coleg în parcare, de
unde apare cineva pontat fără să fie la muncă — iar o amprentă nu poate. Deci odată
ce aveți ceva care nu poate fi transmis, ceea ce poate fi transmis nu mai este
acceptat pentru acțiunea unde ar conta.

Dacă vă autentificați cu PIN-ul și încercați să vă pontați, veți vedea **„Pontarea
necesită amprenta. Deconectați-vă și folosiți butonul de amprentă."**

<a id="passkey-lost"></a>

### Dacă pierdeți telefonul sau bateria este descărcată

Două soluții:

- Cereți administratorului să vă **ponteze din panoul de birou**.
- Cereți-i să **revoce dispozitivul**, ceea ce face ca PIN-ul să funcționeze din
  nou imediat pentru pontare.

Configurați amprenta din nou pe telefonul nou când îl aveți.

> **Este gândită pentru propriul telefon.** Nu este potrivită pe o tabletă comună,
> pentru că orice amprentă înrolată pe acea tabletă ar debloca orice cont
> înregistrat pe ea.

---

<a id="home"></a>

## Ecranul principal

Odată autentificat, aveți patru opțiuni:

| Opțiune | Ce face |
|---|---|
| **Pontare intrare / ieșire** | Înregistrează începutul sau finalul muncii |
| **Pontajele mele** | Orele dvs. pentru o lună |
| **Cerere de concediu** | Solicitați concediu |
| **Concediile mele** | Statusul cererilor dvs. |

Logoul companiei este sus. Totul se află într-un singur card, în culorile
companiei.

---

<a id="clock-in"></a>

## Pontare intrare

1. Apăsați **Pontare intrare**.
2. Alegeți **șantierul** unde lucrați. Dacă aveți un șantier implicit, el este deja
   selectat; schimbați-l dacă astăzi sunteți în altă parte.
3. Adăugați o **notă** dacă doriți — de exemplu la ce lucrați.
4. Confirmați.

Ecranul arată apoi că sunteți pontat, cu ora.

<a id="clock-autoclock"></a>

### Dacă aveți pontaj automat

Unii angajați au ziua înregistrată automat de o sarcină nocturnă. Dacă vi se
aplică, kioskul afișează eticheta **Pontaj automat**, iar butoanele de pontare sunt
dezactivate — nu aveți ce să apăsați, iar orele vă sunt înregistrate.

---

<a id="clock-out"></a>

## Pontare ieșire

Apăsați **Pontare ieșire**, adăugați o notă dacă doriți și confirmați. Șantierul
este deja cunoscut din pontarea de intrare.

Dacă uitați, angajatorul poate avea o oră de pontare automată de ieșire, caz în
care tura se închide atunci și se adaugă o notă în înregistrare. Este mai bine să
vă pontați singur, fiindcă ora automată este aceeași pentru toți.

---

<a id="location"></a>

## Locație și fotografii

În funcție de felul în care angajatorul a configurat lucrurile, vi se pot cere două
lucruri suplimentare.

<a id="location-gps"></a>

### Locația

Dacă **localizarea automată** este activă pentru dvs., locația telefonului este
înregistrată atât la pontarea de intrare, **cât și** la cea de ieșire, iar
înregistrarea arată dacă erați la șantier.

**În acest caz, locația este obligatorie.** Dacă o blocați, nu vă puteți ponta —
veți vedea **„Locația este necesară pentru pontare. Permiteți accesul la locație și
încercați din nou."** O verificare pe care o puteți sări refuzând nu ar fi o
verificare.

Permiteți locația în browser când vi se cere. Dacă vedeți un mesaj că locația este
*indisponibilă*, nu refuzată, înseamnă că ați permis-o, dar nu există încă semnal —
ieșiți afară sau așteptați un moment și încercați din nou.

Faptul că sunteți departe de șantier **nu** vă împiedică să vă pontați. Este
înregistrat pentru ca managerul să îl vadă, nu folosit pentru a vă opri.

Coordonatele dvs. se șterg automat după **180 de zile** și puteți cere
angajatorului să le șteargă mai devreme.

<a id="location-selfie"></a>

### O fotografie, uneori

Angajatorul poate cere o fotografie la o parte aleatorie dintre pontări. Dacă vi
se cere una, se deschide camera.

**Nu puteți scăpa încercând din nou.** Anularea, refuzul camerei sau închiderea
paginii doar amână aceeași fotografie — următoarea încercare o va cere din nou,
până o faceți. Veți vedea **„Este necesară o fotografie pentru această pontare.
Faceți fotografia pentru a continua — va fi cerută din nou până atunci."**

Dacă camera este într-adevăr defectă, cereți administratorului să vă ponteze din
panou, unde nu se cere niciodată o fotografie.

---

<a id="myclocking"></a>

## Pontajele mele

O vedere doar pentru citire a propriilor pontaje, pentru o lună pe care o alegeți.

- Grupate pe zile, cu subtotal pe zi și total pe lună.
- Arată atât orele **efective**, cât și cele **facturabile** — din cele facturabile
  este scăzută pauza neplătită, de aceea cele două pot diferi.
- Înregistrările create automat au marcajul **Auto**.

Dacă ceva pare greșit, spuneți managerului — nu puteți modifica aici, iar o
corecție făcută de el este înregistrată cu numele lui.

---

<a id="timeoff"></a>

## Cerere de concediu

<a id="timeoff-form"></a>

### Completarea formularului

1. Apăsați **Cerere de concediu**.
2. Alegeți **tipul**:

| Tip | Pentru |
|---|---|
| **CO** | Concediu de odihnă |
| **CFP** | Concediu fără plată |
| **Medical** | Concediu medical |
| **Căsătorie** | Propria nuntă |
| **Donare de sânge** | |
| **Evenimente speciale** | |
| **Militar** | Obligații militare |
| **Deces** | Deces în familie |
| **Naștere** | |
| **Motivat** | Absență motivată |
| **Absent** | Absență înregistrată |

3. Alegeți **prima și ultima zi**.
4. Adăugați un **motiv** sau o notă, dacă doriți.
5. Trimiteți.

Se numără doar **zilele lucrătoare**, deci o cerere peste un weekend nu consumă
zile în plus.

<a id="timeoff-after"></a>

### După trimitere

Cererea intră ca **În așteptare**, iar managerul o aprobă sau o respinge. Până
este **aprobată**, tura dvs. planificată rămâne în vigoare, deci nu considerați o
cerere în așteptare drept acceptată.

<a id="timeoff-partner"></a>

### Dacă lucrați pentru o firmă partener

Dacă sunteți asociat unui partener — un colaborator, nu compania al cărei kiosk
este acesta — **nu puteți cere concediu aici**. Rezolvați-l cu propriul angajator.

---

<a id="mytimeoffs"></a>

## Concediile mele

Un tabel doar pentru citire cu cererile dvs. pentru o lună pe care o alegeți, câte
un rând per zi lucrătoare, cu o etichetă de status:

| Status | Înseamnă |
|---|---|
| **În așteptare** | Așteaptă managerul |
| **Aprobat** | Acordat — înlocuiește tura în acele zile |
| **Respins** | Refuzat |
| **Anulat** | Retras, de dvs. sau de manager |

---

<a id="signout"></a>

## Deconectare

Folosiți **Deconectare** când ați terminat — mai ales pe o tabletă comună, ca
următoarea persoană să nu se ponteze pe contul dvs.

---

<a id="problems"></a>

## Probleme

| Ce vedeți | Ce faceți |
|---|---|
| Numele meu nu este în listă | Nu vi s-a setat un PIN — cereți administratorului |
| Codul companiei este refuzat | Verificați-l; poate a fost regenerat |
| „Pontarea necesită amprenta” | V-ați autentificat cu PIN-ul, dar aveți un dispozitiv înregistrat. Deconectați-vă și folosiți butonul de amprentă |
| „Locația este necesară pentru pontare” | Permiteți locația în browser, apoi reîncercați |
| Locația apare ca *indisponibilă* | Permisă, dar încă fără semnal — ieșiți afară sau așteptați și reîncercați |
| Se cere o fotografie și camera nu pornește | Va fi cerută până o faceți; cereți administratorului să vă ponteze |
| Am uitat să mă pontez la ieșire | Spuneți managerului; poate corecta înregistrarea |
| M-am pontat la șantierul greșit | Spuneți managerului; poate corecta |
| Butonul de amprentă nu face nimic | Browserul sau dispozitivul poate să nu îl suporte, ori nu este nimic înregistrat pe acest dispozitiv — folosiți PIN-ul |

**La un terminal de amprentă** (cititorul de pe perete, nu acest kiosk): dacă
degetul nu este recunoscut, încercați din nou, încet, cu degetul curat și uscat.
Eșecurile repetate înseamnă de obicei un senzor murdar sau că a fost înrolat un
singur deget — cereți să vi se adauge un al doilea, ca o rănire la o mână să nu vă
blocheze accesul.

---

*Acest ghid descrie aplicația așa cum este instalată. Dacă un ecran nu corespunde
cu ce este scris aici, aplicația are dreptate și această pagină trebuie
actualizată.*
