# Expense_tracker
# 💸 Spendwise — Personal Expense Tracker

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-00C896?style=for-the-badge)
![Deploy Ready](https://img.shields.io/badge/Deploy-Ready-4E8BFF?style=for-the-badge)

> A fully client-side personal finance web application — track income & expenses, view real-time summaries, analyse spending by category, and visualise 6-month trends. Zero backend. Zero dependencies. One HTML file.

---

## 🖥️ Live Preview

```
Open index.html in any modern browser — works instantly, no setup required.
```

---

## ✨ Features

### 💰 Financial Dashboard
- **Real-time KPI cards** — Total Income, Total Expenses, Net Balance, Savings Rate
- **Net Balance** turns red automatically when expenses exceed income
- **Savings Rate** computed as `(Balance ÷ Income) × 100`

### 📋 Transaction Management
- Add **income & expense** entries with description, amount, category, date, and note
- **Quick-Add modal** accessible from the top navbar for fast entry
- **Delete** individual transactions with a hover-reveal button
- **Clear All** with a confirmation dialog

### 🗂️ 14 Transaction Categories

| Type | Categories |
|------|-----------|
| 💳 Expense | Food & Dining, Transport, Shopping, Bills & Utilities, Health & Medical, Education, Entertainment, Rent & Housing, Other |
| 💰 Income | Salary, Freelance, Investment, Gift / Received, Other |

### 🔍 Search & Filter
- **Live search** across description and note fields
- **Type filter** — All / Income / Expense
- **Category filter** — any of the 14 categories
- Transactions grouped by **date (newest first)**

### 📊 Analytics
- **Category spending breakdown** — animated progress bars proportional to spend, sorted descending with % share
- **6-month bar chart** — side-by-side income vs expense bars for current and past 5 months
- **Stat chips** — transaction count, average expense, top spending category

### 🗓️ Month Navigation
- Prev / Next arrows to browse any past or future month
- All calculations and charts update to the selected month's data

### 💾 Data Persistence
- All data saved to **localStorage** — survives page refresh with no backend
- Auto-seeds **15 realistic demo transactions** on first visit

---

## 📁 Project Structure

```
spendwise/
└── index.html        ← Entire app (HTML + CSS + JS in one file)
```

That's it. No `node_modules`, no `package.json`, no build step.

---

## 🚀 Getting Started

### Run Locally

```bash
# Clone the repository
git clone https://github.com/your-username/spendwise.git

# Navigate into the folder
cd spendwise

# Open in browser (any of the below)
open index.html                        # macOS
start index.html                       # Windows
xdg-open index.html                    # Linux
```

Or simply **double-click** `index.html` in your file explorer.

### Optional — serve with a local server

```bash
# Python (built-in)
python -m http.server 8000

# Node.js (npx, no install needed)
npx serve .
```

Then visit `http://localhost:8000`.

---

## ☁️ Deployment

Since Spendwise is a static single-file app, it deploys in seconds on any static hosting platform.

### Netlify (Drag & Drop)
1. Go to [netlify.com](https://netlify.com) → **Add new site**
2. Drag and drop the `index.html` file (or the project folder)
3. Done — live URL generated instantly ✅

### GitHub Pages
1. Push this repository to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your app is live at `https://your-username.github.io/spendwise/`

### Vercel
```bash
npx vercel
```
Vercel auto-detects it as a static site — zero configuration needed.

### Cloudflare Pages
1. Connect your GitHub repository in the Cloudflare dashboard
2. Leave build settings blank (static site)
3. Deploy ✅

---

## 🧮 How Calculations Work

| Metric | Formula |
|--------|---------|
| Total Income | Sum of all `type = "income"` amounts in selected month |
| Total Expenses | Sum of all `type = "expense"` amounts in selected month |
| Net Balance | Total Income − Total Expenses |
| Savings Rate | `(Net Balance ÷ Total Income) × 100` — returns 0% if no income |
| Average Expense | Total Expenses ÷ Number of expense transactions |
| Category Share % | `(Category Amount ÷ Total Expenses) × 100` |
| Chart Bar Height | `(Month Amount ÷ Max Amount across 6 months) × 100px` |

---

## 🎨 Tech Stack

| Technology | Usage |
|-----------|-------|
| **HTML5** | Semantic structure, native `date` and `number` inputs, data attributes |
| **CSS3** | Custom properties, Grid & Flexbox, keyframe animations, backdrop-filter, CSS data URIs |
| **JavaScript ES6+** | DOM manipulation, Array.reduce/filter/sort, Date API, localStorage, template literals |
| **Web Storage API** | `localStorage` for cross-session data persistence |
| **Google Fonts** | Plus Jakarta Sans (UI) + JetBrains Mono (monetary values) |

---

## 📸 App Sections

```
┌─────────────────────────────────────────────────────────┐
│  💸 Spendwise        [◀ June 2025 ▶]       [+ Add Entry]│
├─────────────────────────────────────────────────────────┤
│  💰 Income   💳 Expenses   ⚖️ Balance   📈 Savings Rate  │
├──────────────────────────────┬──────────────────────────┤
│  🔍 Search  [Type▼] [Cat▼]  │   Add Transaction Form   │
│  ─────────────────────────  │   ○ Expense  ○ Income    │
│  📅 10 Jun                  │   Desc │ Amount           │
│  🍽️ Dinner Out   −₹1,800   │   Cat  │ Date             │
│  🚇 Metro Card  −₹500      │   Note (optional)         │
│  ─────────────────────────  │   [+ Add Transaction]    │
│  📅 07 Jun                  ├──────────────────────────┤
│  🛒 Groceries  −₹3,400     │  Spending by Category    │
│                              │  🍽️ Food ████████ 34%   │
│  📊 Monthly Overview        │  🏠 Rent ███████  29%   │
│  [Jan][Feb][Mar][Apr][May]  │  🛍️ Shop ████     16%   │
│  [Jun - current highlighted]│  ...                     │
└──────────────────────────────┴──────────────────────────┘
```

---

## 🧪 Test Credentials / Demo Data

On first launch, the app auto-loads **15 demo transactions** for the current month, including:

- Monthly Salary — ₹65,000 (Income)
- Freelance Project — ₹12,000 (Income)
- Apartment Rent — ₹18,000 (Expense)
- Grocery Shopping — ₹3,400 (Expense)
- And 11 more across Food, Transport, Bills, Health, Education, Entertainment

To start fresh: click **"Clear all"** in the transaction panel header.

---

## 🗺️ Future Roadmap

- [ ] Budget limits per category (amber/red alerts)
- [ ] Recurring transactions (daily / weekly / monthly)
- [ ] CSV export via Blob API
- [ ] IndexedDB migration for large datasets
- [ ] PWA support (offline + installable)
- [ ] Multi-currency with exchange rate API
- [ ] Doughnut chart for category share (Canvas API)
- [ ] Cloud sync via Firebase Firestore

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

Built as a **B.Tech CSE 4th Semester Web Development Project**.

> *"Track every rupee. Understand every pattern. Own your finances."*

---

<div align="center">
  Made with HTML, CSS & JavaScript &nbsp;·&nbsp; No frameworks. No excuses.
</div>
