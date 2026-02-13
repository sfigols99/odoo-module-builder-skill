# Odoo Module Manifest Reference

## `__manifest__.py` Structure

```python
{
    'name': 'Library Management',
    'version': '17.0.1.0.0',
    'category': 'Services',
    'summary': 'Manage library books, members, and loans',
    'description': """
        Library Management System
        =========================
        Features:
        - Book catalog management
        - Member registration
        - Loan tracking
    """,
    'author': 'Your Company',
    'website': 'https://www.example.com',
    'license': 'LGPL-3',
    'depends': [
        'base',
        'mail',
    ],
    'data': [
        # Security (load first)
        'security/security.xml',
        'security/ir.model.access.csv',
        # Wizards
        'wizards/book_return_wizard_views.xml',
        # Views
        'views/library_book_views.xml',
        'views/library_book_category_views.xml',
        'views/menu.xml',
        # Reports
        'reports/library_book_report.xml',
        'reports/library_book_report_template.xml',
        # Data
        'data/sequence_data.xml',
        'data/demo_data.xml',
    ],
    'demo': [
        'data/demo_data.xml',
    ],
    'assets': {
        'web.assets_backend': [
            'library_management/static/src/css/library.css',
            'library_management/static/src/js/library_widget.js',
        ],
    },
    'installable': True,
    'application': True,
    'auto_install': False,
}
```

## Field Reference

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Human-readable module name |
| `version` | Yes | `ODOO_VERSION.MODULE_VERSION` (e.g., `17.0.1.0.0`) |
| `depends` | Yes | List of module dependencies; minimum `['base']` |
| `data` | Yes | List of data files (XML, CSV) loaded on install/upgrade |
| `license` | Yes | License identifier (e.g., `LGPL-3`, `OPL-1`) |
| `category` | No | Module category for grouping in Apps |
| `summary` | No | Short one-line description |
| `description` | No | Long description (RST or plain text) |
| `author` | No | Author name |
| `website` | No | Author website |
| `demo` | No | Demo data files (loaded only in demo mode) |
| `assets` | No | Static web assets (JS, CSS, XML templates) |
| `installable` | No | Whether module can be installed (default `True`) |
| `application` | No | Show in Apps menu (default `False`) |
| `auto_install` | No | Auto-install when all dependencies are met |
| `external_dependencies` | No | System/Python dependencies: `{'python': ['xlrd'], 'bin': ['wkhtmltopdf']}` |

## Version Convention

Format: `ODOO_VERSION.MAJOR.MINOR.PATCH`

- Odoo 17: `17.0.1.0.0`
- Odoo 16: `16.0.1.0.0`

## Data File Load Order

Files in `data` are loaded in the order listed. Load order matters:

1. **Security groups** (`security/security.xml`) — Define groups first
2. **Access rights** (`security/ir.model.access.csv`) — Reference groups
3. **Views and wizards** — Reference models and groups
4. **Reports** — Reference models and views
5. **Demo/seed data** — Reference everything above

## Module Directory Structure

```
library_management/
├── __init__.py
├── __manifest__.py
├── controllers/
│   ├── __init__.py
│   └── main.py
├── data/
│   ├── sequence_data.xml
│   └── demo_data.xml
├── models/
│   ├── __init__.py
│   ├── library_book.py
│   └── library_book_category.py
├── reports/
│   ├── library_book_report.xml
│   └── library_book_report_template.xml
├── security/
│   ├── ir.model.access.csv
│   └── security.xml
├── static/
│   └── description/
│       └── icon.png
├── views/
│   ├── library_book_views.xml
│   ├── library_book_category_views.xml
│   └── menu.xml
└── wizards/
    ├── __init__.py
    ├── book_return_wizard.py
    └── book_return_wizard_views.xml
```

### `__init__.py` Files

Root `__init__.py`:
```python
from . import models
from . import controllers
from . import wizards
```

`models/__init__.py`:
```python
from . import library_book
from . import library_book_category
```

Each Python file with models must be imported in the corresponding `__init__.py`.
