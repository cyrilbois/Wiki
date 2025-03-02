---
tags:
- Asset
---

# Odoo 16.0.2023.0227

```bash
ODOO_REVISION=16.0.2023.0227

# Checkout odoo repo
cd odoo && git checkout 08cf96d9ba169287a7e8d7dece4ac0110fa01742

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout e9b2ea5c27382f58564f991af501e6a52c6a5193

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout 2d7c8ba5add9e00a9f9b9098ba2fa2a133cd2fb6

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
docker pull odoo@sha256:971c643000e012ad8aca71ab2d903f527bdcb13a23a2c5f1c4d9e5a6a4c3367a

# Tag the docker image
docker tag e4d47774edee odoo:$ODOO_REVISION
```

## Issues

### Liste in form overflow

List f.g. sale order lines in the sale order form overflows the window.

### Cannot edit tax on vendor invoice

When editing the tax field on total section of an vendor invoice a client error is thrown.