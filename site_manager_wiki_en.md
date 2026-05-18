# Site Manager Guide

This guide covers all sections of the admin dashboard available to site managers.

---

## What is a Site Manager?

A site manager is a restricted admin account created by your company administrator. Unlike a full admin, you can only see and manage the employees and data belonging to the sites you have been assigned. The pages you can access are configured by your admin — you may see some or all of: **Status (Dashboard), Clock, Employees, Sites, Timesheets, Time off, Plan**.

---

## Logging In

Navigate to `/login` and enter your email and password. If your account has been deactivated, contact your company administrator.

To recover a forgotten password, use the **Forgot password?** link. You will receive a reset email valid for a limited time.

---

## Navigation

The top navigation bar shows only the sections your admin has enabled for your account. The active section is highlighted. A language picker (EN/RO) is available in the top-right corner. Your name and a sign-out option appear in the bottom bar.

---

## Status (Dashboard)

> Only visible if your admin has granted you access to the **Status** section.

Shows an at-a-glance overview of the employees at your assigned sites.

**What you see:**
- A list of your assigned sites with a clickable map link (if coordinates are set) and the count of employees currently clocked in at each site.
- **Clocked in today** — distinct employees with any clock event today at your sites.
- **Hours this month** — total completed hours for the current month across your sites.
- **Clocked in now** — employees with an open clock-in right now.
- **Active employees** — count of active employees whose default site is one of your assigned sites.
- **Not clocked in last 5 working days** — employees in your sites who have had no clock event in the last 5 working days.
- **Time off today** — employees in your sites with an approved or pending time-off request today.
- **30-day charts** — daily people and hours trends, broken down by site.
- **Currently clocked in table** — employees actively clocked in right now, showing clock-in time and note.

If you have no sites assigned yet, the page shows a notice until your admin assigns sites to your account.

---

## Clock

Record and manage clock-in and clock-out events for the employees at your assigned sites.

### Views

Toggle between **Calendar** and **Table** views using the button in the top-right area.

### Calendar view

A grid with one column per employee (from your assigned sites) and one row per day. Each cell shows the employee's clock events for that day:

- A completed event shows **HH:mm – HH:mm** — click to edit it.
- An ongoing event shows **HH:mm –** — click to clock out or edit.
- A time-off day shows a striped diagonal pattern — click to cancel the request (with an optional note).
- Cells outside the editable window are greyed out.

**Selecting cells for bulk actions** — click individual cells to select them, then choose an action from the toolbar: **Clock In**, **Clock Out**, **Final** (sets both in and out for a past day), or **Time Off**.

### Table view

A list showing each employee's current status, last clock-in time, site, and note.

- **Clock in** — select site, optional note, confirm.
- **Clock out** — optional note, confirm.

### Adding a manual clock event

Use the **+ Add clock** button to record a historical entry. Set employee, clock-in time, optional clock-out time, site, and note. This is useful for correcting missed punches.

### Edit day modal (calendar view)

Clicking a completed-event cell opens an edit dialog. The **Existing note** is shown read-only; use the **Append note** field to add text — an audit stamp (your name + timestamp) is appended automatically on save.

---

## Employees

View and manage employees whose default site is one of your assigned sites.

> CSV import is not available for site managers.

### Filtering

Use the filter pills — **Active / Inactive / All** — to narrow the list. If your admin has enabled partner visibility for your account, a partner dropdown filter also appears.

### Adding an employee

Click **Add employee** and fill in name, position, optional email/phone/PIN, and default site (pre-filled to your first assigned site).

### Editing an employee

Click **Edit** to open the employee's edit page. You can update name, position, email, phone, date of birth, default site, PIN, auto-clock settings, and auto-locate. If your admin has enabled **View/Manage Partners** for your account, you can also view and update the employee's partner assignment.

**Status changes** (Active / Inactive) require a reason, which is appended to the employee's audit notes.

**Danger zone** (inactive employees only) — a **Hide employee** button makes the employee invisible; only a super admin can unhide.

### PDF download

**↓ PDF** downloads a landscape A4 employee list for your sites.

---

## Sites

> Only visible if your admin has granted you access to the **Sites** section.

Shows the sites you have been assigned. You can view site details, edit address and location, and manage the auto clock-out configuration.

Every change is recorded in the site's audit history (what changed, when, and by whom).

---

## Timesheets

> Only visible if your admin has granted you access to the **Timesheets** section.

Monthly clock data for employees at your assigned sites.

### Navigating months

Use the month selector to switch between months.

### Filters

- **Site** — narrow to a specific assigned site
- **Employee** — show a single employee
- **Partner** — filter by partner (if partner visibility is enabled for your account)

### Reading the table

Each employee has a section with daily rows. Columns: Date, Day, In, Out, Hours, Site, Clocked in by, Clocked out by, Note.

Special indicators:
- **Auto** pill — the event was created by the auto-clock cron
- **📍 pin** — GPS coordinates were captured at clock-in
- **Void** badge — the event is marked invalid and excluded from totals

### Editing a clock event

Click the pencil icon on any row to open the edit dialog. You can correct clock-in / clock-out times, toggle the **Valid** flag, and append a note. An audit stamp is appended automatically on save.

### Calendar view

Switch to the calendar view for a visual month grid. Clicking a completed-event cell opens an edit dialog with the same append-note capability. Clicking a time-off cell opens a cancel dialog.

> **Note:** Downloading the PDF timesheet is not available for site managers.

---

## Time Off

> Only visible if your admin has granted you access to the **Time off** section.

Review, approve, and manage time-off requests for employees at your assigned sites.

### Leave types

| Code | Description |
|------|-------------|
| CO | Paid annual leave |
| CFP | Unpaid leave |
| Medical | Sick leave / medical certificate |
| Marriage | Marriage event |
| Blood donation | Blood donation day |
| Special events | Other special events |
| Military | Military service |
| Funeral | Bereavement |
| Child birth | Parental leave |

### Navigating and filtering

Use the **month selector** to navigate. Months with pending requests are highlighted so you can jump to them quickly. A **type** dropdown filters by leave category.

### Actions

- **Approve** — accepts the request; approved days are skipped by the auto-clock cron
- **Reject** — declines the request
- **Cancel** — cancels an approved or pending request

All three actions accept an optional note.

---

## Plan

> Only visible if your admin has granted you access to the **Plan** section.

The Plan section provides resource planning views. See the Plan section of the admin wiki for full details.

---

## Changing your password

Click your name in the bottom bar, then **Change password**. You must enter your current password to set a new one (minimum 8 characters).
