# config_backup/

Holds the backup of `suricata.yaml` taken before making any configuration changes.

```bash
sudo cp /etc/suricata/suricata.yaml /etc/suricata/suricata.yaml.bak
sudo cp /etc/suricata/suricata.yaml.bak ~/Linux_Practice/Suricata_Activity/config_backup/
```

Taking a backup before editing a live config file is standard analyst practice —
it protects against breaking something that's hard to undo, and lets you quickly
restore a known-good state with:
```bash
sudo cp suricata.yaml.bak /etc/suricata/suricata.yaml
```

Replace `suricata.yaml.bak` in this folder with your real backup file.
