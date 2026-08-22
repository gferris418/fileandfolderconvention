# Generic Provider Mapping Contract

```text
EIOS Canonical Information Object
        |
        +--> informationScope + businessContext
        +--> classification / policy / relationships
        +--> RepositoryBinding
                    |
                    v
             EIOS Repository
                    |
                    v
          Provider-native repository
                    |
                    v
       Human-facing logical projection
                    |
                    v
            Native content objects
```

A provider mapping is conformant when users can navigate the intended logical structure while EIOS canonical identity, metadata, policy, authorization, lifecycle, repository bindings, and audit evidence remain authoritative.

## Required mapping record

For each mapped logical root, record at minimum:

```text
logicalSpace
eiosInformationScope
nativeRepositoryConstruct
nativeRootIdentifier
repositoryBindingRole
writeMode
metadataMapping
permissionMapping
retentionCapability
legalHoldCapability
immutabilityCapability
dataResidencyCapability
syncMechanism
knownLimitations
compensatingControls
```

## Non-file objects

The provider profile must state how it handles canonical messages, datasets, records, media, and packages when they are not naturally represented as files/folders. It may use links, views, search projections, virtual collections, or no folder projection at all.

## No inference rule

Neither a provider path nor a folder label is sufficient evidence of authoritative binding role, lifecycle state, record declaration, legal hold, retention status, permission scope, or synchronization state.
