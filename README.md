# ContactCard

A lightweight, client-side contact manager built with plain HTML, Tailwind CSS (CDN), and vanilla JavaScript. All data is stored locally in the browser via `localStorage` — no backend required.

## Features

- **Add contacts** with name, company, email, phone, and a profile photo (stored as a base64 data URL).
- **Dashboard** listing all contacts as cards, with photo or initials fallback.
- **Favorites** — star contacts and view them on a dedicated page.
- **Edit** existing contacts (pre-filled form, updates in place).
- **Trash** — soft-delete with Restore, permanent delete, Empty Trash, and a 30-day auto-purge.
- Consistent sidebar navigation across all pages.

## Pages

| File | Purpose |
|------|---------|
| `dashboard.html` | Main list of all contacts |
| `addcontact.html` | Create a new contact |
| `edit.html` | Edit an existing contact (`edit.html?index=N`) |
| `favorites.html` | Favorited contacts only |
| `trash.html` | Soft-deleted contacts |

## Usage

Open `dashboard.html` in any modern browser. No build step or server is needed.

## Data model

Contacts are stored under the `contacts` key in `localStorage` as an array of objects:

```json
{
  "name": "Jane Doe",
  "company": "Acme",
  "email": "jane@example.com",
  "phone": "+1 (555) 000-0000",
  "photo": "data:image/png;base64,...",
  "favorite": false
}
```

Deleted contacts are moved to the `trash` key with an added `deletedAt` timestamp.

## Notes

- `localStorage` has a ~5MB limit; profile images are capped at 2MB each.
- Tailwind is loaded via CDN for convenience (not intended for production builds).
