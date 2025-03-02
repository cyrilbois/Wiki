---
tags:
  - Asset
---

# Odoo 16.0.2023.0904

Revision: 16.0.2023.0904

```bash
ODOO_REVISION=16.0.2023.0904

# Checkout odoo repo
cd odoo && git checkout 6cf3b617d8082df5820283d07e6623b7684cefdd

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout 359009dc36635669d6760e2a8ddda08d90a1c643

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout 598fcffbae57c0eab422db669e75f52dd5c267e4

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
DIGEST=odoo@sha256:5f4f87d99eb68f6487dfccfc59ea130378dcdd7d52b42e8f6f00031db09ab037
docker pull "$DIGEST"
IMAGE_ID=$(docker image inspect "$DIGEST" --format "{{ .ID }}")

# Tag the docker image
docker tag ${IMAGE_ID:7:12} odoo:$ODOO_REVISION
```