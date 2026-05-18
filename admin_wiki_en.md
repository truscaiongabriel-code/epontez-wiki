# Admin Guide

This guide covers all sections of the admin dashboard available to company administrators.

---

## Logging In

Navigate to `/login` and enter your email and password. If your account has been deactivated by a super admin, you will see a specific message — password reset will not work while inactive, contact your super admin.

To recover a forgotten password, use the **Forgot password?** link on the login page. You will receive an email with a reset link valid for a limited time.

---

## Navigation

The top navigation bar links to all sections: **Dashboard, Clock, Employees, Sites, Partners, Timesheets, Time off, Settings**. The active section is highlighted. A language picker (EN/RO) sits in the top-right corner. Your name and a sign-out option appear in the bottom bar.

---

## Dashboard

An at-a-glance overview of your workforce for today.

**Stats — row 1**
- **Clocked in today** — distinct employees with any valid clock event today (ongoing or completed)
- **Hours this month** — total completed hours for the current month (respects the break schedule if configured)

**Stats — row 2**
- **Clocked in now** (accent) — employees with an open clock-in right now
- **Active employees** — total active employee count

**Expandable stats — row 3** (click any stat to expand a detail table)
- **Not clocked in last 5 working days** — employees who have had no clock event in the last 5 working days; table shows name, position, and default site
- **Time off today** — employees with an approved or pending time-off request covering today; table shows name, type, and status

**Charts** (last 30 days, broken down by site with a distinct colour per site)
- *People per day* — distinct employees with a clock event each day
- *Hours per day* — total completed hours each day

**Currently clocked in** — table of employees with an open clock-in today; columns: Employee (with partner badge if assigned), Clock-in time, Note.

**Missed clock-outs** — if any employees have an open clock-in from a previous day, a warning banner appears at the top listing them so you can correct the records.

---

## Clock

Records clock-in and clock-out events for your employees.

> **Requirement:** at least one active site must exist before you can clock anyone in.

### Views

Toggle between **Calendar** and **Table** views using the button in the top-right area.

### Calendar view

A grid with one column per employee and one row per day of the selected month. Each cell shows the employee's clock events for that day:

- A completed event shows **HH:mm – HH:mm** — click to edit it.
- An ongoing event shows **HH:mm –** — click to clock out or edit.
- A time-off day shows a striped diagonal pattern — click to cancel the request (with an optional note).
- Cells outside the editable window (controlled by the *Edit past clocking days* setting) are greyed out.

Partner badges appear on employee column headers if the employee is assigned to a partner.

**Selecting cells for bulk actions** — click individual cells to select them (highlighted in blue), then choose an action from the toolbar: **Clock In**, **Clock Out**, **Final** (sets both in and out for a past day), or **Time Off**.

### Table view

A traditional list showing each employee's current status, last clock-in time, site, and note. Actions:

