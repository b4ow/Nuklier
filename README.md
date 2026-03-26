# Nuklier
Scanner Zero-Day

markdown
# ⚡ NUKLIER v6.0
## Ultimate WAF Bypass Scanner

```

███╗   ██╗██╗   ██╗██╗  ██╗██╗     ██╗███████╗██████╗ 
████╗  ██║██║   ██║██║ ██╔╝██║     ██║██╔════╝██╔══██╗
██╔██╗ ██║██║   ██║█████╔╝ ██║     ██║█████╗  ██████╔╝
██║╚██╗██║██║   ██║██╔═██╗ ██║     ██║██╔══╝  ██╔══██╗
██║ ╚████║╚██████╔╝██║  ██╗███████╗██║███████╗██║  ██║
╚═╝  ╚═══╝ ╚═════╝ ╚═╝  ╚═╝╚══════╝╚═╝╚══════╝╚═╝  ╚═╝

```
**by b4ow** | [@B4owBit_bot](https://t.me/B4owBit_bot) | **Death System**

---

## ✨ FEATURES

```

┌─────────────────────────────────────────────────────────────┐
│  ✓ 500+ Payloads              ✓ 15+ Bypass Techniques      │
│  ✓ WAF Detection              ✓ Multi-threaded             │
│  ✓ DNS Out-of-Band            ✓ CSRF Auto Handler          │
│  ✓ SQLi | XSS | RCE | LFI     ✓ SSTI | XXE | SSRF | JWT   │
│  ✓ HTML Report                ✓ JSON Output                │
└─────────────────────────────────────────────────────────────┘

```

## 🚀 QUICK START

bash
# Clone & Install
git clone https://github.com/b4ow/nuklier.git
cd nuklier
pip install requirements.txt

# Run
python nuklier.py http://target.com/page.php?id=1
```

📖 USAGE

bash
# Basic
python nuklier.py http://target.com

# With options
python nuklier.py https://target.com --threads 50 --timeout 15 --cookie "session=abc"

# Proxy & DNS
python nuklier.py http://target.com --proxy http://127.0.0.1:8080 --dns your.domain.com
```

⚙️ OPTIONS

```
┌──────────────┬─────────────────────┬──────────────────────────┐
│ ARGUMENT     │ DEFAULT             │ DESCRIPTION              │
├──────────────┼─────────────────────┼──────────────────────────┤
│ target       │ -                   │ Target URL (required)    │
│ --threads    │ 30                  │ Concurrent threads       │
│ --timeout    │ 10                  │ Request timeout (sec)    │
│ --cookie     │ None                │ Session cookie           │
│ --proxy      │ None                │ Proxy URL                │
│ --dns        │ oast.b4ow.com       │ DNS callback domain      │
└──────────────┴─────────────────────┴──────────────────────────┘
```

💉 BYPASS TECHNIQUES

```
┌─────────────────────────────┬──────────┐
│ TECHNIQUE                   │ PAYLOADS │
├─────────────────────────────┼──────────┤
│ Double Encoding             │ 15       │
│ SQL Comments                │ 25       │
│ Case Mutation               │ 30       │
│ Chunked Transfer            │ 5        │
│ DNS Out-of-Band             │ 20       │
│ JSONP & CORS                │ 15       │
│ GraphQL Introspection       │ 10       │
│ JWT Alg None                │ 10       │
│ SSTI Chaining               │ 25       │
│ Header Injection            │ 15       │
│ RCE via Log Poisoning       │ 15       │
│ XXE via SVG                 │ 4        │
│ SSRF Bypass                 │ 20       │
│ Parameter Pollution         │ 15       │
│ TRACE Method                │ 2        │
├─────────────────────────────┼──────────┤
│ TOTAL                       │ 226+     │
└─────────────────────────────┴──────────┘
```

📁 OUTPUT

```
┌────────────────────────────────────┐
│ nuklier_report.html   # HTML report│
│ nuklier_[hash].json   # JSON data  │
│ partial_[hash].json   # Partial    │
└────────────────────────────────────┘
```

⚠️ DISCLAIMER

Use only for authorized security testing.
The author is not responsible for any misuse.

---

NUKLIER v6.0 | Death System | #WAFBypass

```
