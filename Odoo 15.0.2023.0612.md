---
tags:
- Asset
---
# Odoo 15.0.2023.0612

```bash
ODOO_REVISION=15.0.2023.0612

# Checkout odoo repo
cd odoo && git checkout a44cc01c6745507aaed4fb0168ec4e4fc2df3dbd

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout a874f22e66bc60e3f5bb6e9cd1fc13aa5289ba12

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout 56a04f327bbdc611e24699a29c9c09e5421a80fd

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
docker pull odoo@sha256:0bb78119fde699e29d8ac4497bd929dadc5de4453b8ca0dd63aaaa9ea5c1234a

# Tag the docker image
docker tag 1635437d8309 odoo:$ODOO_REVISION
```
