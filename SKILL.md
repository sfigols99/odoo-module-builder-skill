---
name: odoo-module-builder
description: Build complete Odoo modules with models, views, security, wizards, reports, and controllers for Odoo 16 and 17. Use when users want to create a new Odoo module from scratch, add models or views to an existing module, extend/inherit existing Odoo models (res.partner, sale.order, etc.), scaffold an Odoo addon, or work with any Odoo module development task.
---

# Odoo Module Builder

Build and extend Odoo modules (v16 and v17) with correct structure, conventions, and best practices.

## Workflow

### Creating a New Module from Scratch

1. Determine the Odoo version (16 or 17, default to 17 if not specified)
2. Run the scaffold script to generate boilerplate:
   ```bash
   scripts/scaffold_module.py <module_name> --path <output_dir> [--odoo-version 17]
   ```
   Module name must be `snake_case`.
3. Customize the generated files — add models, fields, views per the user's requirements
4. Add security rules for every new model (ir.model.access.csv + groups)
5. Update `__manifest__.py` `data` list whenever adding new XML/CSV files

### Extending an Existing Module

1. Identify the target model(s) to inherit (e.g., `res.partner`, `sale.order`)
2. Use `_inherit` in a new Python file within the module's `models/` directory
3. Create inherited views using `inherit_id` with xpath or field-based positioning
4. Register the new files in `__init__.py` and `__manifest__.py`

## Version Differences (16 vs 17)

| Feature | Odoo 16 | Odoo 17 |
|---------|---------|---------|
| View visibility | `attrs="{'invisible': [(...)]}"` | `invisible="expr"` |
| View readonly | `attrs="{'readonly': [(...)]}"` | `readonly="expr"` |
| View required | `attrs="{'required': [(...)]}"` | `required="expr"` |
| create() decorator | `@api.model_create_multi` | `@api.model_create_multi` |
| Kanban templates | `<t t-name="kanban-box">` | `<t t-name="kanban-card">` |

## Reference Files

Load the appropriate reference file when working on a specific area:

- **Models & fields**: See [references/models.md](references/models.md) — field types, computed fields, constraints, inheritance, CRUD overrides, domains, mixins
- **Views (form, tree, kanban, search)**: See [references/views.md](references/views.md) — form structure, tree decorations, kanban templates, search filters, actions, menus, view inheritance
- **Security**: See [references/security.md](references/security.md) — groups, ir.model.access.csv, record rules, field-level access
- **Wizards**: See [references/wizards.md](references/wizards.md) — transient models, wizard views, launching wizards, multi-record operations
- **Reports (QWeb PDF/HTML)**: See [references/reports.md](references/reports.md) — report actions, QWeb templates, directives, paper format, custom report models
- **Controllers & Website**: See [references/controllers.md](references/controllers.md) — HTTP routes, JSON-RPC, website pages, portal pages
- **Data files**: See [references/data.md](references/data.md) — sequences, cron jobs, mail templates, server actions, demo/seed data, noupdate
- **Static assets**: See [references/static.md](references/static.md) — module icon, JS/CSS/XML assets, OWL components (v17), widget registration
- **Translations (i18n)**: See [references/i18n.md](references/i18n.md) — marking strings for translation, PO/POT files, `_()` usage
- **Tests**: See [references/tests.md](references/tests.md) — TransactionCase, access rights tests, Form simulation, HTTP tests, tour tests, tags
- **Hooks**: See [references/hooks.md](references/hooks.md) — post_init_hook, pre_init_hook, uninstall_hook, manifest registration
- **Demo data**: See [references/demo.md](references/demo.md) — demo records, relational data, CSV demo, demo vs data distinction
- **Manifest & structure**: See [references/manifest.md](references/manifest.md) — __manifest__.py fields, file load order, directory layout, __init__.py patterns

## Conventions

- Module directory name = technical name, `snake_case` (e.g., `library_management`)
- Model `_name` uses dots: `library.management`
- XML IDs: `view_{model}_form`, `action_{model}`, `menu_{model}_root`
- Security CSV IDs: `access_{model}_{group}`
- Version format: `ODOO_VERSION.MAJOR.MINOR.PATCH` (e.g., `17.0.1.0.0`)
- Every model must have access rights in `ir.model.access.csv`
- Always include `mail.thread` and `mail.activity.mixin` for business models that users interact with
- Load security files before views in `__manifest__.py` `data` list
