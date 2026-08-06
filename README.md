# 🌾 Green Valley Farmer Union — Dues, Ledger, Statements & ID Cards

A single-file, self-contained web app for managing a farmer union's membership dues, payments, financial ledger, account statements, and member ID cards. No installation, no server, no internet connection required — just download and open the HTML file in a modern browser.

---

## Table of contents

- Quick start
- What the app does
- Modules (sidebar)
- Key features
- Printing tips
- Sample data included
- Technical notes
- Common customizations
- Roadmap ideas
- Contributing & license
- Disclaimer

---

## 🚀 Quick start

1. Download `dues-management-app.html`.
2. Double-click it to open in any modern browser (Chrome, Edge, Firefox, Safari).
3. That's it — the app runs entirely in your browser.

> ⚠️ **Demo data resets on refresh.** All data is held in memory. Reloading the page restores the original sample data (this is intentional, so you can demo repeatedly with clean numbers).

---

## 🧭 What the app does

The app models a three-tier structure:

```
Farmer Union
 └── Farmer Groups (50+)
        └── Farmers / Members
```

It tracks **who owes what**, **who paid**, **who collected the money**, and keeps everything reconciled in a **double-entry financial ledger**.

---

## 🗂️ Modules (sidebar)

| Module | What it does |
|---|---|
| 📊 **Dashboard** | KPIs (assessed, collected, outstanding, overdue), collection progress by group, funds held for the union. |
| 🏘️ **Farmer Groups** | Each group's dues owed, paid, and balance. Quick links to statement, add dues, or record payment. |
| 👤 **Farmers** | Each member's balance, with buttons for statement, **ID card**, add dues, and pay. |
| 🪪 **Member ID Cards** | Flexible card designer — generate & print standard membership cards. |
| ⚙️ **Dues Setup** | The configurable dues rules (who pays, who benefits, frequency). |
| 🧾 **Assessments** | Every "amount owed" — filterable by group / farmer / outstanding. |
| 💵 **Payments & Receipts** | Recorded payments, each with a printable official receipt. |
| 📄 **Statements & Reports** | Running-balance statements at **member**, **group**, and **union** level, plus arrears & income reports. CSV export + Print/PDF. |
| 📒 **Financial Ledger** | Double-entry journal + trial balance. Every payment auto-posts a balanced entry. |

---

## ⭐ Key features

### Dues management
- Set amount owed for a farmer group or an individual farmer.
- A farmer can owe **union dues and group dues at the same time** — each is a separate assessment with its own beneficiary.
- Record payments, tick which dues to settle, choose method, and mark whether the **union collected directly** or a **group collected on behalf of the union**.
- **Official receipts** auto-generated with a printable layout.

### Financial ledger
- Real **double-entry** bookkeeping — every payment creates a balanced journal entry.
- **Trial balance** and an integrity check confirming *total debits = total credits*.
- Separate income accounts (affiliation dues, membership dues, group dues) and a **clearing account** for money groups collect but haven't yet remitted to the union.

### Statements & reports
- **Running-balance statements** for any member, group, or the whole union.
- **Printable / PDF** statements with header, account details, and summary boxes.
- **CSV export** for use in Excel.
- Supporting reports: members in arrears, group arrears, and income by dues type.

### 🪪 Member ID cards
- Standard **CR80 credit-card size** (~85.6 × 54 mm) — laminates and prints correctly.
- Shows **member name, photo/avatar, farmer group, union branding, QR code, barcode, member ID, and validity date**.
- **Flexible designer:**
  - 3 templates — **Classic**, **Modern**, **Minimal**
  - Custom **accent colour**
  - Toggle fields (phone, date of birth, national ID, blood group, member since)
  - Adjustable **issue date** and **validity period**
  - Editable **role/title**
  - Optional **card back** (terms, signatures, return address)
- **Single card or batch** (all members at once).
- **Print / Save as PDF** — only the cards print; the interface is hidden.

---

## 🖨️ Printing tips

For receipts, statements, and ID cards:

1. Click the **🖨 Print / PDF** button.
2. In the print dialog:
   - Destination: **Save as PDF** (or your printer)
   - Margins: **None**
   - Background graphics: **On** (so colours and cards render)

---

## 🧩 Sample data included

- **1 union** — Green Valley Farmer Union
- **5 farmer groups**
- **6 farmers** (with phone, DOB, blood group, join date, etc. for ID cards)
- **4 dues types**, multiple assessments, payments, and journal entries

You can add new assessments and payments live; they flow through to the dashboard, statements, and ledger immediately.

---

## 🛠️ Technical notes

- **Stack:** Pure HTML + CSS + vanilla JavaScript. No frameworks, no dependencies, no build step.
- **Data:** A single in-memory `DB` object at the top of the `<script>`. Edit it to change the union name, groups, farmers, or dues.
- **Currency:** EUR (€) — change the `CUR` constant and `DB.union.currency` to switch.
- **Offline:** Works with no internet after download.

---

## 🔧 Common customizations

| Want to change… | Where to look (in the `<script>`) |
|---|---|
| Union name, logo, address, currency | `DB.union` object |
| Groups | `DB.groups` array |
| Members / farmers | `DB.farmers` array |
| Dues rules | `DB.duesTypes` array |
| Default ID-card style | `CARD` object |

---

## 📌 Roadmap ideas (not yet built)

- Uploadable member photos (replace the initials avatar)
- Duplex (front + back) ID-card print sheet
- Group **remittance** workflow (batching farmer-collected union dues)
- **Member shares / capital** module
- Persist data in the browser (localStorage) so it survives refresh
- Date-range / period filters on statements

---

## 🤝 Contributing & license

This repository contains a demo prototype. If you'd like to contribute improvements, please open an issue or pull request. Add tests or examples where appropriate and keep changes compatible with the single-file demo approach.

(If you want a license in the repo, tell me which license you prefer — I can add an SPDX header or a LICENSE file.)

---

## ⚖️ Disclaimer

This is a **demonstration prototype** with mock data. Before using it for real financial or membership records, have the accounting treatment and data-protection approach reviewed by a qualified accountant and a data-protection/legal advisor.

---

*Built as a self-contained prototype for the Green Valley Farmer Union dues & membership system.*
