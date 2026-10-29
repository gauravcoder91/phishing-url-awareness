# Test Results

Python version used: 3.12.3 | Operating system: Windows | Date: 29 Oct 2026

Name: Gaurav Kumar | Course: Cyber Security | Submission date: 31/10/2026

| # | Input | Expected result | Actual result | Pass/Fail |
|---|-------|-----------------|---------------|-----------|
| 1 | https://www.example.com/login | No listed warning signs | No listed warning signs found. This does NOT prove safety. | PASS |
| 2 | http://192.0.2.10/account | IP address + HTTP | Uses an IP address instead of a familiar domain. / Uses HTTP. HTTPS alone does not prove trust. | PASS |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | Contains an @ symbol; inspect carefully. / Uses HTTP. HTTPS alone does not prove trust. | PASS |
| 4 | https://a.b.c.d.e.example.invalid/path | Many hostname segments | Contains many hostname segments/subdomains. | PASS |
| 5 | https://xn--example.invalid/ | Punycode-style hostname | Contains a punycode-style hostname. | PASS |

## Bonus checks

| Input | Actual result |
|---|---|
| `(empty)` | No URL entered. |
| `www.example.com` | Uses HTTP. HTTPS alone does not prove trust. |
| `https://secure-login.example.invalid` | No listed warning signs found. This does NOT prove safety. |
| `http://[bad` | This text is not a valid URL format. |

## Notes

- Missing scheme (www.example.com) is treated as http://, so the HTTP warning appears.
- https://secure-login.example.invalid shows no warning, which proves that 'no signs' does NOT mean safe.
- http://[bad used to crash with ValueError; the try/except fix now handles it safely.
