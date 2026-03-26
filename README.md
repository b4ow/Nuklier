# Nuklier
Scanner Zero-Day
markdown
# 🔬 NUKLIER v6.0 - Ultimate WAF Bypass Scanner

> Advanced web vulnerability scanner with 15+ bypass techniques and 500+ payloads

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

## ⚠️ DISCLAIMER

**THIS TOOL IS FOR EDUCATIONAL AND AUTHORIZED TESTING PURPOSES ONLY.**
- Only use on systems you own or have explicit permission to test
- Unauthorized access is illegal and unethical
- The author assumes no responsibility for misuse

## ✨ Features

| Category | Details |
|----------|---------|
| **15 Bypass Techniques** | Double encoding, SQL comments, case mutation, chunked transfer, DNS OOB, JSONP/CORS, GraphQL introspection, JWT alg none, SSTI chaining, header injection, log poisoning, XXE via SVG, SSRF parser bypass, parameter pollution, TRACE method |
| **500+ Payloads** | Comprehensive collection of WAF bypass payloads |
| **8 Vulnerability Types** | SQLi, XSS, LFI, RCE, SSRF, SSTI, XXE, JWT |
| **WAF Detection** | Cloudflare, AWS WAF, ModSecurity, Sucuri, Imperva, Akamai, F5, Fortinet |
| **CSRF Handling** | Automatic CSRF token extraction for POST forms |
| **Parameter Fuzzing** | Automatic parameter discovery |
| **DNS OOB** | Blind injection detection via DNS callbacks |
| **HTML & JSON Reports** | Detailed findings with remediation suggestions |

## 🚀 Installation

bash
git clone https://github.com/yourusername/nuklier.git
cd nuklier
pip install -r requirements.txt


📖 Usage

Basic Scan

bash
python nuklier.py http://target.com/page.php?id=1


Advanced Options

bash
python nuklier.py http://target.com/page.php?id=1 \
    --threads 50 \
    --timeout 8 \
    --cookie "PHPSESSID=abc123" \
    --proxy http://127.0.0.1:8080 \
    --dns your-callback.com

🎯 Examples

bash
# Scan with cookie
python nuklier.py http://target.com/dashboard.php --cookie "session=xyz789"

# Scan via Burp proxy
python nuklier.py http://target.com/page.php?id=1 --proxy http://127.0.0.1:8080

# Custom DNS callback
python nuklier.py http://target.com/page.php?id=1 --dns oast.b4ow.com


📊 Output

Terminal

[CRITICAL] SQLi | http://target.com/page.php?id=1' OR 1=1--
[HIGH] SSRF Bypass | http://target.com/page.php?url=http://169.254.169.254/


Reports

· nuklier_report.html - Interactive HTML report
· nuklier_xxxx.json - JSON format for automation

🛡️ Bypass Techniques

Technique Description
Double Encoding URL encode twice to bypass WAFs
SQL Comments /*!50000UNION*/ bypass regex filters
Case Mutation UnIoN SeLeCt bypass case filters
Chunked Transfer Split payload across HTTP chunks
DNS OOB Blind injection via DNS queries
JWT Alg None Bypass JWT signature verification
SSTI Chaining Template injection to RCE
SSRF Parser Bypass 0.0.0.0, IPv6 variations

📁 Requirements

aiohttp>=3.8.0
dnspython>=2.3.0

🤝 Contributing

1. Fork the repository
2. Create feature branch
3. Submit pull request

📝 License

MIT License - See LICENSE file

👤 Author

b4ow - Security Researcher

· Telegram: @b-4ow
· GitHub: @b4ow

---

⚠️ Remember: Use responsibly. 


