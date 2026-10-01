# Self-hosted deployment

This build is designed to run independently of Manus. The application has no built-in license expiration, trial timer, Manus OAuth, Manus runtime API, or Manus notification service dependency.

## Required
- `DATABASE_URL`: your own MySQL/TiDB-compatible database.
- `JWT_SECRET`: a long random secret used to sign staff sessions. Required in production.
- `PORT`: HTTP port (defaults to 3000).

## Optional
- `AI_API_URL` + `AI_API_KEY`: only if you enable an AI-compatible feature yourself. There is no default AI provider URL.
- `GOOGLE_MAPS_API_KEY` + `VITE_GOOGLE_MAPS_API_KEY`: only if you choose to use the unused Maps component.
- `UPLOAD_DIR`: local file storage directory; defaults to `uploads`.

## Important
The site itself has no expiry date. Staff JWT sessions expire after 30 days and require a fresh login; this is a security session lifetime, not a site/license expiry.

For production, use your own domain, hosting/server, and database. If those services remain online, the application has no built-in timer that shuts it down.
