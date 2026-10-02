# epontez — user guides

End-user documentation for the epontez timekeeping platform, one guide per
audience, in English and Romanian.

| Audience | English | Română |
|---|---|---|
| Company administrator | [admin_wiki_en.md](admin_wiki_en.md) | [admin_wiki_ro.md](admin_wiki_ro.md) |
| Site manager | [site_manager_wiki_en.md](site_manager_wiki_en.md) | [site_manager_wiki_ro.md](site_manager_wiki_ro.md) |
| Partner manager | [partner_manager_wiki_en.md](partner_manager_wiki_en.md) | [partner_manager_wiki_ro.md](partner_manager_wiki_ro.md) |
| Employee (kiosk) | [employee_wiki_en.md](employee_wiki_en.md) | [employee_wiki_ro.md](employee_wiki_ro.md) |

Each guide is self-contained: a reader opens one page and never has to navigate
between files. That means shared topics — clocking, employees — appear in more
than one guide, so **a correction has to be applied in each copy that covers it**.
`grep -l` for a phrase before editing.

## Anchors are a stable interface

Every section carries an explicit anchor:

```html
<a id="clock-calendar"></a>

### Calendar view
```

**The same `id` means the same topic in every file and in both languages.** So
all four of these resolve to the calendar view:

```
admin_wiki_en.md#clock-calendar
admin_wiki_ro.md#clock-calendar
site_manager_wiki_en.md#clock-calendar
site_manager_wiki_ro.md#clock-calendar
```

This exists so the application can deep-link into the guides — a help icon next
to a feature pointing at the section that explains it, in the language the admin
is already using. Two rules follow:

1. **Never change an `id`, even when you reword its heading.** Something may be
   linking to it. Add a new one instead if a topic genuinely splits.
2. **Keep the id identical across languages and roles.** The whole scheme rests
   on `#x` meaning one thing.

Explicit anchors rather than relying on heading text, because Romanian headings
produce anchors full of diacritics that differ from the English ones — which
would make a language-independent link impossible.

### The anchor families

| Prefix | Covers |
|---|---|
| `login`, `navigation`, `password` | Signing in, the nav bar, changing a password |
| `role` | What a restricted role is and is not allowed to do |
| `status` | The dashboard |
| `clock-*` | Clocking: views, colours, bulk actions, manual entry, the lock |
| `employees-*` | The workforce, CSV, fingerprint enrolment |
| `program-*` | Roles, the shift library, the PONTAJ export |
| `planning-*` | The rota grid, assignment, swaps, leave from the grid |
| `sites-*` | Sites, coordinates, per-site auto clock-out |
| `incidents-*` | The Legea 319/2006 register |
| `partners` | Collaborator companies |
| `timesheets-*` | Hours, location pins, downloads |
| `timeoff-*` | Leave types, reading the table, actions |
| `terminals-*` | Fingerprint readers, mapping, push, punch log |
| `plan-*` | Cars, accommodation, the assignment screen |
| `settings-*` | Every company setting |
| `passkey-*`, `location-*`, `myclocking`, `mytimeoffs`, `problems` | Kiosk guide only |

List every anchor in a file with:

```bash
grep -o '<a id="[^"]*"' admin_wiki_en.md
```

Check a pair of files agree:

```bash
diff <(grep -o '<a id="[^"]*"' admin_wiki_en.md) \
     <(grep -o '<a id="[^"]*"' admin_wiki_ro.md)
```

## Keeping these in step with the application

The guides describe behaviour, including the reasoning behind rules that look
surprising — why a PIN stops working for clocking, why the partner filter on the
PONTAJ export defaults to excluding collaborators, why an off-site clock-in is
recorded rather than blocked. That reasoning is the part users most often need and
the part most easily lost, so prefer updating a paragraph to deleting it.

Worth re-checking after a release:

- **Navigation** — the ten sections and their Romanian labels.
- **Thresholds stated in prose** — the 15-minute shift grace, the 60-second
  terminal debounce, the 5-minute offline badge, the 500 m default radius and its
  25 m floor, 180-day location retention, the 48-hour name-edit window, the
  450-employee export cap.
- **Role limits** — what a site manager cannot do, and the partner manager's fixed
  pair of sections.
- **Romanian vocabulary** — a company can be configured to say *sediu* instead of
  *șantier*, which the guides note but do not duplicate.

Each guide ends with a line stating that the application is authoritative and the
page is what needs fixing when they disagree. Keep it there.
