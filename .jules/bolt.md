# Bolt's Journal - Critical Learnings

## 2026-03-05 - Duplicate Filter Rules in Adblock Lists
**Learning:** Adblock filter lists are parsed line-by-line during client extension startup. Duplicate domain rules like `||taboola.com^` or `||sentry.io^` increase list download payload and memory allocation without adding blocking value.
**Action:** Deduplicate rules while maintaining category structure to ensure maximum parsing efficiency and minimal payload size.
