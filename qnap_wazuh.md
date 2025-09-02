# Wazuh QNAP NAS Decoder and Rules

Wazuh Decoder and Rules for syslog sent from QNAP's Log Center to monitor connection logs and system events.


## Installation

### QNAP Configuration
1. Access QNAP Admin Panel → **QuLog Center**
2. Go to **Log Sender** → **Send to Syslog Server**
3. Configure syslog forwarding to your Wazuh Manager:
   - **Server**: `<Wazuh-Manager-IP>`
   - **Port**: `514`
   - **Protocol**: `UDP`
   - **Format**: `Standard Syslog`


### Wazuh 
1. Set up /var/ossec/etc/ossec.conf
2. Configure Remote section (514 port, protocol, etc)
3. Clone this repo to wazuh server and extract qnap_decoder.xml to /var/ossec/etc/decoders/
4. extract qnap_rules.xml to /var/ossec/etc/rules/
5. Restart wazuh manager ( systemctl restart wazuh-manager.service )
6. Test decoders using command  /var/ossec/bin/wazuh-logtest
7. Paste example log like: Sep  2 06:30:00 NAS8E49A8 qulogd[19113]: conn log: Users: Administrator, Source IP: 192.168.130.113, Computer name: ---, Connection type: HTTPS, Accessed resources: Administration, Action: Login Success


