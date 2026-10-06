# Notes — Key Concepts

- **Suricata** is an open-source IDS, IPS, and Network Security Monitoring (NSM)
  tool. It inspects network traffic and generates alerts/logs based on rules.
- **eve.json** is Suricata's detailed, structured JSON log — covers alerts, flows,
  DNS, TLS, HTTP, and more. Rich but larger.
- **fast.log** is a lightweight, minimal log focused only on alerts — easier to
  scan quickly, but far less detail than `eve.json`.
- **Backing up `suricata.yaml` before editing it** is standard analyst practice —
  protects against breaking the configuration in a way that's hard to undo.
- **Custom rules** go in a local rules file (e.g. `local.rules`), loaded by
  Suricata on startup/restart. A rule must be on a single line with straight
  quotes and a plain `->` — copy-pasting from rich text sources (Word, web pages)
  can corrupt these into HTML entities (`&gt;`, `&quot;`).
- **Testing a rule** means triggering the traffic it's designed to catch (e.g. a
  test ping for an ICMP rule) and confirming the alert shows up in both
  `fast.log` and `eve.json`.
