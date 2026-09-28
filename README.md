# logwash

Opinionated log housekeeping tool with dry-run support

## Features

- Exit codes friendly for cron and CI
- Filter by age (--older-than) or size (--larger-than)
- Scan directories for log files by glob pattern
- Archive matched logs into a timestamped .tar.gz
- Dry-run mode shows what would happen, touches nothing

## Install

```bash
pip install -r requirements.txt
python -m logwash --help
```

## Examples

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Project structure

```text
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── roadmap.md
│   └── usage.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   └── errors.py
├── tests/
│   └── test_cli.py
├── .editorconfig
├── .gitattributes
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## Notes

- mostly stable, edge cases remain
