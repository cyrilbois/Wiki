---
tags:
- Asset
---
# Odoo 15.0.2024.0104

```bash
ODOO_REVISION=15.0.2024.0104

# Checkout odoo repo
cd odoo && git checkout 8a18b82a29b73af03b1132d715dd320baa59f9c6

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout e69b23155813ecf7ce416215cf160b04f33f4d0f 

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout 97b0d12cda45f7dba2b7316b4ae24fdc37902d6f

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
DIGEST=odoo@sha256:24d7463086e88729f4a978e622cb483048609d236ace6e2ee7e8feea31e27dbb
docker pull "$DIGEST"
IMAGE_ID=$(docker image inspect "$DIGEST" --format "{{ .ID }}")

# Tag the docker image
docker tag ${IMAGE_ID:7:12} odoo:$ODOO_REVISION
```
