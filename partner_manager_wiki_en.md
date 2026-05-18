# Partner Manager Guide

This guide covers the admin dashboard sections available to partner managers.

---

## What is a Partner Manager?

A partner manager is a restricted admin account created by your company administrator. You can only see and manage the employees who belong to the business partners you have been assigned. Your access is limited to two pages: **Clock** and **Employees**.

---

## Logging In

Navigate to `/login` and enter your email and password. If your account has been deactivated, contact your company administrator.

To recover a forgotten password, use the **Forgot password?** link. You will receive a reset email valid for a limited time.

---

## Navigation

The top navigation bar shows two links: **Clock** and **Employees**. All other sections are not accessible to partner managers. A language picker (EN/RO) is available in the top-right corner. Your name and a sign-out option appear in the bottom bar.

---

## Clock

Record and manage clock-in and clock-out events for employees belonging to your assigned partners.

### Views

Toggle between **Calendar** and **Table** views using the button in the top-right area.

### Calendar view

A grid with one column per employee (from your assigned partners) and one row per day. Each cell shows the employee's clock events for that day:

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

Use the **+ Add clock** button to record a historical entry. Set employee, clock-in time, optional clock-out time, site, and note.

### Edit day modal (calendar view)

Clicking a completed-event cell opens an edit dialog. The **Existing note** is shown read-only; use the **Append note** field to add text — an audit stamp (your name + timestamp) is appended automatically on save.

---

## Employees

View and manage employees who belong to your assigned partners.

> CSV import is not available for partner managers.

### Filtering

Use the filter pills — **Active / Inactive / All** — to narrow the list.

### Adding an employee

Click **Add employee** and fill in name, position, optional email/phone/PIN, and default site.

### Editing an employee

Click **Edit** to open the employee's edit page. You can update name, position, email, phone, date of birth, default site, PIN, auto-clock settings, and auto-locate.

**Status changes** (Active / Inactive) require a reason, which is appended to the employee's audit notes.

**Danger zone** (inactive employees only) — a **Hide employee** button makes the employee invisible; only a super admin can unhide.

### PDF download

**↓ PDF** downloads a landscape A4 employee list for your scope.

---

## Changing your password

Click your name in the bottom bar, then **Change password**. You must enter your current password to set a new one (minimum 8 characters).
