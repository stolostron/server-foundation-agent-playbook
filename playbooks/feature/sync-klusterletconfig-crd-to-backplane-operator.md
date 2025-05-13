---
description: Sync the latest KlusterletConfig CRD to the Backplane Operator
example: "egent_start: sync klusterletconfig crd to backplane operator"
dependencies:
  - knowledge/tools/git.md
---

## Steps

1. Got latest klusterletconfig crd from the url path: `https://raw.githubusercontent.com/stolostron/cluster-lifecycle-api/refs/heads/main/klusterletconfig/v1alpha1/config.open-cluster-management.io_klusterletconfigs.crd.yaml`, store it as a temp file -- `/tmp/klusterletconfig-crd.yaml`.
2. Check if backplane-operator repo exists.
3. If not, clone the repo from `https://github.com/<current-github-user>/backplane-operator.git`; If repo is not forked from `stolostron`, please fork it first.
4. Go to the `backplane-operator` repo, checkout to the `main` branch. If there are any uncommitted changes, stash them. Create a new branch named `sync-klusterletconfig-crd`. If branch already exists, please delete it first.
5. Replace the `pkg/templates/crds/foundation/config.open-cluster-management.io_klusterletconfigs_crd.yaml` with the temp file `/tmp/klusterletconfig-crd.yaml`.
6. Commit the changes and push to the new branch. And return the quick PR create link: https://github.com/<current-github-user>/backplane-operator/pull/new/sync-klusterletconfig-crd
