# Bolt's Journal - Critical Learnings

## 2026-03-05 - Duplicate Filter Rules in Adblock Lists
**Learning:** Adblock filter lists are parsed line-by-line during client extension startup. Duplicate domain rules like `||taboola.com^` or `||sentry.io^` increase list download payload and memory allocation without adding blocking value.
**Action:** Deduplicate rules while maintaining category structure to ensure maximum parsing efficiency and minimal payload size.

## 2026-09-11 - Redundant Subdomain Rules in Adblock Lists
**Learning:** In standard adblock filter list syntax, domain blocking rules using `||domain^` block the specified domain and all of its subdomains automatically. Including rules for specific subdomains (e.g. `||connect.facebook.net^`) when a parent domain rule (e.g. `||facebook.net^`) is already present adds unnecessary rule count and memory overhead during extension parsing without changing blocking scope.
**Action:** Remove redundant subdomain filter rules when parent or apex domain blocking rules are present.
