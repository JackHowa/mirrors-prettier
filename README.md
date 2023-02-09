prettier mirror
===============

Mirror of prettier package for pre-commit.

For pre-commit: see https://github.com/pre-commit/pre-commit

For prettier: see https://github.com/prettier/prettier


### Using prettier with pre-commit

Add this to your `.pre-commit-config.yaml`:

```yaml
-   repo: https://github.com/pre-commit/mirrors-prettier
    rev: ''  # Use the sha / tag you want to point at
    hooks:
    -   id: prettier
```

*note*: only prettier versions >= 2.1.0 are supported. Prettier versions < 2.7.1 and > v3.0.0-alpha.0 are supported via the following configuration if you want `2.8.0`:

```yaml
 - repo: https://github.com/pre-commit/mirrors-prettier
    rev: "v2.7.1"
    hooks:
      - id: prettier
        files: '\.(jsx?|tsx?|css)$'
        additional_dependencies:
          - prettier@2.8.0
```


When using plugins with `prettier` you'll need to declare them under
`additional_dependencies`. For example:

```yaml
-   repo: https://github.com/pre-commit/mirrors-prettier
    rev: ''  # Use the sha / tag you want to point at
    hooks:
    -   id: prettier
        additional_dependencies:
        -   prettier@2.1.2
        -   '@prettier/plugin-xml@0.12.0'
```

By default, all files are passed to `prettier`, if you want to limit the
file list, adjust `types` / `types_or` / `files`:

```yaml
    -   id: prettier
        types_or: [css, javascript]
```
