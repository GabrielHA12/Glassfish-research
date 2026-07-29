# GlassFish Security Research

Vulnerability research on the Eclipse GlassFish administration console.

| CVE | Issue | Severity | Status |
|---|---|---|---|
| [CVE-2026-2586](https://nvd.nist.gov/vuln/detail/CVE-2026-2586) | EL injection → RCE | 9.1 Critical | Fixed in 8.0.2 |
| — | — | — | Pending disclosure |

---

## CVE-2026-2586 — EL Injection to RCE

**Affected:** < 8.0.2 · **CWE-917** · Authenticated RCE

The `alertSummary` and `alertDetail` parameters exist to render a status
message after saving a configuration. Their values were passed back through
the server-side Expression Language engine before rendering, letting an
authenticated console user reach Java classes through Reflection and execute
OS commands as the GlassFish process.
