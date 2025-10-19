# Streamyfin plugin config for Jellyfin

This repo stores my **Streamyfin companion plugin** configuration (YAML) for Jellyfin.
It sets sane client defaults and enables notifications without changing Jellyfin’s core setup.

> Streamyfin’s companion plugin lets you centrally manage Streamyfin app settings
> and exposes a notification endpoint you can call from services like Jellyseerr. :contentReference[oaicite:0]{index=0}

---

## Files

- `streamyfin.yaml` — the plugin configuration I apply in Jellyfin (sanitized).
- (optional) `examples/` — webhook payloads I use for Jellyseerr.

---

## Requirements

- Jellyfin server (10.8+ recommended).
- Streamyfin **companion plugin** installed (see below). :contentReference[oaicite:1]{index=1}

---

## Install the Streamyfin plugin in Jellyfin

1. In Jellyfin open **Dashboard → Plugins → Catalog → ⚙️ (Catalog settings) → Repositories → Add**.  
2. Paste this repository URL:  
   `https://raw.githubusercontent.com/streamyfin/jellyfin-plugin-streamyfin/main/manifest.json`  
3. Go back to **Catalog**, search **Streamyfin**, install, and **restart Jellyfin**. :contentReference[oaicite:2]{index=2}

---

## Apply this YAML

1. In Jellyfin go to **Dashboard → Plugins → Streamyfin → Settings**.  
2. Switch to the **YAML** editor and paste the contents of `streamyfin.yaml`.  
3. Save, then in the Streamyfin app **pull to refresh** (or restart the app) so it syncs.

> The plugin supports editing via YAML or a form UI; I keep my YAML here for versioning. :contentReference[oaicite:3]{index=3}

---

## What my config does (high level)

- Leaves the **Home** layout to the app (no custom sections pushed).  
- Tunes playback controls (skip times, rotate, etc.).  
- Sets **poster** image style for libraries.  
- Enables **Item Added** notifications (with a dedupe threshold to avoid spam).  
  See the plugin’s notifications overview for more details. :contentReference[oaicite:4]{index=4}

---

## (Optional) Jellyseerr → Streamyfin webhooks

You can have Jellyseerr send request events to the Streamyfin plugin’s notification endpoint.

**Webhook URL (in Jellyseerr):**
