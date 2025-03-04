---
tags:
  - Asset
---

# Odoo 16.0.2023.1106

```bash
ODOO_REVISION=16.0.2023.1106

# Checkout odoo repo
cd odoo && git checkout 68dfda1f2957e82a3ae3af68b789b7fe5a3a8a3f

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout b1abcb7a5b075ccbb1409a5fb19c6b142bc6cf77

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout 36b6625bc4ecd53e3f1835a930f5af05d9d13e44

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