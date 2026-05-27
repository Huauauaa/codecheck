# Review Checklist

Only check for the approved Java rules right now.

- Java string case conversion uses explicit `Locale.ROOT` or `Locale.ENGLISH`.
- Java code does not use no-argument `String#toLowerCase()` or
  `String#toUpperCase()` in production code.
- Java number formatting that must render Western digits passes explicit
  `Locale.ROOT` or `Locale.ENGLISH`.
- Java code does not rely on the JVM default locale for stable
  machine-readable output.
- Java files do not import unused types.
