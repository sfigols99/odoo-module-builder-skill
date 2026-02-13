# Odoo Module Builder Skill

An AI agent skill for building complete Odoo modules (v16 and v17) with correct structure, conventions, and best practices.

## What It Does

- **Scaffold new modules** — generates a full Odoo addon with models, views, security, menus, and manifest via `scripts/scaffold_module.py`
- **Extend existing modules** — guides inheritance of models (`_inherit`) and views (`inherit_id`)
- **Version-aware** — handles Odoo 16 (`attrs=`) and Odoo 17 (`invisible="expr"`) differences automatically

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