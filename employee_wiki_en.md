# Employee Kiosk Guide

This guide explains how to use the employee self-service kiosk portal.

---

## Accessing the Kiosk

Open a browser and navigate to the kiosk URL provided by your company (typically `https://yourcompany.domain/kiosk`). The kiosk works on tablets, phones, and desktop browsers.

---

## Logging In

Login happens in two steps.

### Step 1 — Company code

Enter the **company code** given to you by your manager and press **Continue**. The app looks up your company and loads the employee list.

If the code is not recognised, an error message appears — double-check the code with your manager.

### Step 2 — Your name and PIN

Select your name from the dropdown list, enter your **PIN**, and press **Sign in**.

- If you enter the wrong PIN, an error is shown and you can try again.
- If your name does not appear in the list, you do not have a PIN set yet — ask your manager to add one from the admin panel.

### Returning visits

The kiosk remembers your company code in the browser session. On your next visit it skips the code step and goes straight to name and PIN selection. Clearing browser data or using a different browser will require entering the code again.

---

## Home Screen

After signing in you see the home screen with the following options:

- **Clock in / Clock out** — record your working hours
- **Request time off** — submit a leave request
- **My clocking** — view your clock history for any month
- **My time offs** — view your leave requests

Use **Sign out** at any time to return to the login screen.

---

## Clock In / Clock Out

### Clocking in

1. If your company has multiple sites, select the **work site** from the dropdown. Your default site (set by your manager) is pre-selected if available.
2. Optionally add a **note** (e.g. reason for a late start).
3. Press the large **Clock In** button.

**Auto-locate:** if your manager has enabled auto-locate for your account, a browser permission prompt will appear asking for your location. Your GPS coordinates are captured at clock-in and stored alongside the event. Whether you were on-site or not is visible to your admin in the timesheet — this is for information only and does not block you from clocking.

### Clocking out

When you are already clocked in, the screen shows your clock-in time, site, and any note. Optionally add a note for the clock-out and press the large **Clock Out** button.

### Auto-clock

If your schedule is managed with **auto-clock**, you will see an information card instead of the clock-in/out buttons. Auto-clock records your hours automatically every working day at the configured start and end times — you do not need to clock in manually. Approved time-off days and weekends are skipped automatically.

---

## My Clocking

Shows your clock-in and clock-out history for a selected month.

- Use the **month selector** (arrows or dropdown) to navigate between months.
- Entries are grouped by day with a subtotal per day.
- The bottom of the list shows your **total hours** and **billable hours** for the month.
- Billable hours exclude any events marked as void by your admin and may exclude break time if your company has a break schedule configured.

This section is read-only — contact your manager if you notice an error in your records.

---

## Request Time Off

Submit a leave request for your manager to review.

### Filling in the form

1. **Type** — select the leave category:
   - **CO** — paid annual leave
   - **CFP** — unpaid leave
   - **Medical** — sick leave / medical certificate
   - Marriage, Blood donation, Special events, Military, Funeral, Child birth

2. **Start date** — the first day of your requested leave.

3. **End date** — the last day. Must be the same as or after the start date.

4. **Note** (optional) — any additional context for your manager.

5. Press **Submit request**.

### After submitting

You will see a confirmation message. Your manager will review the request and approve, reject, or cancel it. Track the status under **My time offs**.

If some of the days you selected already have a pending or approved request, those days are skipped automatically and you are notified how many were submitted.

---

## My Time Offs

Shows all your time-off requests for a selected month, one row per working day.

Columns: Date, Day, Type, Status, Note.

**Status meanings:**

| Status | Meaning |
|--------|---------|
| Pending | Submitted, waiting for manager review |
| Approved | Accepted by your manager; auto-clock will skip these days |
| Rejected | Declined by your manager |
| Cancelled | Withdrawn (by you or your manager) |

Use the **month selector** to navigate between months. This section is read-only.

---

## Signing Out

Press **Sign out** on any kiosk screen to end your session and return to the login page. Always sign out when using a shared device.
