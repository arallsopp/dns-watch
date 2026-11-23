# dns-watch

Scheduled GitHub Action that sends one push notification (via ntfy.sh) when a
host's DNS starts resolving to a given IP, then disables itself.

Secrets: `WATCH_HOST`, `TARGET_IP`, `NTFY_TOPIC`.

- Test the notification: `gh workflow run dns-watch.yml -f test=true`
- Re-arm after it fires: `gh workflow enable dns-watch.yml`

GitHub disables scheduled workflows in public repos after 60 days with no
commits; push any commit to reset that clock.
