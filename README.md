# Company Board PWA

An installable company communication app for HR news, weather, safety notices, shift updates, and read-only employee viewing.

## What This Is

- Employees open the board from any modern phone browser and can install it to their home screen.
- HR signs into a simple dashboard and publishes updates.
- Employee mode is read-only.
- The Render demo uses a small Node server and JSON storage so it can run on a free web service.

## Run Locally

```powershell
npm start
```

Open:

- Employee board: http://localhost:3000/#employee
- HR dashboard: http://localhost:3000/#admin

Default local HR PIN:

```text
2468
```

Set a real PIN before hosting:

```powershell
$env:HR_PIN="change-this-pin"
npm start
```

## Free Render Demo Deployment

This repo includes `render.yaml` for Render's free web service path.

1. In Render, choose **New > Blueprint**.
2. Select this GitHub repository.
3. Render will read `render.yaml`.
4. When prompted for `HR_PIN`, enter a private PIN for HR.
5. Click **Apply**.

Render will provide a public HTTPS URL. Employees can open that URL on iPhone or Android and add it to their home screen.

Important: this first Render setup is a demo deployment. It stores updates in `data/board.json`, which is not the right storage model for final production hosting. When the demo is approved, upgrade storage to Supabase, Cloudflare D1, or another managed database before real company use.

## Production Upgrade Checklist

- Replace PIN access with real HR login.
- Move `data/board.json` to a database.
- Add push notifications for urgent alerts.
- Add company branding per customer.
- Add image/file attachments.
- Add audit log for compliance.
- Add role-based access for HR, safety, managers, and admins.
- Add weather API integration by location.
