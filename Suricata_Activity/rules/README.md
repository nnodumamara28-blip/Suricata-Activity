# rules/

Holds the custom Suricata rule(s) written and tested during this activity.

`local.rules` contains the custom ICMP test alert:
```
alert icmp any any -> any any (msg:"SURICATA ICMP TEST ALERT"; sid:1000001; rev:1;)
```

Loaded from `/etc/suricata/rules/local.rules` on the live system. Copy it in with:
```bash
sudo cp /etc/suricata/rules/local.rules ~/Linux_Practice/Suricata_Activity/rules/
```

**Tip:** rules must be on a single line with straight quotes (`"`) and a plain `->`
arrow. Copy-pasting from a Word doc or webpage can corrupt these characters into
HTML entities (`&gt;`, `&quot;`) — type rules directly in `nano` when possible.

Validate a rules file loads correctly with:
```bash
sudo suricata -T -c /etc/suricata/suricata.yaml -v
```
