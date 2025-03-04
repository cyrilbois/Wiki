---
tags:
  - Asset
---
# Odoo 17.0.2023.1120


```bash
ODOO_REVISION=17.0.2023.1120

# Checkout odoo repo
cd odoo && git checkout adee7487d9a99217c978d698332671d54a36e039

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout f5b91a7edc19d91a1a7ec9b9b63e8a315aa82a3f

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout bea0f57ca4716dd2fafc2d3e3c0a328b0c6f2351

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
DIGEST=odoo@sha256:9f57fa8946d9301694a786aa4bd0f4ecc934118e82ea410bd082348e1dc42d5e
docker pull "$DIGEST"
IMAGE_ID=$(docker image inspect "$DIGEST" --format "{{ .ID }}")

# Tag the docker image
docker tag ${IMAGE_ID:7:12} odoo:$ODOO_REVISION
```