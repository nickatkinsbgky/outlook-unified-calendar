# Outlook Unified Calendar Viewer

A standalone web app that signs you into multiple Microsoft / Outlook accounts and displays all their calendars in one unified FullCalendar view.

## Features
- Add multiple Outlook.com, Hotmail, Microsoft 365, or work/school accounts
- Fetches every calendar (primary + secondary) from each account
- Unified month / week / day / list views
- Color-coded by account
- Works as a Progressive Web App (add to home screen on Android)
- No backend — pure client-side (MSAL + Microsoft Graph)

## Setup (required before it works)

1. Go to [Azure Portal](https://portal.azure.com) → Microsoft Entra ID → App registrations → New registration.
2. Name: `Outlook Unified Calendar`
3. Supported account types: **Accounts in any organizational directory and personal Microsoft accounts**
4. Redirect URI: Single-page application (SPA) → `https://nickatkinsbgky.github.io/outlook-unified-calendar/` (or `http://localhost:5500` for local testing)
5. Register.
6. Copy the **Application (client) ID**.
7. Open `index.html` and replace `YOUR_CLIENT_ID_HERE` with that ID.
8. Under API permissions → Add a permission → Microsoft Graph → Delegated → `Calendars.Read` → Add. Grant admin consent if you control the tenant (optional for personal accounts).

## Deploy / Run

### GitHub Pages (recommended)
1. In the repo Settings → Pages → Source: Deploy from branch `main` / `/ (root)`.
2. Wait a minute, then open `https://nickatkinsbgky.github.io/outlook-unified-calendar/`.

### Local
Serve the folder with any static server (e.g. VS Code Live Server, `npx serve`, Python `http.server`) and open it.

## Usage
1. Click **Add Account** and sign in with each Outlook account you want.
2. Events from all calendars appear together.
3. Use the checkboxes to hide/show specific calendars.
4. Click Refresh if needed.

## Notes
- Tokens stay in your browser only.
- Refresh rate is manual or on view change (Graph calendarView is efficient).
- For true two-way sync or more providers, consider third-party tools; this is a pure viewer.

Built for multi-account Outlook users who want one clean calendar view.
