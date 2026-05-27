# Coding Standards

Only the following rules are approved for this skill right now. Do not add or
enforce unrelated coding standards until they are explicitly requested.

## Java Locale-Sensitive Operations

- When converting Java strings with `toLowerCase` or `toUpperCase`, always pass
  an explicit locale.
- Use `Locale.ROOT` for locale-independent identifiers, protocol values, keys,
  file names, and normalization.
- Use `Locale.ENGLISH` only when the transformation is intentionally
  English-language behavior.
- Do not use no-argument `String#toLowerCase()` or `String#toUpperCase()` in
  production code. These methods depend on the process default locale and can
  change results for locales such as Turkish.
- When formatting numbers that must render with Western digits, pass
  `Locale.ROOT` or `Locale.ENGLISH` explicitly to APIs such as `String.format`,
  `Formatter`, `NumberFormat`, and `DecimalFormatSymbols`.
- Do not rely on the JVM default locale for stable machine-readable output.

## Java Imports

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
