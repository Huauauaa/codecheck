---
name: code-standards
description: Enforces approved Java code standards. Use when writing or reviewing Java code that calls String.toLowerCase, String.toUpperCase, String.format, Formatter, NumberFormat, or DecimalFormatSymbols, or when checking Java imports.
---

# Code Standards

This skill contains only the Java rules requested by the repository owner. Do
not infer or add unrelated coding standards.

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

## Java Import Rule

- Do not import Java types that are not used in the file.
- Remove unused type imports instead of leaving them for future use.

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

- `references/coding-standards.md` for the full approved Java rules.
- `references/review-checklist.md` for a focused review checklist.
