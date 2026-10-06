# Admin Guide

Everything a company administrator can do in epontez. Sections appear here in the
same order as the navigation bar.

> **Anchors are stable.** Every section carries an explicit `id` (for example
> `<a id="clock-calendar">`) that is **identical in the English and Romanian
> guides**. Link to `admin_wiki_en.md#clock-calendar` or
> `admin_wiki_ro.md#clock-calendar` and both resolve to the same topic. Keep an
> id unchanged even if you reword its heading — something may be linking to it.

**Contents** — [Logging in](#login) · [Navigation](#navigation) ·
[Status](#status) · [Clock](#clock) · [Employees](#employees) ·
[Program](#program) · [Planning](#planning) · [Sites](#sites) ·
[Incidents](#incidents) · [Partners](#partners) · [Timesheets](#timesheets) ·
[Late / early report](#report-late) · [Time off](#timeoff) · [Terminals](#terminals) · [Plan](#plan) ·
[Settings](#settings) · [Your password](#password)

---

<a id="login"></a>

## Logging in

Go to `/login` and enter your email and password.

- **Forgotten password** — use *Forgot password?*. You get an email with a link
  valid for a limited time, usable once.
- **Deactivated account** — you get a specific message rather than a generic
  credentials error. A password reset will **not** help while the account is
  inactive; ask your super admin to reactivate it.
- **Changing your password signs out your other sessions.** This is deliberate:
  if someone else knew the old password, their session dies with it.
- **You stay signed in while you are working.** The session lasts an hour and
  renews on every page you open, so continuous work never logs you out; an hour
  of touching nothing does. That means an unattended screen locks itself, and it
  is also why a tab left open overnight asks you to sign in again.

A language picker sits in the top-right corner of the login page.

---

<a id="navigation"></a>

## Navigation

The top bar links to the sections your role may open. A full administrator sees
all of them:

| English | Romanian | What it is |
|---|---|---|
| Dashboard | Status | Today at a glance |
| Clock | Pontaj | Clocking people in and out |
| Employees | Angajați | The workforce |
| Schedules | Program | Roles, shifts, and the PONTAJ export |
| Sites | Șantiere / Sedii | Work locations, and the incident register |
| Partners | Parteneri | Collaborator companies |
| Timesheets | Fișe pontaj | Hours, costs and exports per month |
| Time off | Concedii | Leave requests |
| Terminals | Terminale | Fingerprint readers |
| Plan | Plan | Vehicles, accommodation and assignments |
| Settings | Setări | Company configuration (admins only) |

**Language** — the picker in the top-right offers **English, Romanian and
German**, and the choice is remembered per browser.

Some Romanian tenants are configured to say **sediu** ("office") instead of
**șantier** ("site") throughout the Romanian interface. A super admin sets this
per company, so your screens may differ from a colleague's at another company.

Your name, *Change password* and *Sign out* are in the bottom bar.

---

<a id="status"></a>

## Status (Dashboard)

Today at a glance.

**Row 1**
- **Clocked in today** — distinct employees with any valid clock event today,
  finished or ongoing
- **Hours this month** — completed hours so far this month, after the break
  schedule if one is configured

**Row 2**
- **Clocked in now** — employees with an open clock-in at this moment
- **Active employees** — current headcount

**Row 3 — click a card to expand a table**
- **Not clocked in last 5 working days** — name, position, default site
- **Time off today** — name, type, status (approved or pending)

**Charts** (last 30 days, one colour per site) — *People per day* and *Hours per
day*.

**Currently clocked in** — employee (with a partner badge if linked), clock-in
time, note.

**Missed clock-outs** — a warning banner listing anyone whose clock-in is still
open from a previous day, so you can correct the record. These are the entries
that most often come from a worker forgetting to present their finger on the way
out.

---

<a id="clock"></a>

## Clock (Pontaj)

Where you clock people in and out, and correct what was recorded.

> **At least one active site must exist** before anyone can be clocked in.

Employees are grouped into **sections by their default site**, and the sections
are ordered **alphabetically**, always in the same place. A site with a number in
its name sorts naturally — *Sediu T5* comes before *Sediu T13*.

<a id="clock-visiting"></a>

### Someone who worked at another site

If an employee clocked at a site that is not their default — most commonly
because they presented their finger at that site's terminal — they appear **twice**:
once under their own site, and once under the site they actually worked at,
badged **(visiting)**.

- Acting on either row acts on the same person; they are not two records.
- The **(visiting)** badge is only shown when the employee *has* a default site
  to be away from. Someone with no default site simply appears under the site
  they worked at, unbadged.
- Each row shows only the clockings belonging to **its own** section, so a site
  never appears to have work that happened elsewhere.
- A row for someone currently clocked in **at another site** reads as not
  clocked, with a muted note, and its clock-in button is disabled — a second
  concurrent clock-in would be refused anyway.

<a id="clock-calendar"></a>

### Calendar view

One column per employee, one row per day of the selected month.

| Cell | Meaning |
|---|---|
| **HH:mm – HH:mm** | A finished clocking — click to edit |
| **HH:mm –** | Still clocked in — click to clock out or edit |
| Diagonal stripes | Time off |
| Greyed out | Outside the editable window (see [Edit past clocking days](#settings-editpast)) |

<a id="clock-colours"></a>

### What the colours mean

| Colour | Meaning |
|---|---|
| **Green** | An ordinary day's clocking |
| **Purple** | Something beyond the plan — see below |
| **Pink / amber column** | Weekend / public holiday |
| **Yellow corner triangle** | Clocking did not honour the scheduled shift: in after it started, or out before it ended |

A cell turns **purple** for any of:

- **overtime** against the company work schedule;
- **weekend or public-holiday** hours;
- **work outside the assigned shift** — clocked in more than **15 minutes**
  before the shift started, *or* out more than 15 minutes after it ended.

On a day with **no shift assigned**, the last rule still applies, measured
against **the widest window that employee's role ever works** — the earliest
start and latest end across all of that role's shifts. So someone who turns up
for an unrostered late shift is not flagged merely for being outside the morning
one; only work outside *everything* the role runs is marked.

Hover any purple cell and the tooltip says which of the reasons applies.

Purple means *more* than planned. Arriving late or leaving early is the opposite
and is shown by the **yellow corner triangle** instead.

> Overnight shifts are not judged by the 15-minute rule. A clock-out at 05:00
> cannot be told apart from an early departure without a date, so the system
> declines to guess rather than flag honest night work.

<a id="clock-select"></a>

### Selecting cells

Click cells to select them (they highlight blue), then pick an action from the
toolbar: **Clock in**, **Clock out**, **Final** (both ends of a past day), or
**Time off**. Days already covered by approved leave, and employees already
clocked in, are not selectable.

An **invalidated** clocking is not attendance: it is ignored by the calendar, the
row status, bulk selection and the per-site summary counts. An *open* event still
counts as in progress regardless, because that is the only way to clock the
person out.

<a id="clock-table"></a>

### Table view

A list per site with each employee's status, last clock-in, site and note.

- **Clock in** — choose the site (their default is pre-selected), optional note.
- **Clock out** — optional note.

The per-site pills above each table count **Completed**, **In progress** and
**Not clocked** for that site.

<a id="clock-manual"></a>

### Adding a clocking by hand

**+ Add clocking** records a historical entry for any employee and date — the fix
for a missed punch. Set the clock-in, optionally the clock-out, the site and a
note.

<a id="clock-shift-times"></a>

### Filling times from a shift

In the add-clocking dialog, a row of **shift chips** appears above the time
fields — for example `Tura B · 08:00–16:00`. They list the shifts belonging to
the **selected employees' roles**. Click one and the times fill in; you can still
edit them.

- For a start-and-end entry both ends are filled; for a single-time entry only
  the relevant one.
- An overnight shift's clock-out is placed on the following day.
- Select people from two roles and you get both sets of chips.
- If your company has no shifts defined, no chips appear and the fields fall back
  to the company work schedule, or 08:00–17:00.

<a id="clock-edit"></a>

### Editing a day

Clicking a finished cell opens the edit dialog; if there are several clockings
that day, pick one. You can correct both times. The **existing note is
read-only** — write in **Append note** and an audit stamp with your name and the
time is added automatically. Notes are only ever added to, never overwritten, so
the history of a correction survives.

<a id="clock-bulk"></a>

### Bulk actions

| Type | What it does |
|---|---|
| Clock in | A clock-in on each selected day |
| Clock out | Closes the open clock-in on each selected day |
| Final | Both ends on each selected day |
| Time off | A leave request for each selected day |

**Granting leave without selecting cells** — press *Add time off* with nothing
selected and you get editable **start and end** dates plus the employee
checkboxes, so an interval can be granted directly. Select cells first and the
dates become read-only instead: there the grid *is* the range, and editable
fields beside highlighted days would contradict them.

You set one site, time(s) and note for the whole batch. Conflicts — approved
leave on a selected day, an overlapping clocking — are reported before anything
is saved.

<a id="clock-lock"></a>

### The red lock banner

If [Clocking locked](#settings-lock) is on, a red banner appears. While locked,
bulk clocking is limited to today and past-day edits are refused. Use it to
freeze a month you have already sent to payroll.

---

<a id="employees"></a>

## Employees

The workforce, grouped by **default site**, with employees who have none in a
*No site assigned* group first.

<a id="employees-filter"></a>

### Filtering

Pills — **Active / Inactive / All**. A partner dropdown appears if you have
partners. Both are kept in the URL, so a reload or a shared link preserves them.

<a id="employees-columns"></a>

### Columns adjust themselves

**A column with no data anywhere in your company is hidden.** If nobody has an
hourly rate, there is no Hourly rate column; if nobody uses auto-locate, that
column is gone. Name, Status, Created and Actions are always shown.

A note under the tables names what is hidden and how to bring it back:

> Columns hidden because no employee uses them yet: **Email, Phone, Fingerprint**
> — switch any of these on from an employee's edit page and the column comes back.

The set does **not** change when you switch the Active/Inactive/All pill, so
columns never appear and disappear as you filter.

<a id="employees-fingerprint"></a>

### The Fingerprint column

Three states, and the middle one matters:

| Shown | Meaning |
|---|---|
| **Off** | Not allowed to register a device |
| **Enrolment pending** (amber) | Allowed, but nothing registered yet — **their PIN still clocks them in** |
| **2 devices** | That many registered devices — and their PIN **no longer works for clocking** |

<a id="employees-add"></a>

### Adding an employee

**Add employee**, then:

| Field | Notes |
|---|---|
| **Last name**, **First name** | Both required |
| Role (position) | Chosen from your [Program](#program-roles) list |
| Email, Phone | Optional |
| Date of birth | Optional |
| Default site | Pre-selects the site at the kiosk and groups the employee in these lists |
| Partner | Links them to a collaborator — see [Partners](#partners) |
| Hourly rate | Base rate for payroll; multipliers are per company in Settings |
| Annual leave (CO) — allowed days | Disabled when a partner is selected |
| Kiosk PIN | 4–6 digits; leave blank if they do not need the kiosk. Can be set later |

A duplicate name in the same company is refused.

> To move an existing employee to another site, use **Transfer** on the list —
> not this form.

<a id="employees-edit"></a>

### Editing an employee

Everything above, plus:

- **System ID** — read-only. This is the only identifier an employee has; there
  is no separate staff number.
- **Name** — editable only within **48 hours** of the employee being created,
  because the name is what timesheets and exports are matched on.
- **Active** — switching it requires a **Reason**, which is written to the
  activity log with your name and the date.
- **Activity log** — append-only history of status changes and edits.
- **Auto-clock** — a daily job creates that day's clocking automatically. Needs a
  site, a start and an end; weekdays only, and it skips anyone already clocked or
  on approved leave. Times are read in Europe/Bucharest.
- **Auto-locate** — captures GPS at kiosk clock-in and judges whether they were
  on site. **With this on, coordinates become mandatory**: a worker who blocks
  location cannot clock in. A location check that can be skipped is not a check.
- **Fingerprint (passkey)** — see below.
- **Kiosk PIN** — set or clear it.
- **Erase location data** — removes all GPS coordinates from this employee's
  clockings, for a GDPR erasure request. The clockings themselves are kept.

<a id="employees-passkey"></a>

### Fingerprint sign-in on the employee's own phone

Switching **Fingerprint** on lets that employee sign in at the kiosk by touching
their own phone's sensor instead of picking a name and typing a PIN.

Registration takes **two factors** on purpose — the employee's PIN **and** a
single-use code you issue here. A PIN alone would let anyone who watched a
colleague type four digits attach their own finger to that colleague's account
permanently.

1. Press the button to generate an enrolment code. **It is shown once** — copy it.
2. The employee opens `/kiosk`, chooses *Set up fingerprint on this device*, and
   enters their PIN and the code.
3. The device then appears in the list here, with the date last used.

Important consequences:

- **Once they have a registered device, their PIN stops working for clocking** —
  though it still works for viewing their hours and requesting leave. A PIN can
  be handed to a colleague in the car park; a fingerprint cannot.
- **Switching Fingerprint off deletes every registered device.** It is a
  revocation, not a pause.
- **Revoking one device restores their PIN immediately** — that is the way back
  in for a lost or flat phone, along with you clocking them from this dashboard.
- A **Synced passkey** badge means the credential is in the employee's platform
  keychain and may appear on their other devices.
- This is for **personal phones**. On a shared tablet every enrolled finger
  unlocks every passkey on it, so it would not prevent one worker clocking in
  another — [Terminals](#terminals) are the answer there.

<a id="employees-csv"></a>

### CSV import and export

- **Export** — choose Active, Inactive or All. Columns are fixed machine headers
  in English (`lastName`, `firstName`, `position`, …) because they are a contract
  with whatever reads the file. Notes are not exported.
- **Import** — **administrators only**, not site managers: it writes company-wide
  and can change who is active, which would escape the site scoping every other
  manager screen applies.
  - `lastName` and `firstName` are required; the file is rejected without both.
  - Existing employees are matched by **name** (case-insensitive), falling back
    to **email**.
  - You get a **preview** first: to add, to update, unchanged, and any errors —
    nothing is written until you confirm.
  - A status change writes a line to that employee's activity log.
  - Unchanged rows are skipped.

<a id="employees-pdf"></a>

### PDF

**↓ PDF** downloads the active employee list grouped by site, with your company
header.

<a id="employees-hide"></a>

### Hiding someone

An **inactive** employee shows a **Danger zone** with **Hide employee**. Hidden
employees disappear from the clock page, the kiosk, the employee list and the
auto-clock job. **Only a super admin can unhide**, so use it for people who have
left rather than for a temporary absence.

---

<a id="program"></a>

## Program (Schedules)

Your company's official work schedule: the roles people hold, the shifts those
roles run, and the monthly PONTAJ export. **Administrators only.**

<a id="program-roles"></a>

### Roles (funcții)

The canonical list of job titles. Each row shows its shifts and how many
employees hold it.

- **Add** a role; names are unique per company, ignoring case.
- **Rename** — renaming onto an existing name offers to **merge**: the employees
  move across, their shift assignments are cleared, and the old role is deleted.
- **Deactivate** instead of deleting when a role is still in use. A delete is
  refused while anyone holds it.
- An amber card lists **active employees with no role at all** — worth clearing,
  since a role is what connects someone to shifts.

<a id="program-shifts"></a>

### The shift library

Shifts belong to the **company**, not to one role, and a role can run several
shifts while a shift can serve several roles.

1. Create the shift once in the library — name, start, end, optional note.
2. Attach it to the roles that run it, from either side: tick roles on the shift,
   or tick shifts on the role. Unticking detaches.

Notes:

- `end` at or before `start` means the shift **crosses midnight**; it is allowed
  and marked with an *overnight* badge.
- Two shifts may share a name — every picker shows `name · 07:00–16:00`, which
  tells them apart. What is refused is the same name **and** the same hours in one
  company, which would be two indistinguishable rows.
- Shifts are **informational**. Nothing in the hours, overtime or cost arithmetic
  reads one. They drive the rota, the adherence marks and the PONTAJ sheets.
- Nobody has a permanent shift. Which shift a person works is a **per-day** fact,
  set in [Planning](#planning), because in practice it changes day to day.
- Deleting a shift also deletes its dated assignments, so those days go blank in
  Planning.

<a id="program-export"></a>

### The PONTAJ export

The month picker and the green **Excel** button sit in the page header, with two
filters beside them.

| Filter | Options |
|---|---|
| **Role** | *All roles* (default), or one role |
| **Partner** | *No partner* (**default**), *All partners*, or one partner |

> **The partner filter defaults to excluding collaborators.** A PONTAJ sheet is a
> payroll document for your own staff, and a collaborator's workers are billed
> through their partner. Choose *All partners* if you do want everyone — and
> check which you have selected before sending the file to payroll.

Both filters stay in the address bar, so a reload keeps them and the download
carries exactly what you see.

Two sheets, identical in layout so they line up column for column:

- **Program** — the plan for the whole month.
- **Pontaj** — the same plan **truncated at today**, annotated with attendance. On
  a scheduled day somebody worked, the row reads normally; on one they did not,
  the hours become **0** and the cell is drawn dark red with an *Absent* note. A
  past month runs to its end; a future month is empty, because nobody can be
  absent from a shift that has not happened.

The **Pontaj** view also carries a per-day row for the **site actually clocked
at** — labelled *Șantier pontat* or *Sediu pontat* to match your own vocabulary.
It is a different fact from the **Sediu** column, which is the employee's
*assigned* site and shows one value for the whole month: a day worked at another
site is visible only in that row, because a terminal records the site its reader
is bolted to. A day split between two sites shows the first with a `+`.

Both report the **planned** shift times and hours. A day with nothing rostered is
blank in both, even if somebody clocked — the sheet is schedule-driven, so there
are no planned hours to report the work against.

Columns are `Nr.Crt | Nume | Functie | Sediu | Program de lucru | 1..n | total |
Bonus/RON`, with a live `SUM()` per employee. **Sediu** is the employee's default
site, one merged value per person. Headings are **always Romanian** whatever your
interface language, because the file's shape is a contract with whoever receives
it. Capped at 450 employees.

Approved leave replaces the shift: the leave code (`CO`, `CM`, `CFP`, `CS`…) goes
in *Inceput*, the end and break blank out, and the day books **0 hours** so the
monthly total still counts worked hours only.

---

<a id="planning"></a>

## Planning (the rota)

Reached from **Planning** on a role in Program, or the coloured button in the
page header. **Administrators only.**

<a id="planning-grid"></a>

### The grid

Employees down the side, days of the month across the top — the shape that
answers *is every night covered?*, which a per-person calendar cannot.

- Each shift has its own colour, stable across the grid.
- Weekends are pink, public holidays amber.
- A purple **✓** marks a day somebody worked with **nothing rostered**.
- An **All roles** option in the role dropdown shows everyone at once; the legend
  lists each shift once even when several roles share it.

<a id="planning-automation"></a>

### Two pills at the top: what writes to this rota by itself

Above the grid, on both Program and Planning, two pills say whether the
automatic mechanisms are on — green for on, grey for off. Both write to the rota
with nobody pressing anything, so if a grid changed overnight these tell you
which could have done it. Hover either for the full explanation.

| Pill | What it does |
|---|---|
| **⊕ Auto-fill shift on clock-in** | Rosters a **blank** day when somebody clocks in on it |
| **◎ Shift-change detection** | Moves a day **already rostered** when the clocking fits another shift better |

They are deliberately different jobs, and a day can show one then the other —
filled in the morning, corrected the following night. Both are switched on per
company in [Settings](#settings-autofill).

<a id="planning-cells"></a>

### Reading a cell

Each cell is filled with its shift's colour and stacks the shift's short name
over its start and end:

```
  TB
07:00
16:00
```

Hovering gives the whole picture for that one day:

```
Tura B · 07:00–16:00
2026-10-14
Clocked: 07:12 – 16:03
Late in
```

A day nobody clocked reads **No clocking** on the third line rather than leaving
it blank. The corner glyph is the adherence verdict — green ✓ on time, amber ✓
late in or early out, red ✗ scheduled but absent — and sits on a white backing so
it stays readable whatever colour the shift is.

<a id="planning-select"></a>

### Selecting several cells at once

Rostering one dialog at a time is slow, so **empty cells can be clicked to build
a selection**, then **Allocate shift (n)** applies one shift to all of them.

- **Only empty cells join a selection.** A cell that already has a shift, or
  approved leave, opens the dialog as before — editing one of those is a
  different act from rostering a blank day.
- **One function at a time.** A shift belongs to a function, so a selection
  spanning two could not be satisfied by any one shift; clicking into another
  function starts a fresh selection rather than failing when you try to allocate.
- **Nothing selected?** Everything behaves exactly as it always did.
- Selected days are grouped into runs of consecutive dates per employee, so a
  fortnight for four people is four operations rather than fifty-six. Every day
  you picked is honoured, weekends included — you chose them deliberately.

Pressing *Allocate* captures the cells and clears the selection; cancelling the
dialog means re-selecting.

<a id="planning-assign"></a>

### Assigning a shift

Click any cell — or use the From/To fields for a range, which is the sane way to
enter a fortnight of nights.

- **A range is split into runs of working days.** 2–13 February becomes two
  assignments, not one long one that swallows the weekend. Saturdays, Sundays and
  public holidays are left blank unless you tick *include non-working days*.
- **A single day is always honoured as-is** — that is how you put somebody on a
  Saturday.
- An **open-ended** assignment (no end date) necessarily covers every day,
  weekends included, since there is no last day to stop at. The dialog says so.
- **Overlaps are reshaped, not refused.** Putting somebody on nights from the
  10th ends their open-ended morning assignment on the 9th.
- You always get a **preview** of what would change, and a confirmation step
  whenever anything would be altered.

<a id="planning-switch"></a>

### Swapping two people for one day

On a single day, the dialog offers a **Switch shift** panel listing colleagues on
a different shift that day. A swap:

- carves a **single day** out of each person's assignment, leaving the rest of
  both rotas untouched;
- marks both days **Switched**, with a note naming who did it and with whom;
- requires the two to hold the same role and to be on different shifts that day.

A switched day is never overwritten by automatic shift detection — a human
decision outranks the detector.

<a id="planning-clear"></a>

### Clearing a day

**Clear this day** carves that one day out of the surrounding assignment,
splitting it in two if the day sits in the middle. It does not restore whatever
was reshaped earlier to make room.

<a id="planning-timeoff"></a>

### Allocating leave from the rota

- **Allocate time off** beside *Assign shift* handles a range across several
  employees.
- Inside the cell dialog, a **Shift / Time off** toggle handles the day you
  clicked.
- A day already on approved leave offers **Remove time off** in place of *Clear
  this day*. Leave is stored one row per working day, so that is a single row,
  and it is **cancelled rather than deleted** — the audit trail survives and,
  since only approved leave overrides, the shift underneath reappears by itself.
- You may assign a shift to a day already covered by leave; the rota underneath
  is still being edited, and the dialog says as much.

Both routes go through the same checks as the Time off section, so overlaps and
clocked-on-a-leave-day behave identically everywhere.

<a id="planning-table"></a>

### The table under the grid

One row per **scheduled day** — `Employee | Shift | Day | In | Out | Status |
Note` — where In and Out are that day's first clock-in and last clock-out.

**Each employee is collapsed**, and clicking their row opens their days. A month
for one function runs to hundreds of rows, so the header carries the tally that
matters — ✓ on time, ✓ late, ✗ absent, ✓ unplanned — and the count of hidden
days. Somebody with a red ✗ is still one visible line, so collapsing hides the
detail without hiding the signal.

**The table stops at today**, while the grid still shows the whole month. Every
column except Shift reports what actually happened, and a future day has none of
it, so those rows were a page of blanks. A past month is complete; a future month
shows an empty table and a full grid. Nothing is lost — clicking a future cell in
the grid still opens the assign dialog.

| Tint | Meaning |
|---|---|
| **Red** | The plan was broken: in after the start, out before the end, or no clocking at all on a day whose shift was already due |
| **Purple** | There was no plan: somebody worked a day with nothing rostered. Status reads **Unplanned**, and the action offers *Assign shift* rather than *Clear this day* |

The **Status** column also distinguishes how a day came to be rostered:

| Status | Meaning |
|---|---|
| *(blank)* | Put there by a person |
| **⇄ Switched** | A one-day swap between two colleagues |
| **⊕ Auto-filled** | Written by [auto-fill](#settings-autofill) because somebody clocked in on an unrostered day. The note records the clock-in and which shift was matched |
| **◎ Detected** | Moved by shift-change detection; hover to see what it replaced |

"Already due" means the day is past, or it is today and the shift's start time has
passed — so a shift later today is not yet a no-show.

Approved leave is **not** absence and takes precedence over both.

---

<a id="sites"></a>

## Sites (Șantiere / Sedii)

Your work locations.

<a id="sites-add"></a>

### Adding a site

Name, optional address, and an optional **map pin**. Search for an address or
click the map to place it.

<a id="sites-coords"></a>

### Why coordinates matter

Coordinates are what make the on-site check possible. Without them, a clock-in
can never be judged — however tight your [radius](#settings-radius) — so those
rows are badged amber **No coordinates**. Otherwise the gap stays invisible until
somebody wonders why every location pin is grey.

Being off-site is **recorded, not blocked**. It is evidence for whoever reviews
the timesheet, not a gate on clocking in.

<a id="sites-autoclockout"></a>

### Per-site auto clock-out

Enable it and set a time, and anyone still clocked in **at that site** is clocked
out then. A site's rule takes priority over the
[company-wide one](#settings-autoclockout).

<a id="sites-partner"></a>

### Partner link

A site can belong to one partner. The Partners page then lists the site beneath
that partner.

<a id="sites-status"></a>

### Active, inactive, hidden

Pills filter **Active / Inactive / All**. A site must be **inactive before it can
be hidden**, and hidden sites are invisible to admins, the kiosk and the
auto-clock job — **only a super admin can unhide one**.

Every change appends an audit line to the site's notes: *Updated by «name» · date
(fields changed)*.

---

<a id="incidents"></a>

## Incidents

A per-site incident register, for Legea 319/2006. The buttons are on each site's
row and are available to every role that can see Sites.

<a id="incidents-add"></a>

### Logging an incident

**Add Incident**, then:

| Field | Options |
|---|---|
| **Type** | Accident · Near miss · Dangerous occurrence · Occupational disease |
| **Severity** | Minor · Moderate · Serious · Fatal |
| **Date of incident** | When it happened |
| **Date logged** | When it was recorded |
| **Description** | Required |
| **Employees involved** | Picked from the employees assigned to that site |
| Witnesses | Optional |
| Corrective actions | Optional |
| **Reported to authorities** | Yes/no |

<a id="incidents-pdf"></a>

### The register PDF

**Incidents PDF** asks for a month and produces a landscape A4 register for that
site and month. If there is nothing recorded, it tells you so rather than
producing an empty file.

---

<a id="partners"></a>

## Partners

Collaborator companies whose people work on your sites.

Fields: name, address, email, phone, CUI, active. The table shows each partner's
associated **sites** as sub-rows. Pills filter **Active / Inactive / All**.

Two things follow from linking an employee to a partner, both deliberate:

- **They cannot request time off.** Leave is their own employer's business. It is
  refused both in the dashboard and at the kiosk.
- **Their annual leave balance fields are disabled** in the employee form, for
  the same reason.

The **partner filter** on the employees and clock pages is a different thing from
the *Partners* section: it filters **employees**, not pages. Separately, a site
manager can be configured to see only employees who are **not** linked to a
partner.

---

<a id="timesheets"></a>

## Timesheets (Fișe pontaj)

Hours, costs and exports, a month at a time.

<a id="timesheets-filters"></a>

### Choosing what you see

The header carries the month picker and filters for **site**, **employee** and
**partner** (*All partners* or *No partner*). Use the arrows or the month input
to move between months.

<a id="timesheets-read"></a>

### Reading the table

Each employee is a block of their clockings for the month, with daily subtotals
and a monthly total.

| Marker | Meaning |
|---|---|
| **Auto** pill | Created by the auto-clock job, not by a person |
| **Purple row** | Overtime, weekend, holiday, or work outside the assigned shift — the same rules as the [clock colours](#clock-colours) |
| Struck through / faded | Marked invalid; not counted anywhere |
| Partner badge | Employee is linked to a collaborator |

The employee header shows `| default site: «name»` when one is set.

<a id="timesheets-gps"></a>

### Location pins

A shift is one record with **two** positions, so each row can carry two pins:
**In** and **Out**. Each links to OpenStreetMap at that exact point.

| Pin | Meaning |
|---|---|
| **Green** | On site |
| **Red** | Off site |
| **Grey** | A position was recorded, but the site had no coordinates to judge it against — "cannot verify" |
| No pin | No position was captured |

This is the only place an **employee's** position is shown; every other map link
in the app points at a site.

**The verdict is frozen at the moment of clocking.** Changing the radius, or
adding coordinates to a site, affects later clockings only — re-judging a closed
month by changing a setting today is exactly what would make attendance data
indefensible.

Coordinates are erased automatically after **180 days**, and on demand from the
employee's edit page.

<a id="timesheets-edit"></a>

### Correcting a clocking

Click a row to edit its times, or mark it invalid. Notes are append-only with an
audit stamp, as on the clock page. Re-validating an invalid entry re-runs the
overlap check, so a salvaged record cannot end up overlapping a valid one.

<a id="timesheets-download"></a>

### Downloads

The download menu offers:

| File | Contents |
|---|---|
| **PDF** | The monthly timesheet, with your company header and logo |
| **Excel** | The same data per employee, or per site |
| **Payroll CSV** | Machine-readable, **including hourly rates** |
| **Late / early report** | Who arrived late or left early, and by how many minutes — see below |

All three honour the filters you have set.

> **Site managers cannot download any of these**, even if they can read the page.
> The payroll file contains wages, and that is enforced on the server, not just by
> hiding the button.

---

<a id="report-late"></a>

### The late / early report

Also under *Download Excel* on [Program](#program-export), and honouring the
filters set on whichever page you start from.

Employees down the left, days across the top, and seven rows for each person:
clock-in, clock-out, minutes late, minutes early, shift start, shift end, and the
site clocked at. Three totals follow the last day — late minutes, early minutes,
and planned shift hours — and **the worst offender is first**, which is the point
of the report.

The end that was breached is tinted: red for a late arrival, amber for an early
departure, and the clock time is tinted with the minutes it produced.

Four things it deliberately does not do:

- **No grace period.** It states the minutes; a tolerance belongs in how you read
  them, not hidden inside the number.
- **Employees with no breach are left out.** The ordering is a ranking, and a
  sheet of blank rows would be unusable.
- **A day nobody clocked produces nothing** — that is absence, which the PONTAJ
  clocking view already reports as a red zero.
- **Overnight shifts show their times but not the minutes.** `HH:mm` carries no
  date, so a 23:00 clock-out on a 22:00–06:00 shift would compute as six hours
  *early*. A cell note says so.

A day with no assigned shift falls back to the company work schedule where one is
enabled, noted on the cell.

Admin-only, like the other exports: the file names individuals and quantifies
their lateness.

---

<a id="timeoff"></a>

## Time off (Concedii)

Leave requests, from you or from employees at the kiosk. A pending request puts an
asterisk on the nav tab.

<a id="timeoff-types"></a>

### Types

`CO` annual leave · `CFP` unpaid · `MEDICAL` sick · `MARRIAGE` · `BLOOD_DONATION`
· `SPECIAL_EVENTS` · `MILITARY` · `FUNERAL` · `CHILD_BIRTH` · **`MATERNITY`** ·
`EXCUSED` · `ABSENT`.

**Maternity** is separate from *Child birth* on purpose: the latter is the few
days granted around a birth, maternity the long statutory period, and a pontaj
reports them separately. Its payroll code is `CMAT`, since `CM` is already sick
leave and `CS` already marriage.

<a id="timeoff-read"></a>

### Reading the table

Leave is stored **one row per working day**, so the table has separate **Date**,
**Day** and **Days** columns and the summary pills count working days — not
calendar days. A request over a weekend does not inflate the count.

<a id="timeoff-actions"></a>

### Actions

**Approve**, **Reject** or **Cancel**. `requestedBy` records who submitted it.

**Only approved leave displaces a scheduled shift.** A pending request has not
been granted, so the rota keeps showing the shift and marks the cell with a small
dot instead.

The override is applied when the rota and the sheets are *read*, never written
back — so cancelling leave makes the shift underneath reappear by itself, with no
repair step.

A per-request **PDF** is available for signing.

---

<a id="terminals"></a>

## Terminals (Terminale)

Physical fingerprint readers. **Administrators only.**

<a id="terminals-why"></a>

### Why a terminal rather than a tablet

A terminal does **1:N identification**: the worker presents a finger and the
device answers *who it is*, with nobody selected first. That is the only
arrangement that actually prevents one worker clocking in another. A tablet's own
sensor cannot, because the operating system treats every enrolled finger as equal.

Two further things come free: **the site is certain**, because the reader is
bolted to it — far more reliable than a self-reported choice in a dropdown — and
**no fingerprint ever leaves the device**. Only a number mapping a device slot to
an employee is stored, which keeps the platform out of scope for biometric data
protection rules.

<a id="terminals-add"></a>

### Registering a reader

Add it with a name, serial number, vendor and model, then bind it to a **site** —
that binding is what attributes punches, so set it before enrolling anybody. A
panel warns you if a terminal has no site.

<a id="terminals-setup"></a>

### The Configure panel

A copy-and-paste panel for whoever installs the reader: host, port, the intake
URL, the site binding, an **IP allowlist**, and the editable **ISUP account and
key** that the terminal dials out with.

- The **account** is set on the terminal's own *Comm. → EHome* screen and is
  **unrelated to its serial number** — you need both.
- After changing the EHome key, allow up to **five minutes**. The receiver reads
  its device list on a timer, and until it refreshes it still presents the old key
  and the terminal is refused. A run of key-rejection messages right after a
  change is this, not a fault.

<a id="terminals-mappings"></a>

### Mapping employees to the device

The table lists each device user ID, the employee it maps to, and whether the
terminal holds an **RFID card** for them. A card badge means the reader reported
one; its number is in the tooltip. Cards added at the keypad show up after the
next refresh.

Rows are flagged when they disagree:

| Flag | Meaning |
|---|---|
| **mapped here but absent on the terminal** | We have a mapping the reader does not know |
| **mapped here to «name» — wrong mapping** | The reader holds a different name for that ID |
| **not mapped** | A device user belonging to nobody — usually an installer's own account |

<a id="terminals-fixname"></a>

### Fixing a mistyped name

If you correct an employee's name after pushing them to a reader, the reader keeps
the old spelling and the row is flagged as a wrong mapping. Use **Fix name on
device** on that row.

> Do **not** try to fix this by pushing the employee again. A re-push is refused
> as a taken ID and the mapping is deleted, after which their punches stop
> resolving. *Fix name on device* changes only the name, leaving enrolled
> fingerprints and door rights untouched.

<a id="terminals-push"></a>

### Sending employees to a terminal

Pushing the **identity** from here means the installer picks an already-present
named person at the reader instead of inventing a number — which is what stops one
worker's hours arriving under another's name.

- **Choose employees…** opens a searchable checkbox list. People already on the
  reader are greyed out with their allocated ID. *Select all* applies only to the
  rows your search is showing, so it can never quietly include somebody scrolled
  out of view.
- **Push all unmapped employees** is the right action when commissioning a new
  reader.
- Device user IDs are **allocated by the platform**, deliberately above the
  highest number either side already knows, so a recycled ID can never attach a
  previous holder's punches to a new employee.
- **The finger itself is still enrolled by hand at the reader.** No vendor exposes
  enrolment without handing over the template, which the platform will not
  request.

Commands queue rather than run instantly, because a reader on a site network is
usually not reachable from outside. Pending and failed counts show on the device.

<a id="terminals-punchlog"></a>

### The punch log

The ten most recent punches, with **Show 10 more** fetching the next ten only
when asked — the log grows with every punch of every terminal, so loading more
than you read would get slower every week. When you reach the end it says so
rather than offering a button that does nothing.

| Outcome | Meaning |
|---|---|
| **Clock in / Clock out** | Worked normally — direction is derived, never trusted from the device |
| **Unknown user** | A punch from a device user mapped to nobody |
| **Rejected** | A finger that did not match anybody. It identifies no one, so it can never become attendance, but it is recorded |
| **Duplicate ignored** | A replay of a punch already recorded |
| **Debounced** | A second tap within 60 seconds |
| **Stale open event** | A punch long after an unclosed clock-in: a new shift is opened and the old one left for you to correct, rather than inventing a plausible clock-out |
| **Device inactive** | The terminal is switched off in the app |

Reading this log is how problems become visible: a run of **Rejected** with no
successes between them means a dirty sensor, a failing reader, or somebody never
enrolled. A run of **Debounced** around your auto clock-out time means the job is
eating real punches.

<a id="terminals-offline"></a>

### Online / offline

The badge goes offline after **5 minutes** without contact — or after three of
that device's own polling intervals, whichever is longer, so a reader deliberately
polled every ten minutes does not flap.

Deleting a terminal removes its mappings and punch history but **keeps the
clockings already created** — those are real worked hours.

---

<a id="plan"></a>

## Plan

A separate area for worker logistics: vehicles, accommodation, and who sleeps
where. It has its own navigation and its own sign-in page at `/plan/login`.
Partner managers and employees cannot open it.

<a id="plan-cars"></a>

### Cars

The company fleet: make, model, year, licence plate, colour, seats, gearbox
(manual or automatic), fuel (petrol, diesel, hybrid, electric) and the date
acquired.

<a id="plan-accommodation"></a>

### Accommodation

Places workers stay: name, address, number of rooms, capacity in people, and an
optional map pin. Each accommodation holds **rooms**, identified by number and
unique within that accommodation, and employees are assigned to a room.

CSV export and import are available for accommodation.

<a id="plan-assign"></a>

### The Plan screen

Pick a site and the screen shows its employees alongside the accommodation
available, with the **distance in km** from that site and each room's occupancy.

- Capacity is shown as *spots* and *occupied*, and a full room is marked **Full**.
- Assign an employee to a room, or clear the assignment.
- A room with nobody in it reads **No residents assigned**.
- Employees with no site appear under **No site**.

**Export assignments** and **Import assignments** move the whole allocation as CSV.

<a id="plan-directories"></a>

### Employees and Sites

Read-only directories, for looking something up without leaving this area.

---

<a id="settings"></a>

## Settings

**Administrators only.** Site managers cannot open this page — it is where site
managers are created.

<a id="settings-company"></a>

### Company details

Name, address, and a **logo**, which appears in the navigation chip, on the kiosk
and in PDF headers. Upload a public image URL or a PNG/JPEG up to 200 KB.

<a id="settings-radius"></a>

### On-site radius

How close to a site's pin a kiosk clock-in must be to count as on site, **in
metres**, default **500**.

Per company because a city-centre office and a motorway earthworks need wildly
different tolerances. The minimum is **25 m** on purpose: consumer GPS is accurate
to roughly 5–20 m and worse between tall buildings, so anything tighter would mark
people off-site while they stand on it. The maximum is 50 000 m.

A saved change takes up to **a minute** to affect clock-ins, which is worth
knowing when testing by hand.

<a id="settings-selfie"></a>

### Clock-in selfie

Switch it on and set a **percentage**, and that proportion of kiosk clock-ins ask
for a photo.

**The decision is made on the server and it sticks.** Cancelling the camera,
denying permission or closing the tab all *postpone* the same photo rather than
escaping it — the next attempt asks again until one is provided. Without that, a
worker could simply press *Clock in* again and re-roll.

An administrator clocking somebody from the dashboard is never asked, which is
also the way round a broken camera.

<a id="settings-kiosk-code"></a>

### Employee kiosk code

The company code employees type at the kiosk, in the form `AB1234`. It is
generated when the company is created and can be regenerated here — after which
**everyone must use the new code**.

<a id="settings-autoclockout"></a>

### Global auto clock-out

A time at which anyone still clocked in anywhere in the company is clocked out,
with an optional different time for weekends. A [site's own
rule](#sites-autoclockout) takes priority.

Each automatic clock-out writes an audit line to the clocking's note naming the
rule and the time it was configured for, so an automatic close is never
indistinguishable from a worker ending their own shift.

<a id="settings-break"></a>

### Break schedule

An unpaid window deducted from any clocking that spans it, keeping worked hours
honest without anyone clocking out for lunch.

<a id="settings-workschedule"></a>

### Work schedule

Your company's standard day. Anything beyond it counts as **overtime** and is
drawn purple in the calendars and timesheets. It is also the fallback for the
pre-filled times when adding a clocking, if no shifts are defined.

<a id="settings-autofill"></a>

### Auto-fill shift on clock-in

When somebody clocks in on a day with **no shift rostered**, writes the shift of
their own role whose start time is nearest the clock-in — before or after.

- **It never changes a day already rostered.** Correcting those is what
  shift-change detection below is for, and two mechanisms writing the same day
  would undo each other.
- **Only the employee's own role's shifts** are candidates. A *Receptioner* who
  clocks at 08:14 gets their 08:30 shift, not the 08:00 one belonging to another
  role.
- **Nothing is written beyond two hours** from the nearest start. With shifts at
  08:00, 09:00, 12:30 and 13:30, a 20:00 clock-in is "nearest" to 13:30 — six and
  a half hours away — and rostering that would be a guess. The day stays blank
  and the company log records why.
- Days on **approved leave** are skipped, since the rota draws leave over the
  shift anyway.
- It fires on a kiosk or terminal clock-in and on an admin clocking somebody in,
  but **not** when an admin enters a historical clocking with explicit times —
  there you are already deciding.

Filled days are marked **⊕ Auto-filled** in the rota table, with the clock-in and
the matched shift in the note, so every one is auditable.

> **This changes the PONTAJ export.** Both sheets are schedule-driven, so a day
> with no assignment is blank in both. Days that auto-fill rosters now carry
> planned hours where they were previously empty. That is usually the point of
> switching it on — but it is a payroll document changing shape, so turn it on
> deliberately rather than mid-month.

<a id="settings-shiftdetect"></a>

### Shift-change detection

A nightly job that moves a day's shift assignment when the actual clocking fits a
**different** shift clearly better.

Deliberately conservative: it looks at finished clockings only, at roles with two
or more shifts, it never touches a day somebody **switched** by hand, and it never
invents an assignment where the rota was blank — blank means *not planned*.

It distinguishes a real shift change from overtime or a late arrival structurally
rather than by a threshold: overtime produces a worked span that *contains* the
assigned shift and a late arrival produces one *inside* it, so in both the
assigned shift is still the best match. Two nearly identical shifts (07–16 against
08–17) are never swapped, which is correct because the distinction does not matter
there.

<a id="settings-lock"></a>

### Clocking locked

Freezes clocking: a red banner appears, bulk clocking is limited to today, and
past-day edits are refused. Use it once a month has gone to payroll.

<a id="settings-editpast"></a>

### Edit past clocking days

How many days back a clocking may be added or corrected. Cells outside the window
are greyed out in the calendars.

<a id="settings-notifications"></a>

### Notifications

- **Site clock-in warnings** and **monthly report emails**, with a daily send cap
  so extra runs cannot spam anybody.
- **New IP sign-in notifications** — an email when an administrator signs in from
  an address not seen before.

<a id="settings-admins"></a>

### Administrator accounts

Create and edit administrators, deactivate them, and reset a password. A
deactivated administrator cannot sign in and cannot use a password reset to get
back in.

<a id="settings-site-managers"></a>

### Site managers

A restricted administrator, scoped to the sites you assign.

- **Sections** — tick which of the ten sections they may open. The default is
  *Clocking* and *Employees*. Settings is never grantable.
- **Partner visibility** — with it off, they see only employees **not** linked to
  a partner. This filters *employees*, not pages, and is separate from whether
  they can open the Partners section.
- Regardless of sections: they **cannot download any timesheet export**, and
  **cannot import the employee CSV**.

<a id="settings-partner-managers"></a>

### Partner managers

Scoped to the partners you assign, with a fixed pair of sections — **Clocking**
and **Employees** — that cannot be changed.

---

<a id="password"></a>

## Your password

**Change password** is in the bottom bar. You need your current password, and the
new one must be at least 8 characters.

Changing it **ends your sessions in other browsers**. That is the point: if the
old password had leaked, a session opened with it dies too.

---

*This guide describes the application as deployed. If a screen does not match
what is written here, the application is right and this page needs updating.*
