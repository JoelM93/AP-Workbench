# AP Workbench

A personal Accounts Payable management web application, built to practice real-world AP workflows: invoice tracking, vendor management, approvals, due-date monitoring, and AP aging reports.

> **All data in this project is fictional sample data** for learning and demonstration. No confidential employer or vendor information is used anywhere in the app.

## Features (v1)

1. **AP Dashboard** — KPI cards (total outstanding, overdue amount, due this week, pending approvals), a payables-by-status bar chart, a payables-by-aging-bucket chart, and a "Due Soon" table for the next 7 days.
2. **Invoice entry and tracking** — add invoices (vendor, invoice number, dates, amount, status, approver), edit and delete them, and filter the list by payment status or "due soon".
3. **Vendor management** — add, edit, and delete vendors with contact info, payment terms, and category. Each vendor shows its open (unpaid) balance. A vendor with linked invoices cannot be deleted.
4. **Due dates and payment statuses** — statuses are Paid, Pending, Scheduled, and Overdue. Overdue is computed automatically: any unpaid invoice whose due date has passed is flagged and highlighted in red.
5. **Approval tracking** — each invoice has an approval status (Pending / Approved / Rejected) with one-click Approve and Reject buttons and an approver name.
6. **AP aging report** — unpaid invoices grouped into buckets: Current, 1–30, 31–60, 61–90, and 90+ days past due, with totals per bucket and a per-vendor breakdown.
7. **Excel/CSV import and export** — export all invoices to a CSV file (opens in Excel or Google Sheets); import invoices from a CSV file. New vendors in an import are created automatically with Net 30 terms.

Data is saved in the browser's `localStorage`, so edits survive page reloads. A **Reset Sample Data** button on the Import / Export tab restores the original fictional data set (14 invoices, 6 vendors).

## How to run

No build step, no server, no installation.

1. Open `index.html` in any modern browser — double-click it, or open it from your phone's Files app. It works offline, including from `file://`.
2. Use the tabs at the top to move between Dashboard, Invoices, Vendors, Aging Report, and Import / Export.

## Tech stack

- **HTML** — page structure and forms
- **CSS** — styling, responsive layout (works on phone and desktop), status pills, and pure-CSS bar charts
- **JavaScript** — data layer, rendering, and event handling, all in one inline `<script>` block
- **localStorage** — persistence, no backend or database

The code is organized for a beginner to read and extend:

- **Data layer** — sample data, `loadData()` / `saveData()`
- **Helpers** — date math, money formatting, computed status, aging buckets
- **Render functions** — one per tab (`renderDashboard`, `renderInvoices`, `renderVendors`, `renderAging`)
- **Event handlers** — forms, table buttons, CSV import/export

## Roadmap (v2 and beyond)

- Automated invoice processing and duplicate detection
- AI-powered invoice data extraction (e.g. from a photo or PDF)
- Workflow automation (approval routing, payment reminders)
- More advanced reporting and analytics (spend by vendor/category over time, payment history)
- Search across invoices and vendors
- Multi-currency support
- User accounts / cloud sync (would require a backend — out of scope for the single-file version)

## License

Personal project. Fictional data only.
