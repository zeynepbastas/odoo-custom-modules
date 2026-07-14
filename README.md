# Fault Log

A small custom Odoo 19.0 module for logging equipment/machine faults — built as a learning exercise, inspired by a client's need to track recurring machine faults by product and severity.

## Features

- Log faults with a title, related product/machine, severity, description, and report date
- Track each fault through a simple workflow: **New → Investigating → Resolved**
- List and form views, with its own top-level menu

## Model: `fault.log`

| Field           | Type       | Notes                                   |
|-----------------|------------|------------------------------------------|
| `name`          | Char       | Required. Short fault title              |
| `product_id`    | Many2one   | `product.product` — machine/product      |
| `severity`      | Selection  | Low / Medium / High                      |
| `description`   | Text       |                                           |
| `date_reported` | Date       | Defaults to today                        |
| `state`         | Selection  | New / Investigating / Resolved           |

## Requirements

- Odoo 19.0
- Depends on the core `product` module

## Installation

Clone this repo alongside your Odoo source and point `--addons-path` at it:

```bash
python odoo-bin \
  --addons-path=/path/to/odoo/addons,/path/to/this/repo \
  -d your_database \
  -i fault_log
```

Or, once running, install it from **Apps** in the UI (remove the default filter, search "Fault Log").

## License

LGPL-3
