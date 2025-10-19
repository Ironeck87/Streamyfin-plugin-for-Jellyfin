# Quick curl tests

```bash
# Broadcast to all registered devices
curl -H 'Content-Type: application/json' \
     -H 'Authorization: MediaBrowser Token="YOUR_API_KEY"' \
     -d @examples/broadcast-test.json \
     http://<jellyfin>/jellyfin/streamyfin/notification

# Target a specific Jellyfin userId
curl -H 'Content-Type: application/json' \
     -H 'Authorization: MediaBrowser Token="YOUR_API_KEY"' \
     -d '[{"title":"Hi","body":"Test","userId":"PASTE_ID"}]' \
     http://<jellyfin>/jellyfin/streamyfin/notification