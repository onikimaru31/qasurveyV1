# QA Lead 360° Assessment Platform — CP Axtra
**Version:** 1.0.0  
**Theme:** CP Axtra (Blue #003B7A · Yellow #FFD000)

---

## Quick Start

This is a **single HTML file** application — no installation, no server, no database required.

```
qa-survey-app-cpaxtra.html   ← the entire application
```

Just open the file in any modern browser, or deploy to any static web host.

---

## Default Admin Login

| Field    | Value      |
|----------|------------|
| Username | `admin`    |
| Password | `admin123` |

> ⚠️ Change these in the source code before production use.  
> Search for `ADMIN_CREDS` in the HTML file and update the values.

---

## Deployment Options

### Option 1 — Local (no server needed)
Double-click `qa-survey-app-cpaxtra.html` to open in browser.  
Survey links will use `file://` paths — suitable for same-machine testing only.

### Option 2 — Static Web Host (Recommended)
Upload the single HTML file to any of these free services:

| Platform       | Steps                                                |
|----------------|------------------------------------------------------|
| **Netlify**    | Drag & drop the file at netlify.com/drop             |
| **Vercel**     | `npx vercel` in the folder, or drag into dashboard   |
| **GitHub Pages** | Push to repo → Settings → Pages → Deploy from branch |
| **Cloudflare Pages** | Connect repo or drag & drop via dashboard       |
| **Firebase Hosting** | `firebase deploy` after `firebase init hosting`  |

### Option 3 — Company Intranet / SharePoint
Place the file on any shared web directory or SharePoint site that serves HTML files.

### Option 4 — Simple Python Server (local network)
```bash
# Python 3
python -m http.server 8080

# Then open: http://YOUR-IP:8080/qa-survey-app-cpaxtra.html
```

---

## How It Works

1. **Admin logs in** → manages QA Leads and survey questions
2. **Admin creates a survey link** → enters assessor name + position
3. **Link is shared** with the assessor (email, LINE, Teams, etc.)
4. **Assessor opens link** → fills in the evaluation form → submits
5. **Results appear instantly** in the Reports and Dashboard sections

---

## Data Storage

All data is stored in **browser localStorage** of the admin's browser.

- Key name: `qa360_cpaxtra_store`
- Data persists across page refreshes and browser restarts
- Data is **tied to the browser/device** where the admin portal is used
- Clearing browser data will erase all records — export reports before clearing

> For a shared/multi-device setup, consider deploying with a backend (see Customisation below).

---

## Survey Link Sharing

When you generate a survey link, it looks like:
```
https://your-domain.com/qa-survey-app-cpaxtra.html?survey=survey_1234567_abc123
```

Share this URL via:
- Email
- LINE / Microsoft Teams / Slack
- QR Code (use any free QR generator with the URL)

The assessor opens the link, fills the form, and submits. The result is saved automatically.

---

## Customisation

### Change Admin Password
Find in the `<script>` section:
```javascript
const ADMIN_CREDS = { username: 'admin', password: 'admin123' };
```
Update to your preferred credentials.

### Change Brand Colors
Find the `:root` CSS block:
```css
--blue: #003B7A;
--yellow: #FFD000;
```
Update hex values to match your brand.

### Change Application Title
Search for `QA 360° Assessment` and replace with your preferred title.

---

## Browser Support

| Browser          | Support |
|------------------|---------|
| Chrome 90+       | ✅ Full  |
| Edge 90+         | ✅ Full  |
| Firefox 88+      | ✅ Full  |
| Safari 14+       | ✅ Full  |
| Mobile Chrome    | ✅ Full  |
| Mobile Safari    | ✅ Full  |

---

## File Structure

```
qa-survey-app-cpaxtra.html
├── <style>        CSS — CP Axtra theme, layout, components
├── Auth Screen    Login page
├── Admin App      Dashboard, QA Leads, Questions, Surveys, Reports
├── Survey Page    Assessor-facing evaluation form
├── Modals         Add/Edit Lead, Add/Edit Question, Send Survey
└── <script>       Data store, all logic, routing
```

---

## Support

Built for CP Axtra QA Team internal use.  
All 13 QA Lead Evaluation Questions are pre-loaded and ready to use.
