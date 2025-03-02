---
tags:
  - Asset
---

# Odoo 17.0.2024.0104


```bash
ODOO_REVISION=17.0.2024.0104

# Checkout odoo repo
cd odoo && git checkout c96760a76b89894acda592a33b366cb74aa51588

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout enterprise repo
cd enterprise && git checkout 6b8c8ecacf3496e4c45dcf58ff02d10f24084337

# Create tag on the enterprise repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Checkout theme repo
cd themes && git checkout 7b2782875514e055a8db285fc1d46ec2d3225f70

# Create tag on the odoo repo
git tag -a $ODOO_REVISION -m "$ODOO_REVISION"
..

# Pull docker image
DIGEST=odoo@sha256:cb62da0aaea917a6ef53e457e4b4113da46b60fc95d06e72f946d75f1f1eaaad
docker pull "$DIGEST"
IMAGE_ID=$(docker image inspect "$DIGEST" --format "{{ .ID }}")

# Tag the docker image
docker tag ${IMAGE_ID:7:12} odoo:$ODOO_REVISION
```