- **Clock in** — select site (defaults to employee's default site), optional note, confirm.
- **Clock out** — optional note, confirm.

### Adding a manual clock event

Use the **+ Add clock** button to record a historical entry for any employee and date — useful for missed punches. Set clock-in time, optional clock-out time, site, and note.

### Edit day modal (calendar view)

Clicking a completed-event cell opens an edit dialog. If the employee has multiple events on that day, pick the one to edit. You can correct the clock-in and clock-out times. The **Existing note** is shown read-only; write in the **Append note** field to add text — an audit stamp (your name + timestamp) is appended automatically on save.

### Bulk modal

After selecting multiple calendar cells, choose the action type:

| Type | What it does |
|------|-------------|
| Clock In | Records a clock-in for each selected day |
| Clock Out | Closes the open clock-in on each selected day |
| Final | Records both clock-in and clock-out for each selected day |
| Time Off | Creates a time-off request for each selected day |

You can set a shared site, time(s), and note. Conflicts (e.g. an employee already has approved PTO on a selected day) are reported before saving.

### Lock banner

If **Clocking locked** is enabled in Settings, a red banner is displayed at the top of the page. While locked, bulk clocking is restricted to today only and past-day edits are blocked.

---

## Employees

Manage your workforce. Employees are grouped by their **default site**; those without a default site appear in a "No site assigned" group at the top.

### Filtering

Use the filter pills — **Active / Inactive / All** — to narrow the list. If partners exist, a partner dropdown filter also appears. The URL parameters persist the filter on reload.

### Adding an employee

Click **Add employee** and fill in:

- **Name** (required)
- **Position** (required)
- Email, phone (optional)
- **Default site** — pre-selects this site in the kiosk clock-in dropdown and groups the employee under that site in this list
- **PIN** — a numeric code the employee uses to log in at the kiosk; leave blank if the employee doesn't need kiosk access (can be set later)
- **Employee ID** is generated automatically but can be set manually; it is unique within your company and cannot be changed after creation

### Editing an employee

Click **Edit** to open the employee's edit page. All creation fields are editable, plus:

- **Date of birth** — optional; stored for reference
- **Status** — toggling Active / Inactive requires a reason, which is appended to the employee's audit notes
- **Partner** — assign the employee to a business partner; shows as a purple badge throughout the platform
- **Auto-clock** — enable to have the system automatically record clock-in and clock-out every working day:
  - Select the site, start time (HH:mm), and end time (HH:mm)
  - Start must be before end
  - While enabled, the employee cannot manually clock in from the kiosk
  - Approved time-off days and weekends are skipped automatically
- **Auto-locate** — when enabled, the kiosk requests the employee's GPS location at clock-in; the server stores the coordinates and records whether the employee was within range of the site
- **Clear PIN** — removes the PIN so the employee can no longer use the kiosk
- **Danger zone** (inactive employees only) — **Hide employee** makes the employee invisible to all admins and the kiosk; only a super admin can unhide

### Partner badge

A purple pill with the partner name appears next to the employee's name throughout the platform (employees list, timesheets, clock page, dashboard).

### CSV Import / Export

**Export CSV** — downloads a spreadsheet of all employees matching the current status filter. Columns: `employeeId, name, position, email, phone, dateOfBirth, active, autoClockEnabled, autoClockStart, autoClockEnd, autoClockSiteName, autoLocateEnabled, defaultSiteName`.

**Import CSV** — after selecting a file, a **preview** is shown before any changes are made:
- **To add** — rows that don't match any existing employee
- **With changes** — existing employees where at least one field differs
- **No changes** — existing employees with identical data (skipped on import)

Errors (unknown site name, invalid value, missing required auto-clock fields, duplicate Employee ID, etc.) must be resolved before the import can be confirmed. Active status changes are automatically appended to each employee's audit notes.

Matching logic: `employeeId` is the primary key, falling back to name (case-insensitive), then email. New rows require `employeeId` to be set.

### PDF download

**↓ PDF** downloads a landscape A4 employee list grouped by site, including name, position, email, phone, and PIN status.

---

## Sites

Manage your company's construction sites. Active sites appear in the clock-in dropdown.

### Adding a site

Fill in the **site name** (required) and optionally:

- **Address**
- **Map location** — click **Set location on map** to open an interactive map; drag the pin or search by address; saved coordinates are used for the auto-locate on-site check and appear as a clickable map link throughout the admin
- **Partner** — link this site to a business partner
- **Auto clock-out** — check the box and set a time (HH:mm) to automatically clock out any employee still clocked in at this specific site at that time

### Editing a site

All creation fields are editable. Every save appends a line to the site's **audit history** showing what changed, when, and by whom. View history by expanding the history section on the edit form.

### Activating / Deactivating

An inactive site no longer appears in the clock-in dropdown or the kiosk. Deactivating does not delete any clock history.

### Hiding a site

Inactive sites can be hidden using the **Hide** button in the actions column. Hidden sites are invisible to all admins and the kiosk — only a super admin can unhide them.

### Filter pills

Use **Active / Inactive / All** to switch the view.

---

## Partners

Manage the business partners (subcontractors, clients) associated with your company.

### Adding a partner

Fill in the **partner name** (required) and optionally address, email, phone, and CUI (Romanian fiscal ID).

### Editing a partner

Click **Edit** to update any field. You can also **Deactivate** or **Activate** a partner from the actions column.

### Partner–site association

Sites are linked to partners from the **Sites** page (in the site's edit form). Each partner row in this table shows a sub-list of all sites currently assigned to it.

### Filter pills

**Active / Inactive / All** filters apply here too.

---

## Timesheets

Monthly payroll data per employee.

### Navigating months

Use the month selector (arrows or dropdown) to switch between months.

### Filters

- **Site** — show only employees clocked in at a specific site
- **Employee** — show a single employee
- **Partner** — show only employees belonging to a specific partner (or "No partner" for unassigned)

The default (no filter) shows a compact summary. Use the **Expand all** button or select a filter to load the full table.

### Reading the table

Each employee has a section with daily rows. Columns: Date, Day, In, Out, Hours, Site, Clocked in by, Clocked out by, Note.

Special indicators:
- **Auto** pill — the event was created by the auto-clock cron
- **📍 pin** — GPS coordinates were captured at clock-in (hover for on-site / off-site badge)
- **Void** badge — the event is marked invalid and excluded from totals

Day totals, overall total hours, and billable hours (respecting the break schedule) are shown per employee.

### Editing a clock event

Click the pencil icon on any row to open the edit dialog. You can correct the clock-in or clock-out time, toggle the **Valid** flag, and append a note. An audit stamp (your name + timestamp) is appended automatically on save.

### Calendar view (timesheets)

Switch to the calendar view for a visual month grid. Clicking a completed-event cell opens an edit dialog with the same append-note capability. Clicking a time-off cell opens a cancel dialog with an optional note.

### Downloading the PDF

Click **↓ PDF** to download a formatted A4 timesheet for the selected month and filters.

---

## Time Off

Review, approve, and manage employee time-off requests.

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

Use the **month selector** to navigate. A **type** dropdown filters by leave category. Months with pending requests are highlighted above the selector so you can jump to them quickly.

### Reading the table

Requests are listed per working day (one row per day). Summary pills at the top count working days by status. Each row shows: date, day of week, type, status badge, submitted by, and note.

### Actions

- **Approve** — accepts the request; approved days are skipped by the auto-clock cron
- **Reject** — declines the request
- **Cancel** — cancels an approved or pending request

All three actions accept an optional note that is saved to the request.

---

## Settings

Company configuration. Accessible only to admins.

### Company details

Update your company's **name, email, phone, address, CUI**, and **manager** name. These appear in PDF headers.

**Logo** — upload a PNG or JPEG up to 200 KB. The logo appears in the top-left navigation chip and in all PDF headers.

### Employee kiosk

The **kiosk access code** is the code employees enter at `/kiosk` to identify their company. You can update it here.

### Global auto clock-out

Automatically clocks out all employees still clocked in at a set time.

- Toggle **Enable** on or off.
- Set a **clock-out time** (HH:mm, Europe/Bucharest). All employees with an open clock-in at that exact minute are clocked out automatically.

> **Tip:** per-site auto clock-out times can be set on the **Sites** page to target only employees clocked in at a specific site.

### Break schedule

Enable and configure a daily break window (start time and end time). When enabled, hours that fall within the break window are excluded from billable totals in timesheets and the dashboard.

### Work schedule

Enable and configure the standard working hours (start and end time). Used to calculate overtime — hours outside this window count as overtime in timesheet totals.

### Clocking lock

When **Clocking locked** is enabled, all past-day edits are blocked and bulk clocking is restricted to today only. A red banner is shown on the Clock page while locked.

### Edit past clocking days

Controls how many days back a clock event can be edited (default: 5). Events older than this limit cannot be modified by non-super-admin users.

### Admin users

Lists all admin accounts for your company. You can:

- **Add** a new admin (name, email, password — minimum 8 characters)
- **Edit** name and email
- **Reset password**
- **Deactivate / Activate** existing admins

Deactivated admins cannot log in and password reset does not work for them. Super admin accounts are marked with a **Super** badge and cannot be deactivated from this page.

### Site managers

Lists all site manager accounts. Site managers have restricted access — they can only see employees whose default site matches their assigned sites.

- **Add** a site manager (name, email, password)
- **App access** — choose which sections the manager can see: Status, Clocking, Employees, Sites, Timesheets, Time off, Plan. Clocking and Employees are always on by default.
- **View/Manage Partners** — checkbox on the manager's profile; when enabled the manager can see the Partners column and partner badges on employees
- **Assign sites** — select which sites this manager is responsible for
- **Edit**, **reset password**, **deactivate / activate**

### Partner managers

Lists all partner manager accounts. Partner managers can only access the Clock and Employees pages, and only see employees who belong to their assigned partners.

- **Add** a partner manager (name, email, password)
- **Assign partners** — select which partners this manager is responsible for
- **Edit**, **reset password**, **deactivate / activate**

---

## Changing your password

Click your name in the bottom bar, then **Change password**. You must enter your current password to set a new one (minimum 8 characters).
