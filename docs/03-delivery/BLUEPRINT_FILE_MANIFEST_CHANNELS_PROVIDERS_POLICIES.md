# Blueprint Manifest Disposition — Channels Providers Policies

This appendix is part of `BLUEPRINT_FILE_MANIFEST_DISPOSITION.md`. It is a source-reconciliation record, not file-creation authority.

| ID | Original path | Disposition | Repository home or target | Phase | Rule |
|---|---|---|---|---:|---|
| `FILE-CHANNEL-008` | `channels/facebook.yaml` | Defer | future channel descriptors behind Connector Gateway (facebook) | 4+ | Authenticated/high-risk channel requires separate policy, legal, and security approval. |
| `FILE-CHANNEL-003` | `channels/github.yaml` | Defer | future channel descriptors behind Connector Gateway (github) | 4 | Read-only initial channel. |
| `FILE-CHANNEL-009` | `channels/instagram.yaml` | Defer | future channel descriptors behind Connector Gateway (instagram) | 4+ | Authenticated/high-risk channel requires separate policy, legal, and security approval. |
| `FILE-CHANNEL-007` | `channels/linkedin.yaml` | Defer | future channel descriptors behind Connector Gateway (linkedin) | 4+ | Authenticated/high-risk channel requires separate policy, legal, and security approval. |
| `FILE-CHANNEL-006` | `channels/reddit.yaml` | Defer | future channel descriptors behind Connector Gateway (reddit) | 4+ | Authenticated/high-risk channel requires separate policy, legal, and security approval. |
| `FILE-CHANNEL-000` | `channels/registry.yaml` | Defer | future channel descriptors behind Connector Gateway (registry) | 4 | Read-only initial channel. |
| `FILE-CHANNEL-004` | `channels/rss.yaml` | Defer | future channel descriptors behind Connector Gateway (rss) | 4 | Read-only initial channel. |
| `FILE-CHANNEL-001` | `channels/web.yaml` | Defer | future channel descriptors behind Connector Gateway (web) | 4 | Read-only initial channel. |
| `FILE-CHANNEL-005` | `channels/x.yaml` | Defer | future channel descriptors behind Connector Gateway (x) | 4+ | Authenticated/high-risk channel requires separate policy, legal, and security approval. |
| `FILE-CHANNEL-002` | `channels/youtube.yaml` | Defer | future channel descriptors behind Connector Gateway (youtube) | 4 | Read-only initial channel. |
| `FILE-POL-006` | `policies/authenticated-channels.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 4+ | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-001` | `policies/browser-actions.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 6 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-005` | `policies/data-acquisition.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 4 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-003` | `policies/evidence-retention.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 1–2 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-011` | `policies/measurement.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 7 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-007` | `policies/provider-installation.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 4 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-000` | `policies/registry.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 2 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-009` | `policies/research-publishing-separation.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 4–6 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-004` | `policies/secrets-and-redaction.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 1–2 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-002` | `policies/social-publishing.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 6 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-008` | `policies/source-provenance.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 4 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-POL-010` | `policies/source-retention.yaml` | Adapt/defer | accepted policy contract and security/architecture documentation | 4 | Policies become enforceable only with owner, scope, tests, and runtime enforcement path. |
| `FILE-PROVIDER-001` | `providers/agent-reach.yaml` | Adapt/defer | future connector/provider descriptor and implementation | 4 | Optional replaceable acquisition provider. |
| `FILE-PROVIDER-004` | `providers/browser-session.yaml` | Adapt/defer | future connector/provider descriptor and implementation | 4+/6 | Provider-native behavior must remain inside connector implementation. |
| `FILE-PROVIDER-005` | `providers/cli-mcp.yaml` | Adapt/defer | future connector/provider descriptor and implementation | 4 | Provider-native behavior must remain inside connector implementation. |
| `FILE-PROVIDER-002` | `providers/direct-web.yaml` | Adapt/defer | future connector/provider descriptor and implementation | 4 | Provider-native behavior must remain inside connector implementation. |
| `FILE-PROVIDER-003` | `providers/official-api.yaml` | Adapt/defer | future connector/provider descriptor and implementation | 4 | Provider-native behavior must remain inside connector implementation. |
| `FILE-PROVIDER-000` | `providers/registry.yaml` | Adapt/defer | future connector/provider descriptor and implementation | 4 | Provider-native behavior must remain inside connector implementation. |

**Record count:** 28
