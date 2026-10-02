# Employee Kiosk Guide

How to clock in and out, check your hours, and ask for time off.

> **Anchors are stable** and shared with the Romanian version: a topic has the
> same `id` in both, so `employee_wiki_en.md#clock-in` and
> `employee_wiki_ro.md#clock-in` are the same topic.

**Contents** — [Getting to the kiosk](#kiosk) · [Signing in](#login) ·
[Fingerprint sign-in](#passkey) · [Home screen](#home) ·
[Clocking in](#clock-in) · [Clocking out](#clock-out) ·
[Location and photos](#location) · [My clocking](#myclocking) ·
[Requesting time off](#timeoff) · [My time off](#mytimeoffs) ·
[Signing out](#signout) · [Problems](#problems)

---

<a id="kiosk"></a>

## Getting to the kiosk

Open `/kiosk` in a browser — on the tablet at your site, or on your own phone.
The kiosk is a full-screen, dark layout separate from the office dashboard, and it
takes on your company's colours and logo once it knows which company you belong
to.

---

<a id="login"></a>

## Signing in

<a id="login-code"></a>

### Step 1 — your company code

Type the code your employer gave you. It looks like **AB1234** — two letters and
four digits. Once accepted, the screen shows your company's logo.

If the code is refused, check it with your administrator; it can be regenerated,
in which case everybody gets a new one.

<a id="login-pin"></a>

### Step 2 — your name and PIN

Pick your name from the list and type your **PIN** (4 to 6 digits).

Only employees who have been given a PIN appear in this list. If your name is
missing, ask your administrator to set one.

<a id="login-return"></a>

### Coming back

The company code is remembered on that device, so next time you go straight to
picking your name.

---

<a id="passkey"></a>

## Fingerprint sign-in

If your employer has enabled it for you, you can sign in by touching your own
phone's fingerprint sensor instead of picking your name and typing a PIN. The
**Sign in with fingerprint** button appears on **both** sign-in steps — including
the first one, before any company code, because your fingerprint identifies both
you and your company at once.

<a id="passkey-setup"></a>

### Setting it up, once per device

You need two things, deliberately: **your PIN** and a **single-use enrolment
code** from your administrator. A PIN on its own is not enough, because anyone
who watched you type four digits could otherwise attach their own finger to your
account for good.

1. Ask your administrator for an enrolment code. They can only see it once, so
   they will read it out or send it to you.
2. On **your own phone**, open `/kiosk` and choose **Set up fingerprint on this
   device**.
3. Enter your company code, your name, your PIN and the enrolment code.
4. Confirm with your phone's fingerprint or face unlock when it asks.

Your fingerprint **never leaves your phone**. Only a key stored inside the
phone's secure chip is used, and your employer never receives your fingerprint.

<a id="passkey-pin-rule"></a>

### Once set up, your PIN no longer clocks you in

This surprises people, so it is worth being clear:

| Action | PIN | Fingerprint |
|---|---|---|
| Clocking in and out | **No longer works** | Yes |
| Viewing your hours | Yes | Yes |
| Viewing your time off | Yes | Yes |
| Requesting time off | Yes | Yes |

The reason is that a PIN can be shared — handed to a colleague in the car park,
which is how somebody ends up clocked in while not at work — and a fingerprint
cannot. So once you hold something that cannot be passed around, the thing that
can is no longer accepted for the action where it would matter.

If you sign in with your PIN and try to clock, you will see **"Clocking needs your
fingerprint. Sign out and use the fingerprint button."**

<a id="passkey-lost"></a>

### If you lose your phone, or the battery is flat

Two ways back:

- Ask your administrator to **clock you in from the office dashboard**.
- Ask them to **revoke the device**, which makes your PIN work for clocking again
  immediately.

Set the fingerprint up again on your new phone when you have one.

> **This is designed for your own phone.** It is not suitable on a shared tablet,
> because every finger enrolled on that tablet would unlock every account
> registered on it.

---

<a id="home"></a>

## Home screen

Once signed in you get four options:

| Option | What it does |
|---|---|
| **Clock in / Clock out** | Record the start or end of your work |
| **My clocking** | Your own hours for a month |
| **Request time off** | Ask for leave |
| **My time off** | The status of your requests |

Your company's logo sits at the top. Everything is in one card, in your
company's colours.

---

<a id="clock-in"></a>

## Clocking in

1. Press **Clock in**.
2. Choose the **site** you are working at. If you have a default site it is
   already chosen; change it if you are somewhere else today.
3. Add a **note** if you want to — for example what you are working on.
4. Confirm.

The screen then shows you are clocked in, with the time.

<a id="clock-autoclock"></a>

### If you are on auto-clock

Some employees have their day recorded automatically by a nightly job. If that
applies to you, the kiosk shows an **Auto-clock** badge and the clocking buttons
are disabled — there is nothing for you to press, and your hours are recorded for
you.

---

<a id="clock-out"></a>

## Clocking out

Press **Clock out**, add a note if you want, and confirm. The site is already
known from your clock-in.

If you forget, your employer may have an automatic clock-out time, in which case
your shift is closed then and a note is added to the record saying so. It is
better to clock out yourself, since the automatic time is the same for everybody.

---

<a id="location"></a>

## Location and photos

Depending on how your employer has set things up, two extra things may be asked
of you.

<a id="location-gps"></a>

### Location

If **auto-locate** is switched on for you, your phone's location is recorded when
you clock in **and** when you clock out, and the record shows whether you were at
the site.

**Location is required in that case.** If you block it, you cannot clock —
you will see **"Location is required to clock in. Allow location access and try
again."** A check you can skip by refusing would not be a check.

Allow location in your browser when it asks. If you see a message about location
being *unavailable* rather than denied, you have allowed it but there is no signal
yet — go outside or wait a moment and try again.

Being away from the site does **not** block you from clocking in. It is recorded
for your manager to see, not used to stop you.

Your coordinates are deleted automatically after **180 days**, and you can ask
your employer to erase them sooner.

<a id="location-selfie"></a>

### A photo, sometimes

Your employer may ask for a photo on a random share of clock-ins. If one is asked
for, the camera opens.

**You cannot skip it by trying again.** Cancelling, denying the camera or closing
the tab only postpones the same photo — the next attempt will ask again until you
provide one. You will see **"A photo is required for this clock-in. Take the photo
to continue — it will be asked for again until you do."**

If your camera is genuinely broken, ask your administrator to clock you in from
the dashboard, which is never asked for a photo.

---

<a id="myclocking"></a>

## My clocking

A read-only view of your own clock events for a month you choose.

- Grouped by day, with a subtotal per day and a total for the month.
- Shows both **actual** and **billable** hours — billable has any unpaid break
  window deducted, which is why the two can differ.
- Entries created automatically carry an **Auto** mark.

If something looks wrong, tell your manager — you cannot change it here, and a
correction they make is recorded with their name.

---

<a id="timeoff"></a>

## Requesting time off

<a id="timeoff-form"></a>

### Filling in the form

1. Press **Request time off**.
2. Choose the **type**:

| Type | For |
|---|---|
| **CO** | Annual leave |
| **CFP** | Unpaid leave |
| **Medical** | Sick leave |
| **Marriage** | Your own wedding |
| **Blood donation** | |
| **Special events** | |
| **Military** | Military obligations |
| **Funeral** | Bereavement |
| **Child birth** | |
| **Excused** | Excused absence |
| **Absent** | Recorded absence |

3. Choose the **first and last day**.
4. Add a **reason** or note if you want to.
5. Submit.

Only **working days** are counted, so a request across a weekend does not use up
extra days.

<a id="timeoff-after"></a>

### After submitting

The request goes in as **Pending** and your manager approves or rejects it. Until
it is **approved** your rostered shift stays in place, so do not treat a pending
request as agreed.

<a id="timeoff-partner"></a>

### If you work for a partner company

If you are linked to a partner — a collaborator rather than the company whose
kiosk this is — **you cannot request leave here**. Arrange it with your own
employer instead.

---

<a id="mytimeoffs"></a>

## My time off

A read-only table of your requests for a month you choose, one row per working day,
with a status badge:

| Status | Meaning |
|---|---|
| **Pending** | Waiting for your manager |
| **Approved** | Granted — it replaces your shift for those days |
| **Rejected** | Refused |
| **Cancelled** | Withdrawn, by you or your manager |

---

<a id="signout"></a>

## Signing out

Use **Sign out** when you are finished — especially on a shared tablet, so the
next person does not clock in as you.

---

<a id="problems"></a>

## Problems

| What you see | What to do |
|---|---|
| My name is not in the list | No PIN has been set for you — ask your administrator |
| The company code is refused | Check it; it may have been regenerated |
| "Clocking needs your fingerprint" | You signed in with your PIN but have a registered device. Sign out and use the fingerprint button |
| "Location is required to clock in" | Allow location in your browser, then retry |
| Location says *unavailable* | Allowed, but no signal yet — go outside or wait and retry |
| A photo is demanded and the camera will not open | It will be asked again until provided; ask your administrator to clock you in instead |
| I forgot to clock out | Tell your manager; they can correct the record |
| I clocked in at the wrong site | Tell your manager; they can correct it |
| The fingerprint button does nothing | Your browser or device may not support it, or nothing is registered on this device — use your PIN |

**At a fingerprint terminal** (the wall-mounted reader, not this kiosk): if your
finger is not recognised, try again slowly with a clean, dry finger. Repeated
failures usually mean a dirty sensor or that only one finger was enrolled — ask
to have a second finger added, so an injury to one hand does not lock you out.

---

*This guide describes the application as deployed. If a screen does not match
what is written here, the application is right and this page needs updating.*
