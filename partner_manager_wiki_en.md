# Partner Manager Guide

What a partner manager can do in epontez.

> **Anchors are stable** and shared with the other guides: a topic has the same
> `id` here as in the admin and site manager guides, and in the Romanian
> versions.

**Contents** — [What a partner manager is](#role) · [Logging in](#login) ·
[Navigation](#navigation) · [Clock](#clock) · [Employees](#employees) ·
[Your password](#password)

---

<a id="role"></a>

## What a partner manager is

You manage the people belonging to one or more **partner** companies — the
collaborators working on a client's sites. An administrator at that company
assigns you the partners you are responsible for, and everything you see is
limited to employees linked to them.

**Your sections are fixed at two: Clock and Employees.** Unlike a site manager,
this pair cannot be changed or extended, so there is no Timesheets, Settings,
Program, Terminals or Plan for this role.

One consequence is worth knowing before anybody asks you about it:

> **Employees linked to a partner cannot request time off.** Leave is their own
> employer's business, not the client company's, so it is refused both in this
> dashboard and at the employee kiosk. Their annual leave balance fields are
> disabled for the same reason.

---

<a id="login"></a>

## Logging in

Go to `/login` with your email and password.

- **Forgotten password** — *Forgot password?* emails a single-use link valid for
  a limited time.
- **Deactivated account** — you get a specific message, and a password reset will
  not help while inactive. Ask the company's administrator to reactivate you.
- Changing your password ends your sessions in other browsers.

A language picker — **English, Romanian, German** — is in the top-right corner.

---

<a id="navigation"></a>

## Navigation

Two sections:

| English | Romanian |
|---|---|
| Clock | Pontaj |
| Employees | Angajați |

Some Romanian companies are configured to say **sediu** rather than **șantier**
throughout, so labels may differ between the companies you work with.

Your name, *Change password* and *Sign out* are in the bottom bar.

---

<a id="clock"></a>

## Clock (Pontaj)

Clocking your partner's people in and out.

> At least one active site must exist at the client company before anyone can be
> clocked in.

Employees are grouped into sections by their default site, ordered
**alphabetically** and always in the same place. Names containing numbers sort
naturally, so *Sediu T5* comes before *Sediu T13*.

<a id="clock-visiting"></a>

### Someone who worked at another site

An employee who clocked somewhere other than their default site — typically by
presenting a finger at that site's terminal — appears **twice**: under their own
site, and under the site they worked at, badged **(visiting)**.

- Either row acts on the same person; they are not two records.
- The badge only appears when they *have* a default site to be away from.
- Each row shows only its own section's clockings.
- A row for somebody currently clocked in elsewhere reads as not clocked, with a
  muted note, and its button is disabled.

<a id="clock-calendar"></a>

### Calendar view

One column per employee, one row per day of the selected month.

| Cell | Meaning |
|---|---|
| **HH:mm – HH:mm** | Finished — click to edit |
| **HH:mm –** | Still clocked in — click to clock out or edit |
| Diagonal stripes | Time off |
| Greyed out | Outside the editable window the company has set |

<a id="clock-colours"></a>

### What the colours mean

| Colour | Meaning |
|---|---|
| **Green** | An ordinary day |
| **Purple** | Beyond the plan — see below |
| **Pink / amber** | Weekend / public holiday |
| **Yellow corner triangle** | In after the shift started, or out before it ended |

**Purple** means overtime against the company work schedule, weekend or holiday
hours, **or** work outside the assigned shift — in more than **15 minutes** early,
or out more than 15 minutes late. On a day with no shift assigned, that last rule
is measured against the widest window that employee's role ever works.

Purple means *more* than planned; late in or early out shows the **yellow
triangle** instead. Hover a cell for the reason.

<a id="clock-select"></a>

### Selecting cells

Click cells to select them (they highlight blue), then choose **Clock in**,
**Clock out**, **Final** (both ends of a past day) or **Time off**. Days on
approved leave and people already clocked in are not selectable.

An **invalidated** clocking is not attendance and is ignored by the calendar, the
row status, selection and the summary counts. An *open* event still counts as in
progress, since that is the only way to clock the person out.

<a id="clock-table"></a>

### Table view

A list per site with each employee's status, last clock-in, site and note. **Clock
in** takes a site (their default is pre-selected) and an optional note; **Clock
out** takes a note. The pills above each table count **Completed**, **In
progress** and **Not clocked**.

<a id="clock-manual"></a>

### Adding a clocking by hand

**+ Add clocking** records a historical entry for any of your employees and any
date — the fix for a missed punch. Set the clock-in, optionally the clock-out, the
site and a note.

<a id="clock-shift-times"></a>

### Filling times from a shift

A row of **shift chips** appears above the time fields — for example `Tura B ·
08:00–16:00` — listing the shifts belonging to the selected employees' roles.
Click one and the times fill in; they stay editable. An overnight shift's
clock-out lands on the following day. If the company defines no shifts, no chips
appear and the fields fall back to the company work schedule, or 08:00–17:00.

<a id="clock-edit"></a>

### Editing a day

Clicking a finished cell opens the edit dialog; if there are several clockings
that day, pick one. You can correct both times. The **existing note is
read-only** — write in **Append note** and your name and the time are stamped
automatically. Notes are only ever added to, never overwritten.

<a id="clock-bulk"></a>

### Bulk actions

| Type | What it does |
|---|---|
| Clock in | A clock-in on each selected day |
| Clock out | Closes the open clock-in on each selected day |
| Final | Both ends on each selected day |
| Time off | A leave request per day — **refused for partner-linked employees** |

One site, time(s) and note for the whole batch. Conflicts are reported before
anything is saved.

<a id="clock-lock"></a>

### The red lock banner

If the client company has locked clocking, a red banner appears: bulk clocking is
limited to today and past-day edits are refused. It usually means the month has
gone to payroll.

---

<a id="employees"></a>

## Employees

The employees linked to your partners, grouped by their default site.

<a id="employees-filter"></a>

### Filtering

Pills — **Active / Inactive / All** — plus a partner dropdown when you manage more
than one. Both persist in the URL, so a reload or a shared link keeps them.

<a id="employees-columns"></a>

### Columns adjust themselves

**A column no employee in the company uses is hidden.** If nobody has an hourly
rate, there is no Hourly rate column. Name, Status, Created and Actions always
show, and a note under the tables names what is hidden and how to bring it back.
The set does not change as you switch the Active/Inactive/All pill.

<a id="employees-fingerprint"></a>

### The Fingerprint column

| Shown | Meaning |
|---|---|
| **Off** | Not allowed to register a device |
| **Enrolment pending** (amber) | Allowed, nothing registered — **their PIN still clocks them in** |
| **2 devices** | Registered, and their PIN **no longer works for clocking** |

<a id="employees-add"></a>

### Adding an employee

**Last name** and **First name** are required. Then role, email, phone, date of
birth, default site, partner, hourly rate, and a **kiosk PIN** (4–6 digits,
optional, settable later). A duplicate name in the company is refused.

**Annual leave fields are disabled once a partner is selected**, since
partner-linked employees take leave through their own employer.

> To move an existing employee to another site, use **Transfer** on the list, not
> this form.

<a id="employees-edit"></a>

### Editing an employee

- **System ID** is read-only and is the only identifier an employee has.
- **Name** is editable only within **48 hours** of creation, because timesheets
  and exports match on it.
- **Active** requires a **Reason**, written to the activity log with your name and
  the date.
- **Auto-clock** creates that day's clocking automatically — needs a site, a start
  and an end; weekdays only, skipping anyone already clocked or on approved leave.
- **Auto-locate** captures GPS at kiosk clock-in. **With it on, coordinates are
  mandatory** — somebody who blocks location cannot clock in.
- **Kiosk PIN** can be set or cleared.
- **Erase location data** strips GPS from this employee's clockings for a GDPR
  request, keeping the clockings themselves.

<a id="employees-passkey"></a>

### Fingerprint sign-in on the employee's own phone

Switching **Fingerprint** on lets an employee sign in at the kiosk by touching
their own phone's sensor instead of typing a PIN.

Registration needs **two factors**: their PIN *and* a single-use code you issue
here, which is **shown once**. The employee then opens `/kiosk`, chooses *Set up
fingerprint on this device*, and enters both. A PIN alone would let anyone who
watched them type four digits attach their own finger to that account permanently.

- **Once a device is registered their PIN stops working for clocking**, though it
  still works for viewing their hours and requesting leave. A PIN can be handed to
  a colleague; a fingerprint cannot.
- **Switching Fingerprint off deletes every registered device** — a revocation,
  not a pause.
- **Revoking one device restores their PIN at once** — the way back in for a lost
  or flat phone, along with you clocking them from this dashboard.
- It is designed for **personal phones**. On a shared tablet every enrolled finger
  unlocks every passkey on it, so it would not stop one worker clocking in
  another.

<a id="employees-csv"></a>

### CSV export

**Export** gives Active, Inactive or All, with fixed English machine headers
because they are a contract with whatever reads the file. Notes are not exported.

> **Import is not available to this role.** It writes company-wide and can change
> who is active, which would escape the partner scoping everything else applies.

<a id="employees-pdf"></a>

### PDF

**↓ PDF** downloads your active employees grouped by site, with the company
header.

---

<a id="password"></a>

## Your password

**Change password** is in the bottom bar. You need your current password, and the
new one must be at least 8 characters.

Changing it **ends your sessions in other browsers**. That is deliberate: if the
old password had leaked, any session opened with it dies too.

---

*This guide describes the application as deployed. If a screen does not match
what is written here, the application is right and this page needs updating.*
