---
name: code-standards
description: Enforces the Java Locale rule for string case conversion and Western-digit number formatting. Use when writing or reviewing Java code that calls String.toLowerCase, String.toUpperCase, String.format, Formatter, NumberFormat, or DecimalFormatSymbols.
---

# Code Standards

This skill currently contains only the Java Locale rule requested by the
repository owner. Do not infer or add unrelated coding standards.

## Java Locale Rule

- In Java, calls to `String#toLowerCase` and `String#toUpperCase` must pass an
  explicit locale.
- Use `Locale.ROOT` for locale-independent identifiers, protocol values, keys,
  file names, and normalization.
- Use `Locale.ENGLISH` only when the transformation is intentionally
  English-language behavior.
- Do not use no-argument `String#toLowerCase()` or `String#toUpperCase()` in
  production code.
- When formatting numbers that must render with Western digits, pass
  `Locale.ROOT` or `Locale.ENGLISH` explicitly to APIs such as `String.format`,
  `Formatter`, `NumberFormat`, and `DecimalFormatSymbols`.
- Do not rely on the JVM default locale for stable machine-readable output.

## Examples

```java
String key = value.toLowerCase(Locale.ROOT);
String code = value.toUpperCase(Locale.ROOT);
String padded = String.format(Locale.ROOT, "%04d", count);
NumberFormat formatter = NumberFormat.getIntegerInstance(Locale.ROOT);
DecimalFormat decimal = new DecimalFormat(
    "0.00", DecimalFormatSymbols.getInstance(Locale.ROOT));
```

## References

Load these files when deeper guidance is needed:

- `references/coding-standards.md` for the full Java Locale rule.
- `references/review-checklist.md` for a focused review checklist.
