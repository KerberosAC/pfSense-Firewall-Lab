# pfSense Screenshot Guide

Source: `Cyber Home Lab Doc 1.docx`. These are original embedded screenshots, not stock illustrations.

| Original embedded image | GitHub filename | What it shows |
|---|---|---|
| `image49.png` | `screenshots/01-pfsense-virtual-machine.png` | pfSense VM, FreeBSD (64-bit), 4096 MB RAM, two processors, 16 GB virtual disk |
| `image50.png` | `screenshots/02-pfsense-wan-lan-console.png` | WAN em0 192.168.100.245/24 via DHCP; LAN em1 172.30.2.1/24 |
| `image51.png` | `screenshots/03-pfsense-internal-adapter.png` | Adapter shown attached to Internal Network named pfVulnlab1; capture shows one adapter setting |
| `image52.png` | `screenshots/04-kali-internal-adapter.png` | Kali adapter attached to the same named internal network pfVulnlab1 |
| `image53.png` | `screenshots/05-kali-ip-addresses.png` | ip address output: eth0 192.168.100.207/24 and eth1 172.30.2.100/24 |
| `image54.png` | `screenshots/06-pfsense-web-login.png` | Browser shows pfSense web configuration interface sign-in |
| `image55.png` | `screenshots/07-pfsense-general-setup.png` | Hostname and domain settings from pfSense setup flow |
| `image56.png` | `screenshots/08-lan-block-rule-action.png` | Firewall > Rules > Edit displays Block, LAN interface, IPv4 and Any protocol |
| `image57.png` | `screenshots/09-lan-rule-source-destination.png` | Source LAN subnets and destination Any in the displayed form |
| `image58.png` | `screenshots/10-lan-firewall-rules.png` | Existing LAN rules and order in the pfSense interface |
| `image59.png` | `screenshots/11-metasploitable-connectivity.png` | ping 8.8.8.8 receives replies in the displayed test |
| `image60.png` | `screenshots/12-nat-port-forward-screen.png` | Firewall > NAT > Port Forward initial rules view |
| `image61.png` | `screenshots/13-nat-redirect-target.png` | WAN address redirect target IP 172.30.2.102; screenshot shows rule editing values |
| `image62.png` | `screenshots/14-nat-port-forward-rule.png` | NAT table lists the WAN rule with target 172.30.2.102 |
| `image63.png` | `screenshots/15-putty-ssh-connection-setup.png` | PuTTY configured to contact 192.168.100.245 on TCP port 22 |
| `image64.png` | `screenshots/16-putty-ssh-session-result.png` | Login through pfSense WAN address reaches the Metasploitable test machine |
| `image65.png` | `screenshots/17-pfsense-snort-package.png` | pfSense Package Manager screen for the Snort add-on |
| `image66.png` | `screenshots/18-pfsense-snort-custom-rules.png` | custom.rules includes SID 1000001 Ping Detected and SID 1000002 SSH Detected |
| `image67.png` | `screenshots/19-snort-lan-interface-status.png` | LAN (em1) active, pattern match AC-BNFA; blocking mode shown disabled at this stage |
| `image68.png` | `screenshots/20-snort-icmp-alerts.png` | Alert log shows custom Ping Detected events with SID 1:1000001 |
| `image69.png` | `screenshots/21-putty-ssh-test.png` | PuTTY SSH login prompt against 192.168.100.245 during testing |
| `image70.png` | `screenshots/22-snort-ssh-alerts.png` | Snort alert log shows SSH Detected entries associated with SID 1:1000002 |
| `image71.png` | `screenshots/23-snort-blocking-settings.png` | Block Offenders, IPS Mode, Kill States and Which IP to Block settings screenshot |
| `image72.png` | `screenshots/24-windows-ping-pfsense.png` | ping 192.168.100.245 displays responses and one request timed out |
| `image73.png` | `screenshots/25-snort-active-alert-log.png` | Log summary with 91 entries and sample Ping Detected events |
| `image74.png` | `screenshots/26-snort-blocked-hosts.png` | Blocked-hosts panel shows a host entry for 192.168.100.70 |
| `image75.png` | `screenshots/27-snort-ip-alias-settings.png` | General Information with custom alias IP 192.168.100.70 |
| `image81.png` | `screenshots/28-opt1-firewall-rules-separate-stage.png` | OPT1 rule with 172.60.1.0/24 source, distinct from 172.30.2.0/24 testing segment |

## Notes

- Original images **49–75** form the pfSense firewall and pfSense-Snort walkthrough.
- `image81.png` shows an additional OPT1 firewall-rule stage and is intentionally presented separately.
- Screenshots from **standalone Ubuntu Snort** (earlier in the document) are excluded; the pfSense Snort package is included here.
- The final two Snort rules in `rules/` were transcribed from original `image66.png`, with standard final option semicolons.
- No evidence of a fully verified production deployment is claimed.
