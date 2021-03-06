---
date: 2019-10-09
linktitle: "Uninstalling"
title: Uninstalling SchemaHero
weight: 3
---

If you want to uninstall SchemaHero from your cluster, the easiest method is to use the `[install](/cli/install/)` command to generate the YAML and pass that to `kubectl delete`:

```shell
kubectl schemahero install --yaml | kubectl delete -f -
```

## Manually Uninstalling

To manually uninstall SchemaHero:

First, delete the CRDs:

```shell
kubectl delete crd databases.databases.schemahero.io
kubectl delete crd tables.schemas.schemahero.io
kubectl delete crd migrations.schemas.schemahero.io
```

Finally, delete the SchemaHero namespace:

```shell
kubectl delete ns schemahero-system
```
