# Command History

Paste the commands you actually ran during the activity below, in order.

```bash
sudo apt update
sudo apt install -y suricata
suricata -V

sudo cp /etc/suricata/suricata.yaml /etc/suricata/suricata.yaml.bak

sudo nano /etc/suricata/rules/local.rules
# added: alert icmp any any -> any any (msg:"SURICATA ICMP TEST ALERT"; sid:1000001; rev:1;)

sudo suricata -T -c /etc/suricata/suricata.yaml -v

sudo systemctl restart suricata
ping -c 4 <target-ip>

sudo tail -20 /var/log/suricata/fast.log
sudo tail -20 /var/log/suricata/eve.json
```

> Replace this block with your actual command history if it differs.
