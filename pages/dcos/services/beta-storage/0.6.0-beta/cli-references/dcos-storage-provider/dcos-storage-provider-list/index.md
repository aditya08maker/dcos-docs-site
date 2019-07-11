---
layout: layout.pug
navigationTitle: dcos storage provider list
title: dcos storage provider list
menuWeight: 0
notes: Code generated by docgen.go, DO NOT EDIT
enterprise: true
beta: true
origin: github.com/mesosphere/dcos-storage/cli/pkg/cmd/cmd_provider_list.go
excerpt: List existing volume providers.
---
#include /dcos/services/include/beta-software-warning.tmpl

## dcos storage provider list

List existing volume providers.

### Synopsis

Arguments:

    <providers> A space-separated list of providers. This argument is optional.
                If it is not provided all providers will be listed.

List existing volume providers.

```bash
dcos storage provider list [<providers>] [flags]
```

### Examples

1. Create two volume providers then list them:

```bash
$ cat <<EOF | dcos storage provider create
{
    "name": "ssds",
    "spec": {
        "plugin": {
            "name": "lvm",
            "config-version": "latest"
        },
        "node": "c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S2",
        "plugin-configuration": {
            "devices": ["xvdb", "xvdc"]
        },
        "labels": {"rotational": "false"}
    }
}
EOF

$ cat <<EOF | dcos storage provider create
{
    "name": "spinning-rust",
    "spec": {
        "plugin": {
            "name": "lvm",
            "config-version": "latest"
        },
        "node": "c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S1",
        "plugin-configuration": {
            "devices": ["xvde", "xvdf"]
        },
        "labels": {"rotational": "true"}
    }
}
EOF

$ dcos storage provider list
PLUGIN  NAME           NODE                                     STATE
lvm     ssds           c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S2  ONLINE
lvm     spinning-rust  c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S1  ONLINE

$ dcos storage provider list --json
{
    "providers": [
        {
            "name": "ssds",
            "spec": {
                "plugin": {
                    "name": "lvm",
                    "config-version": 1
                },
                "node": "c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S2",
                "plugin-configuration": {
                    "devices": [
                        "xvdb",
                        "xvdc"
                    ]
                },
                "labels": {
                    "rotational": "false"
                }
            },
            "status": {
                "state": "ONLINE",
                "nodes": [
                    "c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S2"
                ],
                "last-changed": "0001-01-01T00:00:00Z",
                "last-updated": "0001-01-01T00:00:00Z",
                "asset-id": "dfgj9sdfg7s9dfg"
            }
        },
        {
            "name": "spinning-rust",
            "spec": {
                "plugin": {
                    "name": "lvm",
                    "config-version": 1
                },
                "node": "c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S1",
                "plugin-configuration": {
                    "devices": [
                        "xvde",
                        "xvdf"
                    ]
                },
                "labels": {
                    "rotational": "true"
                }
            },
            "status": {
                "state": "ONLINE",
                "nodes": [
                    "c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S1"
                ],
                "last-changed": "0001-01-01T00:00:00Z",
                "last-updated": "0001-01-01T00:00:00Z",
                "asset-id": "lkjsdoguosd9g8"
            }
        }
    ]
}

$ dcos storage provider list ssds --json
{
    "providers": [
        {
            "name": "ssds",
            "spec": {
                "plugin": {
                    "name": "lvm",
                    "config-version": 1
                },
                "node": "c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S2",
                "plugin-configuration": {
                    "devices": [
                        "xvdb",
                        "xvdc"
                    ]
                },
                "labels": {
                    "rotational": "false"
                }
            },
            "status": {
                "state": "ONLINE",
                "nodes": [
                    "c67efa5d-34fa-4bc5-8b21-2a5e0bd52385-S2"
                ],
                "last-changed": "0001-01-01T00:00:00Z",
                "last-updated": "0001-01-01T00:00:00Z",
                "asset-id": "dfgj9sdfg7s9dfg"
            }
        }
    ]
}
```

### Options

Name | Description
--- | ---
`--all` | Display removed providers.
`--json` | Display the list of volume providers in json format.
`--node` string | Only show local volume providers on node.
`--plugin` string | Only show providers of the specified plugin.

### Options inherited from parent commands

Name | Description
--- | ---
`-h`,`--help` | Help for this command.
`--timeout` duration | Override the default request timeout. (default 55s)
