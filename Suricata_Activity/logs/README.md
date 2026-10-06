# logs/

Sample log output from Suricata, showing the custom ICMP alert firing.

| File | Description |
|---|---|
| `eve.json` | Detailed, structured JSON log — covers alerts, flows, DNS, TLS, HTTP, and more. |
| `fast.log` | Lightweight, minimal log — focused only on alerts, easy to scan quickly. |

Captured from `/var/log/suricata/` after triggering a test ping to confirm the
custom rule in `rules/local.rules` fires correctly:
```bash
ping -c 4 <target-ip>
sudo tail -20 /var/log/suricata/fast.log
sudo tail -20 /var/log/suricata/eve.json
```

Copy your real log entries into the placeholder files here, replacing the sample
content.
