# Site Manager Guide

What a site manager can do in epontez, and where the limits are.

> **Anchors are stable** and shared with the other guides: a topic has the same
> `id` here as in `admin_wiki_en.md` and in the Romanian versions. Link to
> `site_manager_wiki_en.md#clock-calendar` and it resolves to the same topic.

**Contents** — [What a site manager is](#role) · [Logging in](#login) ·
[Navigation](#navigation) · [Status](#status) · [Clock](#clock) ·
[Employees](#employees) · [Program](#program) · [Planning](#planning) ·
[Sites](#sites) · [Incidents](#incidents) · [Partners](#partners) ·
[Timesheets](#timesheets) · [Time off](#timeoff) · [Terminals](#terminals) ·
[Plan](#plan) · [Your password](#password)

---

<a id="role"></a>

## What a site manager is

A restricted administrator. Two separate things decide what you see.

**1. Your sites.** An administrator assigns you one or more sites, and your data
is scoped to them — employees whose default site is one of yours, their
clockings, their leave.

**2. Your sections.** The same administrator ticks which of the ten sections you
may open. The default is **Clocking** and **Employees** only, so if a section
named below is missing from your navigation bar, it has not been granted and that
part of this guide does not apply to you.

Three limits apply **whatever** you have been granted:

| Limit | Why |
|---|---|
| **Settings cannot be opened** | It is where site managers are created |
| **No timesheet downloads** — PDF, Excel or payroll CSV | The payroll file contains hourly rates. Enforced on the server, not by hiding a button |
| **No employee CSV import** | It writes company-wide and can change who is active, escaping the site scoping everything else applies. Export still works |

A fourth may apply: if **partner visibility** is switched off for your account,
you see only employees who are **not** linked to a partner.

Two sections carry company-wide power when granted, so they may not be:
**Program** (roles and shifts affect everyone) and **Terminals** (a reader's site
binding decides where punches land).

---

<a id="login"></a>

## Logging in

Go to `/login` with your email and password.

- **Forgotten password** — *Forgot password?* emails a single-use link valid for
  a limited time.
- **Deactivated account** — you get a specific message, and a password reset will
  not help. Ask an administrator to reactivate you.
- Changing your password ends your sessions in other browsers.
- **You stay signed in while you work.** The session lasts an hour and renews on
  every page you open, so continuous work never signs you out; an hour of
  touching nothing does.

A language picker — **English, Romanian, German** — is in the top-right corner.

---

<a id="navigation"></a>

## Navigation

Only your granted sections appear:

| English | Romanian |
|---|---|
| Dashboard | Status |
| Clock | Pontaj |
| Employees | Angajați |
| Schedules | Program |
| Sites | Șantiere / Sedii |
| Partners | Parteneri |
| Timesheets | Fișe pontaj |
| Time off | Concedii |
| Terminals | Terminale |
| Plan | Plan |

Some Romanian companies are set up to say **sediu** instead of **șantier**
throughout, so your screens may differ from a colleague's elsewhere.

Your name, *Change password* and *Sign out* are in the bottom bar.

---

<a id="status"></a>

## Status (Dashboard)

Today at a glance, **for your sites only**.

- **Clocked in today** — distinct employees with a valid clocking today
- **Hours this month** — completed hours so far, after the break schedule
- **Clocked in now** — open clock-ins at this moment
- **Active employees** — headcount in your scope

Click the third-row cards to expand: **Not clocked in last 5 working days**, and
**Time off today**.

Charts cover the last 30 days, one colour per site. **Currently clocked in** lists
open clock-ins with their times and notes.

**Missed clock-outs** warns about anyone whose clock-in is still open from a
previous day — usually a forgotten punch on the way out.

---

<a id="clock"></a>

## Clock (Pontaj)

> At least one active site must exist before anyone can be clocked in.

Employees are grouped into sections by their default site, ordered
**alphabetically** and always in the same place. Names containing numbers sort
naturally, so *Sediu T5* comes before *Sediu T13*.

<a id="clock-visiting"></a>

### Someone who worked at another site

An employee who clocked somewhere other than their default site — typically by
presenting a finger at that site's terminal — appears **twice**: under their own
site, and under the site they worked at, badged **(visiting)**.

- Either row acts on the same person.
- The badge only appears when they *have* a default site to be away from.
- Each row shows only its own section's clockings, so a site never appears to
  have work that happened elsewhere.
- A row for somebody currently clocked in elsewhere reads as not clocked, with a
  muted note, and its button is disabled.

<a id="clock-calendar"></a>

### Calendar view

One column per employee, one row per day.

| Cell | Meaning |
|---|---|
| **HH:mm – HH:mm** | Finished — click to edit |
| **HH:mm –** | Still clocked in — click to clock out or edit |
| Diagonal stripes | Time off |
| Greyed out | Outside the editable window an administrator has set |

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
or out more than 15 minutes late.

On a day with no shift assigned, that last rule is measured against **the widest
window that employee's role ever works**, so somebody on an unrostered late shift
is not flagged merely for being outside the morning one.

Purple means *more* than planned; arriving late or leaving early shows the
**yellow triangle** instead. Hover a cell and the tooltip says which applies.

<a id="clock-select"></a>

### Selecting cells

Click cells to select (they highlight blue), then choose **Clock in**, **Clock
out**, **Final** (both ends of a past day) or **Time off**. Days on approved leave
and people already clocked in are not selectable.

An **invalidated** clocking is not attendance and is ignored by the calendar, the
row status, selection and the summary counts. An *open* event still counts as in
progress, since that is the only way to clock the person out.

<a id="clock-table"></a>

### Table view

A list per site with status, last clock-in, site and note. **Clock in** takes a
site (their default is pre-selected) and an optional note; **Clock out** takes a
note. The pills above each table count **Completed**, **In progress** and **Not
clocked**.

<a id="clock-manual"></a>

### Adding a clocking by hand

**+ Add clocking** records a historical entry — the fix for a missed punch. Set
the clock-in, optionally the clock-out, the site and a note.

<a id="clock-shift-times"></a>

### Filling times from a shift

A row of **shift chips** appears above the time fields — `Tura B · 08:00–16:00` —
listing shifts belonging to the selected employees' roles. Click one and the times
fill in, still editable. An overnight shift's clock-out lands on the next day. If
your company defines no shifts, no chips appear and the fields fall back to the
company work schedule or 08:00–17:00.

<a id="clock-edit"></a>

### Editing a day

Clicking a finished cell opens the edit dialog; pick the clocking if there are
several. You can correct both times. The **existing note is read-only** — write in
**Append note**, and your name and the time are stamped automatically. Notes are
only added to, never overwritten.

<a id="clock-bulk"></a>

### Bulk actions

| Type | What it does |
|---|---|
| Clock in | A clock-in on each selected day |
| Clock out | Closes the open clock-in on each day |
| Final | Both ends on each day |
| Time off | A leave request per day |

**Granting leave without selecting cells** — press *Add time off* with nothing
selected and the start and end dates become editable, so an interval can be
granted directly. Select cells first and the dates are read-only, because there
the grid is the range.

One site, time(s) and note for the batch. Conflicts are reported before anything
is saved.

<a id="clock-lock"></a>

### The red lock banner

If an administrator has locked clocking, a red banner appears: bulk clocking is
limited to today and past-day edits are refused. This usually means the month has
gone to payroll.

---

<a id="employees"></a>

## Employees

Employees whose default site is one of yours, grouped by site.

<a id="employees-filter"></a>

### Filtering

Pills — **Active / Inactive / All** — plus a partner dropdown if partners exist
and you are allowed to see them. Both persist in the URL.

<a id="employees-columns"></a>

### Columns adjust themselves

**A column no employee uses is hidden.** If nobody has an hourly rate, there is no
Hourly rate column. Name, Status, Created and Actions always show. A note under
the tables names what is hidden and how to bring it back. The set does not change
as you switch the Active/Inactive/All pill.

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
birth, default site, partner, hourly rate, annual leave days, and a **kiosk PIN**
(4–6 digits, optional, settable later). A duplicate name in the company is
refused.

> To move an existing employee to another site, use **Transfer** on the list, not
> this form.

<a id="employees-edit"></a>

### Editing an employee

- **System ID** is read-only and is the only identifier an employee has.
- **Name** is editable only within **48 hours** of creation, because exports match
  on it.
- **Active** requires a **Reason**, written to the activity log with your name and
  the date.
- **Auto-clock** creates that day's clocking automatically — needs a site, start
  and end; weekdays only, skipping anyone already clocked or on approved leave.
- **Auto-locate** captures GPS at kiosk clock-in. **With it on, coordinates are
  mandatory** — somebody who blocks location cannot clock in.
- **Kiosk PIN** can be set or cleared.
- **Erase location data** strips GPS from this employee's clockings for a GDPR
  request, keeping the clockings.

<a id="employees-passkey"></a>

### Fingerprint sign-in on the employee's own phone

Switching **Fingerprint** on lets an employee sign in at the kiosk with their own
phone's sensor. Registration needs **two factors**: their PIN *and* a single-use
code you issue here, shown **once**. The employee then opens `/kiosk`, chooses
*Set up fingerprint on this device*, and enters both.

- **Once a device is registered their PIN stops working for clocking**, though it
  still works for viewing hours and requesting leave. A PIN can be shared; a
  fingerprint cannot.
- **Switching Fingerprint off deletes every registered device** — a revocation,
  not a pause.
- **Revoking one device restores their PIN at once** — the way back in for a lost
  phone, along with you clocking them from the dashboard.
- It is designed for **personal phones**. On a shared tablet any enrolled finger
  unlocks any passkey on it, so it would not stop one worker clocking in another.

<a id="employees-csv"></a>

### CSV export

**Export** gives Active, Inactive or All with fixed English machine headers.

> **Import is not available to site managers.** It writes company-wide and can
> change who is active, which would escape your site scoping.

<a id="employees-pdf"></a>

### PDF

**↓ PDF** downloads your active employees grouped by site.

---

<a id="program"></a>

## Program (Schedules)

Only if granted — this section affects the whole company, not just your sites.

<a id="program-roles"></a>

### Roles (funcții)

The company's job titles, each showing its shifts and how many employees hold it.
Add, rename (a rename onto an existing name offers to **merge**), or deactivate.
A delete is refused while anybody holds the role. An amber card lists active
employees with **no role**, which is worth clearing because a role is what
connects somebody to shifts.

<a id="program-shifts"></a>

### The shift library

Shifts belong to the **company**, and a role may run several while a shift may
serve several roles. Create the shift once, then attach it to roles from either
side.

- An end at or before the start means the shift **crosses midnight**; allowed, and
  badged *overnight*.
- Two shifts may share a name — pickers show `name · 07:00–16:00`. Only the same
  name **and** the same hours is refused.
- Shifts are **informational**: no hours, overtime or cost arithmetic reads one.
  They drive the rota, the adherence marks and the PONTAJ sheets.
- Nobody has a permanent shift; it is a **per-day** fact set in
  [Planning](#planning).
- Deleting a shift deletes its dated assignments, so those days go blank.

<a id="program-export"></a>

### The PONTAJ export

The month picker, the green **Excel** button and two filters are in the header:
**Role** (*All roles* by default) and **Partner** (*No partner* by **default**,
or *All partners*, or one).

> The partner default **excludes collaborators**, because a PONTAJ sheet is a
> payroll document for your own staff. Check which you have selected before
> sending the file on.

Two sheets in identical layouts: **Program**, the plan for the month; and
**Pontaj**, the same plan truncated at today and annotated with attendance — a
scheduled day nobody worked books **0 hours** and is drawn dark red with an
*Absent* note. Both report **planned** times; a day with nothing rostered is blank
in both even if somebody clocked. Headings are always Romanian, because the file's
shape is a contract with whoever receives it. Approved leave writes its code into
*Inceput* and books 0 hours. Capped at 450 employees.

---

<a id="planning"></a>

## Planning (the rota)

> **You can now edit this.** Granting the Program section used to leave Planning
> readable and useless to you — every change was refused. You may now assign,
> clear, swap and bulk-allocate shifts for **employees whose default site is one
> of yours, plus anyone with no default site at all**. That second part matters:
> without it an unassigned employee could be planned by nobody but a full admin,
> and those are exactly the people most likely to need covering.
>
> An employee at another site is refused by name. A **swap needs both sides** in
> your scope, since it rewrites two people's days and holding one of them is not
> authority over the other.
>
> Your name is recorded on everything you change, in the assignment and in the
> company log.
>
> The shift **library** stays admin-only. A shift belongs to the company, so
> creating or deleting one changes every site and cannot be scoped to yours — you
> assign shifts, you do not define them.

Reached from **Planning** on a role in Program. Granted with Program.

<a id="planning-grid"></a>

### The grid

Employees down the side, days across the top — the shape that answers *is every
night covered?*. Each shift has a stable colour, weekends are pink, holidays
amber, and a purple **✓** marks a day worked with **nothing rostered**. An **All
roles** option shows everyone, with each shift listed once in the legend.

<a id="planning-automation"></a>

### Two pills at the top

Above the grid, two pills say whether the automatic mechanisms are on — green for
on, grey for off. Both write to the rota with nobody pressing anything, so if a
grid changed overnight these say which could have done it.

| Pill | What it does |
|---|---|
| **⊕ Auto-fill shift on clock-in** | Rosters a **blank** day when somebody clocks in on it |
| **◎ Shift-change detection** | Moves a day **already rostered** when the clocking fits another shift better |

Both are switched on per company by an administrator, in Settings — which you
cannot open, so the pills are how you find out.

<a id="planning-cells"></a>

### Reading a cell

Each cell carries its shift's colour and stacks the short name over the start and
end times. Hovering gives the whole day: the shift and its hours, the date, what
was actually clocked (or **No clocking**), and the adherence verdict. The corner
glyph is that verdict — green ✓ on time, amber ✓ late or early, red ✗ absent.

<a id="planning-select"></a>

### Selecting several cells at once

**Empty cells can be clicked to build a selection**, then **Allocate shift (n)**
applies one shift to all of them.

- Only empty cells join a selection; a cell with a shift or leave opens the dialog
  as before.
- **One function at a time** — a shift belongs to a function, so clicking into
  another one starts a fresh selection.
- Nothing selected? Everything behaves as it always did.
- The same site scoping applies: a selection may only contain employees you may
  plan.

<a id="planning-assign"></a>

### Assigning a shift

Click a cell, or use From/To for a range.

- **A range is split into runs of working days** — 2–13 February becomes two
  assignments, leaving weekends and holidays blank unless you tick *include
  non-working days*.
- **A single day is always honoured as-is**, which is how you put somebody on a
  Saturday.
- An **open-ended** assignment covers every day, weekends included, since there is
  no last day to stop at.
- **Overlaps are reshaped, not refused**: nights from the 10th end an open-ended
  morning assignment on the 9th.
- You get a **preview** and a confirmation whenever anything would change.

<a id="planning-switch"></a>

### Swapping two people for one day

On a single day, **Switch shift** lists colleagues on a different shift that day.
A swap carves out a **single day** each, leaves the rest of both rotas untouched,
and marks both **Switched** with a note naming who did it and with whom. The two
must hold the same role and be on different shifts that day. A switched day is
never overwritten by automatic shift detection.

<a id="planning-clear"></a>

### Clearing a day

**Clear this day** carves one day out of the surrounding assignment, splitting it
if the day is in the middle. It does not restore anything reshaped earlier.

<a id="planning-timeoff"></a>

### Allocating leave from the rota

**Allocate time off** covers a range across several employees; inside the cell
dialog a **Shift / Time off** toggle covers the day you clicked. A day already on
approved leave offers **Remove time off**, which **cancels** rather than deletes —
the audit trail survives and the shift underneath returns by itself. You may
assign a shift to a day already on leave; the rota underneath is still being
edited.

<a id="planning-table"></a>

### The table under the grid

One row per **scheduled day** — `Employee | Shift | Day | In | Out | Status |
Note`, where In and Out are that day's first clock-in and last clock-out.

**Each employee is collapsed**; click their row to open their days. The header
keeps the tally — ✓ on time, ✓ late, ✗ absent, ✓ unplanned — and the count of
hidden days, so somebody with a red ✗ is still one visible line.

The **Status** column says how a day came to be rostered: blank for a person,
**⇄ Switched** for a one-day swap, **⊕ Auto-filled** when a clock-in rostered it,
**◎ Detected** when detection moved it.

**The table stops at today** while the grid shows the whole month: every column
except Shift reports what happened, and a future day has none of it. A past month
is complete; a future month shows an empty table and a full grid. Clicking a
future cell in the grid still opens the assign dialog.

| Tint | Meaning |
|---|---|
| **Red** | The plan was broken — in late, out early, or no clocking on a day whose shift was already due |
| **Purple** | There was no plan — **Unplanned**, offering *Assign shift* |

"Already due" means the day is past, or it is today and the start time has passed.
Approved leave is not absence and outranks both.

---

<a id="sites"></a>

## Sites (Șantiere / Sedii)

Your assigned sites.

<a id="sites-coords"></a>

### Coordinates

A site's map pin is what makes the on-site check possible. Without it a clock-in
can never be judged, however tight the radius, so those rows are badged amber **No
coordinates**. Being off-site is **recorded, not blocked** — evidence for whoever
reviews the timesheet, not a gate on clocking in.

<a id="sites-autoclockout"></a>

### Per-site auto clock-out

A time at which anyone still clocked in at that site is clocked out. It takes
priority over the company-wide rule.

<a id="sites-status"></a>

### Active, inactive, hidden

Pills filter **Active / Inactive / All**. A site must be inactive before it can be
hidden, and **only a super admin can unhide** one. Every change appends an audit
line to the site's notes.

---

<a id="incidents"></a>

## Incidents

A per-site register for Legea 319/2006, available to every role that can see
Sites.

<a id="incidents-add"></a>

### Logging an incident

| Field | Options |
|---|---|
| **Type** | Accident · Near miss · Dangerous occurrence · Occupational disease |
| **Severity** | Minor · Moderate · Serious · Fatal |
| **Date of incident** / **Date logged** | When it happened / was recorded |
| **Description** | Required |
| **Employees involved** | From the employees assigned to that site |
| Witnesses, Corrective actions | Optional |
| **Reported to authorities** | Yes/no |

<a id="incidents-pdf"></a>

### The register PDF

**Incidents PDF** takes a month and produces a landscape A4 register for that site
and month, telling you if there is nothing to report rather than producing an
empty file.

---

<a id="partners"></a>

## Partners

Only if granted. Collaborator companies, with each one's sites as sub-rows.

Linking an employee to a partner has two consequences: **they cannot request time
off** (that is their own employer's business, refused in both the dashboard and
the kiosk), and **their leave balance fields are disabled**.

Note that the **partner filter** on the employees and clock pages filters
*employees*, not pages — separate from whether you can open this section. If
partner visibility is off for your account, you see only employees with no
partner.

---

<a id="timesheets"></a>

## Timesheets (Fișe pontaj)

Only if granted. Hours a month at a time, for your sites.

<a id="timesheets-filters"></a>

### Choosing what you see

Month picker plus filters for **site**, **employee** and **partner**.

<a id="timesheets-read"></a>

### Reading the table

Each employee is a block of their clockings with daily subtotals and a monthly
total.

| Marker | Meaning |
|---|---|
| **Auto** pill | Created by the auto-clock job |
| **Purple row** | Overtime, weekend, holiday, or outside the assigned shift — the [same rules](#clock-colours) as the calendar |
| Struck through | Marked invalid; not counted |
| Partner badge | Linked to a collaborator |

<a id="timesheets-gps"></a>

### Location pins

A shift carries **two** positions, so a row can show **In** and **Out** pins, each
linking to OpenStreetMap at that point.

| Pin | Meaning |
|---|---|
| **Green** | On site |
| **Red** | Off site |
| **Grey** | A position exists but the site had no coordinates to judge it against |
| No pin | No position captured |

**The verdict is frozen at the moment of clocking** — changing the radius later
affects new clockings only. Coordinates are erased after 180 days, or on demand
from the employee's page.

<a id="timesheets-edit"></a>

### Correcting a clocking

Click a row to fix its times or mark it invalid. Notes are append-only with an
audit stamp. Re-validating an invalid entry re-runs the overlap check.

<a id="timesheets-download"></a>

### Downloads

> **Not available to site managers.** The PDF, Excel and payroll CSV are all
> refused for this role, because the payroll file contains hourly rates. This is
> enforced on the server, so a direct link will not work either. Ask an
> administrator for the file.

---

<a id="timeoff"></a>

## Time off (Concedii)

Only if granted. A pending request puts an asterisk on the nav tab.

<a id="timeoff-types"></a>

### Types

`CO` annual leave · `CFP` unpaid · `MEDICAL` sick · `MARRIAGE` · `BLOOD_DONATION`
· `SPECIAL_EVENTS` · `MILITARY` · `FUNERAL` · `CHILD_BIRTH` · **`MATERNITY`** ·
`EXCUSED` · `ABSENT`.

**Maternity** is separate from *Child birth*: the latter is the few days around a
birth, maternity the long statutory period, and a pontaj reports them
separately.

<a id="timeoff-read"></a>

### Reading the table

Leave is stored **one row per working day**, so there are separate **Date**,
**Day** and **Days** columns and the summary pills count working days. A request
spanning a weekend does not inflate the count.

<a id="timeoff-actions"></a>

### Actions

**Approve**, **Reject** or **Cancel**; `requestedBy` records who submitted it.

**Only approved leave displaces a scheduled shift.** A pending request keeps the
shift visible in the rota, marked with a small dot. The override happens when the
rota and sheets are read, never written back, so cancelling leave brings the shift
back by itself. A per-request **PDF** is available for signing.

---

<a id="terminals"></a>

## Terminals (Terminale)

Only if granted — this section carries company-wide power, since a reader's site
binding decides where its punches land.

<a id="terminals-why"></a>

### Why a terminal rather than a tablet

A terminal does **1:N identification**: a worker presents a finger and the device
answers *who it is*, with nobody selected first. That is the only arrangement that
actually prevents one worker clocking in another. It also makes the **site
certain**, because the reader is bolted to it, and **no fingerprint ever leaves
the device** — only a number mapping a device slot to an employee is stored.

<a id="terminals-mappings"></a>

### Mapping employees to the device

The table lists each device user ID, the employee it maps to, and whether the
terminal holds an **RFID card** for them (the number is in the tooltip). Rows are
flagged when the two sides disagree: *mapped here but absent on the terminal*,
*mapped here to «name» — wrong mapping*, or *not mapped* (usually an installer's
own account).

<a id="terminals-fixname"></a>

### Fixing a mistyped name

Correct an employee's name after they were pushed and the reader keeps the old
spelling. Use **Fix name on device** on the flagged row.

> Do **not** push the employee again to fix it. A re-push is refused as a taken ID
> and the mapping is deleted, after which their punches stop resolving. *Fix name
> on device* changes only the name and leaves enrolled fingerprints alone.

<a id="terminals-push"></a>

### Sending employees to a terminal

**Choose employees…** opens a searchable checkbox list; people already on the
reader are greyed out with their allocated ID, and *Select all* applies only to
the rows your search is showing. **Push all unmapped employees** is for
commissioning a new reader. IDs are allocated by the platform, above the highest
number either side knows, so a recycled ID can never attach a previous holder's
punches to a new employee.

**The finger itself is still enrolled by hand at the reader** — only the identity
is pushed. Commands queue rather than run instantly, because a reader on a site
network usually cannot be reached from outside.

<a id="terminals-punchlog"></a>

### The punch log

The ten most recent punches, with **Show 10 more** fetching the next ten only
when asked.

| Outcome | Meaning |
|---|---|
| **Clock in / Clock out** | Normal. Direction is derived, never trusted from the device |
| **Unknown user** | From a device user mapped to nobody |
| **Rejected** | A finger that matched nobody — it identifies no one, so it can never become attendance, but it is recorded |
| **Duplicate ignored** | A replay of a punch already recorded |
| **Debounced** | A second tap within 60 seconds |
| **Stale open event** | A punch long after an unclosed clock-in: a new shift opens and the old one is left for correction |
| **Device inactive** | Switched off in the app |

A run of **Rejected** with no successes between them means a dirty sensor, a
failing reader, or somebody never enrolled.

<a id="terminals-offline"></a>

### Online / offline

The badge goes offline after **5 minutes** without contact, or three of that
device's polling intervals, whichever is longer.

---

<a id="plan"></a>

## Plan

Only if granted. Worker logistics — vehicles, accommodation and who sleeps where —
with its own navigation and its own sign-in at `/plan/login`.

<a id="plan-cars"></a>

### Cars

The fleet: make, model, year, licence plate, colour, seats, gearbox, fuel and the
date acquired.

<a id="plan-accommodation"></a>

### Accommodation

Name, address, rooms, capacity in people, and an optional map pin. Each
accommodation holds **rooms** numbered uniquely within it, and employees are
assigned to a room. CSV export and import are available.

<a id="plan-assign"></a>

### The Plan screen

Pick a site and see its employees alongside the available accommodation, with the
**distance in km** and each room's occupancy. Capacity shows as *spots* and
*occupied*, a full room is marked **Full**, an empty one reads **No residents
assigned**, and employees with no site appear under **No site**. **Export
assignments** and **Import assignments** move the whole allocation as CSV.

<a id="plan-directories"></a>

### Employees and Sites

Read-only directories for looking something up without leaving this area.

---

<a id="password"></a>

## Your password

**Change password** is in the bottom bar. You need your current password and at
least 8 characters. Changing it **ends your sessions in other browsers**, which is
the point.

---

*This guide describes the application as deployed. If a screen does not match
what is written here, the application is right and this page needs updating.*
