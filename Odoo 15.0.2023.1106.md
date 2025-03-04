---
tags:
- Asset
---
# Odoo 15.0.2023.1106

```bash
ODOO_REVISION=15.0.2023.1106

# Checkout odoo repo
cd odoo && git checkout ef340a9dea7c73d14a01ec5f567ccf2df7e56ff3

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout e54db62b241a6ad2aedf8c332d7ca9bf9d8fcdb1

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout 1f023fe70e4bf35600300f178fb25e2cae7bfa34

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
DIGEST=odoo@sha256:ed3a88ca1f9bb776bfde513bfdedfbbaedc6959abb48ea489d4ff1348acbf74b
docker pull "$DIGEST"
IMAGE_ID=$(docker image inspect "$DIGEST" --format "{{ .ID }}")

# Tag the docker image
docker tag ${IMAGE_ID:7:12} odoo:$ODOO_REVISION
```
