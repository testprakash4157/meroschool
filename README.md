# EduAccounts Pro — School Accounting System

## Live Hosting on GitHub Pages + Google Sheets Backend

---

## 🚀 Step 1 — Setup Google Apps Script (Backend/Database)

1. Go to [sheets.google.com](https://sheets.google.com) → Create a **new blank spreadsheet**
2. Name it: `EduAccounts Pro Database`
3. Click **Extensions → Apps Script**
4. Delete all existing code and paste the entire contents of `gas_backend.js`
5. Click **Save** (💾)
6. Click **Deploy → New Deployment**
   - Type: **Web App**
   - Execute as: **Me**
   - Who has access: **Anyone**
7. Click **Deploy** → Copy the **Web App URL** (looks like `https://script.google.com/macros/s/XXXX/exec`)
8. Open `index.html`, find line with `var GAS_URL` and replace the placeholder with your URL

---

## 🌐 Step 2 — Host on GitHub Pages

1. Create a new GitHub repository (e.g. `eduaccounts-pro`)
2. Upload these files:
   - `index.html`
   - `README.md`
3. Go to **Settings → Pages**
4. Source: **Deploy from branch → main → / (root)**
5. Click **Save**
6. Your app will be live at: `https://yourusername.github.io/eduaccounts-pro`

---

## ✅ Features

| Feature | Description |
|---|---|
| 🔴 Live Data | All data saved to Google Sheets in real-time |
| 🌐 Multi-browser | Open from any browser/device — data is always synced |
| 📊 Auto-create Sheets | All sheets and headers created automatically on first run |
| 🔐 Secure Login | Role-based access (Admin / Cashier / Accountant / Viewer) |
| 🧾 Cash Receipt | Create, Edit, Delete, Print 2-copy voucher |
| 💸 Party Payment | Submit → Admin approves → Print unlocks |
| 💰 Misc Income | Full CRUD + 2-copy print |
| 📈 Income & Expense | Full ledger with running balance |
| 📒 Party Ledger | Party-wise statement |
| 👤 Party Master | Full CRUD with balance tracking |
| 👥 User Management | Full CRUD, permissions, activate/deactivate |
| ✅ Approvals | Admin approve/reject payment vouchers |
| 🚫 Blacklist | Add/Edit/Remove blacklisted parties |
| 📝 Notes | Priority notes with user assignment |
| 💬 Messages | Internal messaging system |
| ⚙️ Settings | Company, Currency, Voucher, Appearance |

---

## 🔑 Default Login Credentials

| Username | Password | Role |
|---|---|---|
| `admin` | `admin123` | Administrator (Full Access) |
| `user1` | `user123` | Cashier (Limited Access) |

> Change passwords after first login from User Management.

---

## 📁 File Structure

```
eduaccounts-pro/
├── index.html        ← Main app (open this in browser)
├── gas_backend.js    ← Paste this into Google Apps Script
└── README.md         ← This file
```

---

## 🔄 How Data Sync Works

```
Browser (index.html)
      ↕  fetch() API calls
Google Apps Script Web App URL
      ↕  read/write
Google Sheets (live database)
```

Every create/edit/delete immediately calls the GAS API and updates Google Sheets.
When any user opens the app, it fetches fresh data from Sheets.
