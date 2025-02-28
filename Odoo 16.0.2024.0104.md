---
tags:
  - Asset
---

# Odoo 16.0.2024.0104

```bash
ODOO_REVISION=16.0.2024.0104

# Checkout odoo repo
cd odoo && git checkout 57d6be02a3516f117477fc2ee1fb3c165c462e7f

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout 5eea906527ed07b54be08461bea59481702798ef

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout db3dde66ffa2e8ff889903540138799858994899

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
DIGEST=odoo@sha256:9b0eae5f92d511274b0f770bb01e09af24dec4a8316300e01a74411ecf5a6ffd
docker pull "$DIGEST"
IMAGE_ID=$(docker image inspect "$DIGEST" --format "{{ .ID }}")

# Tag the docker image
docker tag ${IMAGE_ID:7:12} odoo:$ODOO_REVISION
```