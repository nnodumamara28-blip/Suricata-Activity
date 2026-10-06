# Suricata Activity — IDS/IPS/NSM Practical

## Objective
Hands-on practice with Suricata, an open-source Intrusion Detection System (IDS),
Intrusion Prevention System (IPS), and Network Security Monitoring (NSM) tool —
covering its logging outputs, safe configuration practices, and writing/testing a
custom detection rule.

## Repository Structure
```
Suricata_Activity/
├── README.md                  → this file
├── config_backup/
│   ├── README.md
│   └── suricata.yaml.bak      → backup taken before editing the config
├── rules/
│   ├── README.md
│   └── local.rules            → custom rule(s) written and tested
├── logs/
│   ├── README.md
│   ├── eve.json                → sample of Suricata's detailed JSON log
│   └── fast.log                → sample of Suricata's minimal alert log
├── evidence/
│   ├── README.md
│   └── screenshots/            → terminal screenshots of the activity
└── docs/
    ├── command_history.md      → commands run during the activity
    └── notes.md                → key concepts learned
```

## What this activity covered

**1. What Suricata is**
An open-source IDS/IPS/NSM engine that inspects network traffic and generates
alerts/logs based on defined rules.

**2. Logging outputs**
- `eve.json` — detailed, structured JSON log covering alerts, flows, DNS, TLS,
  HTTP, and more. Richer but larger.
- `fast.log` — a lightweight, minimal log focused only on alerts. Easier to scan
  quickly, but far less detail than `eve.json`.

**3. Safe configuration practice**
Before editing `suricata.yaml` (the main config file), a backup was taken first:
```bash
sudo cp /etc/suricata/suricata.yaml /etc/suricata/suricata.yaml.bak
```
This is standard analyst practice — a backup before any config change protects
against breaking something that can't easily be undone.

**4. Writing and testing a custom rule**
A local rule was added to `local.rules` and tested to confirm Suricata picks it up
and fires correctly:
```
alert icmp any any -> any any (msg:"SURICATA ICMP TEST ALERT"; sid:1000001; rev:1;)
```
Validated with:
```bash
sudo suricata -T -c /etc/suricata/suricata.yaml -v
```
Then triggered with a test ping and confirmed the alert appeared in both
`fast.log` and `eve.json`.

## How to use this on your Kali machine
1. Copy your real `suricata.yaml.bak`, `local.rules`, and log samples into the
   matching folders here, replacing the placeholders.
2. Save screenshots into `evidence/screenshots/`.
3. Fill in `docs/command_history.md` with the commands you actually ran.

## Pushing to GitHub
```bash
cd ~/Linux_Practice/Suricata_Activity
git init                                    # only if not already inside a repo
git add .
git commit -m "Document Suricata IDS/IPS activity: logging, config backup, custom rule"
git push
```
If this folder sits inside an existing repo (e.g. your `LINUX_PRACTICE` portfolio),
skip `git init` — just `add`, `commit`, and `push` from the repo root.

## Submission Checklist
- [ ] `suricata.yaml.bak` backup included
- [ ] `local.rules` with the custom ICMP alert rule
- [ ] Sample `eve.json` and `fast.log` entries showing the alert firing
- [ ] Screenshots in `evidence/screenshots/`
- [ ] Command history filled in
