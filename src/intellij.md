# IntelliJ IDEA

Search `eslint` at [Preference]

- Enable at [Languages & Frameworks] - [JavaScript] > [Code Quality Tools] > [ESLint]
- Apply each path using at `Node interpreter`, `ESLint package`
- To use `File Watcher`, search `File Watcher` at [Preference]

## Use Dart

`dartfmt` adopts the coding style defined in the following [Effective Dart Style](https://dart.dev/guides/language/effective-dart/style), and you set `dartfmt` in [Preferences] - [Editor] - [Cord Style] - [Dart]

Use [pedantic_mono](https://pub.dev/packages/pedantic_mono)

```yaml
dev_dependencies:
  pedantic_mono: any
```

Create `analysis_options.yaml` to root in a project, and add your rules if needed. You can confirm [Linter for Dart](https://dart-lang.github.io/linter/lints/)

```yaml
# Strict
include: package:pedantic_mono/analysis_options.yaml

# More loose
include: package:pedantic_mono/analysis_options_flutter_samples.yaml
```
