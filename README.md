# Odoo Module Builder Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An AI agent skill for building complete Odoo modules (v16 and v17) with correct structure, conventions, and best practices.

## What It Does

- **Scaffold new modules** — generates a full Odoo addon with models, views, security, menus, and manifest via `scripts/scaffold_module.py`
- **Extend existing modules** — guides inheritance of models (`_inherit`) and views (`inherit_id`)
- **Version-aware** — handles Odoo 16 (`attrs=`) and Odoo 17 (`invisible="expr"`) differences automatically
- **Comprehensive references** — 13 detailed reference guides covering all aspects of Odoo development

## Bundled Resources

### Script

| File | Description |
|------|-------------|
| `scripts/scaffold_module.py` | Generates a complete Odoo module directory with all boilerplate files |

### Reference Files

| File | Covers |
|------|--------|
| `references/models.md` | Field types, computed fields, constraints, inheritance, CRUD overrides, domains, mixins |
| `references/views.md` | Form, tree, kanban, search views, actions, menus, view inheritance |
| `references/security.md` | Groups, ir.model.access.csv, record rules, field-level access |
| `references/wizards.md` | TransientModel, wizard views, launching, multi-record operations |
| `references/reports.md` | QWeb reports, templates, directives, paper format, custom report models |
| `references/controllers.md` | HTTP routes, JSON-RPC, website pages, portal pages |
| `references/data.md` | Sequences, cron jobs, mail templates, server actions, noupdate |
| `references/demo.md` | Demo records, relational data, CSV demo, demo vs data distinction |
| `references/static.md` | Module icon, JS/CSS/XML assets, OWL components (v17), widget registration |
| `references/i18n.md` | Translation markers, PO/POT files, `_()` usage |
| `references/tests.md` | TransactionCase, access rights tests, Form simulation, HTTP/tour tests, tags |
| `references/hooks.md` | post_init_hook, pre_init_hook, uninstall_hook, manifest registration |
| `references/manifest.md` | `__manifest__.py` fields, file load order, directory layout, `__init__.py` patterns |

## Installation

Install the `.skill` file through your compatible editor or agent platform.

## Usage Examples

- "Create an Odoo module for managing library books"
- "Add a new model to my Odoo module for tracking loans"
- "Extend res.partner with a loyalty points field"
- "Scaffold an Odoo 16 addon called inventory_tracking"

## Quick Start

### Scaffolding a New Module

```bash
python3 scripts/scaffold_module.py library_management --path ./addons --odoo-version 17
```

This creates a complete Odoo module with:
- Model with common fields (name, state, company_id)
- Form, tree, and search views
- Security groups and access rights
- Menu structure
- Mail thread integration

### Using as an AI Skill

Install the `.skill` file in your compatible AI agent platform, then ask it to help you build Odoo modules. The skill provides context-aware guidance using the bundled reference documentation.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to contribute to this project.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for a list of changes in each version.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.