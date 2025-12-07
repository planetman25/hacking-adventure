 ┌────────────────────────────────────────┐
 │ Windows Host (Attacker Browser)        │
 │ IP: 10.10.76.20 or 192.168.159.1       │
 │ Role: BeEF Panel access + Victim #1    │
 └────────────────────────────────────────┘
                ▲
                │ HTTP 3000 (UI Panel) + Hook communication + Victim machine
                ▼
 ┌────────────────────────────────────────┐
 │ Kali Linux VM (Attacker Machine)       │
 │ NAT Network                            │
 │ IP: 192.168.159.156                    │
 │ Services: BeEF, Python Web Server      │
 │ Tooling: Ruby, Bundler, BeEF v0.5.4.0  │
 └────────────────────────────────────────┘
                ▲
                │ HTTP 8080 (malicious web page)
                ▼
 ┌────────────────────────────────────────┐
 │ Windows VM (Victim Browser)            │
 │ IP: 192.168.159.159                    │
 │ Role: Browser exploitation target      │
 └────────────────────────────────────────┘


