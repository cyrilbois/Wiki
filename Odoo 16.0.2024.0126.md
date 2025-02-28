---
tags:
  - Asset
---

# Odoo 16.0.2024.0126

```bash
ODOO_REVISION=16.0.2024.0126

# Checkout odoo repo
cd odoo && git checkout 41ca2fcf0449e9b30075808734984b032cb70901

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout e99f71d4a6d5da2e368367d8ca695013e5d3852d

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout 4cdd1db20c021ebd369b46c739591def9732eec5

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
DIGEST=odoo@sha256:7f6185af13681be1acafe491510e48584ac51a2bbda0cd322196b02ba4da6bf9
docker pull "$DIGEST"
IMAGE_ID=$(docker image inspect "$DIGEST" --format "{{ .ID }}")

# Tag the docker image
docker tag ${IMAGE_ID:7:12} odoo:$ODOO_REVISION
```
