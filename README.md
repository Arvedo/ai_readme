# Setup Markdown Structure:
Contains guidelines for a stricter approach to AI usage in code contributions.

## Human Accountability in AI-Generated Code Contributions
This repository contains four sets of guidelines for contributors and maintainers regarding the use of AI in code contributions. The "minor" set enforces stricter limitations on AI usage, while the "major" set allows for more flexibility. Both sets emphasize the importance of human accountability and understanding when using AI tools in the development process.

## Strict No to AI-Generated Code Contributions
from https://github.com/ggml-org/llama.cpp/
This repository contains guidelines for a strict no-AI approach to code contributions, where AI tools are not allowed to generate any portion of the code. This does not mean that AI tools cannot be used at all, but rather that they should not be used for code generation or worse the whole development process.


## live_die_ralphete ONLY USE THIS IF YOU UNDERSTAND THE DANGER!
For testing multiple agents in the same workspace.

# AI disclosure
/docs/modules.md is AI generated with info drom from 
and https://github.com/ggml-org/llama.cpp/wiki/Modules
and
https://github.com/qoomon/git-conventional-commits

# AI Generated:

- `strict_no` ⛔ — Forbids AI use entirely. For critical, security-sensitive, or legally sensitive code where human authorship and provenance must be guaranteed.
- `human_accountability_minor` ⚠️ — Allows AI assistance for less than 50% of the contribution. The human must remain the primary author and reviewer.
- `human_accountability_major` ✅ — For quick-and-dirty work, proofs of concept, prototypes, etc. AI may do the heavy lifting, but a human must still disclose, review, and sign off.
- `live_die_ralphete` 🔥 — For Ralph-loops (autonomous agent loops). **Do not use this unless you fully understand the danger.** Intended for self-iterating AI agent workflows; misuse can cause **full data loss or worse**.

### Central TODOs for all folders:

#### `human_accountability_major/`
| File | Line | TODO |
|------|------|------|
| [AGENTS.md](human_accountability_major/AGENTS.md#L87) | 87 | Add more guidelines here |
| [CONTRIBUTING.md](human_accountability_major/CONTRIBUTING.md#L70) | 70 | Add the right guidelines here |
| [CONTRIBUTING.md](human_accountability_major/CONTRIBUTING.md#L74) | 74 | Add the right guidelines here |
| [CONTRIBUTING.md](human_accountability_major/CONTRIBUTING.md#L78) | 78 | Add the right guidelines here |
| [CONTRIBUTING.md](human_accountability_major/CONTRIBUTING.md#L103) | 103 | Add the right resources here |
| [docs/build.md](human_accountability_major/docs/build.md#L1) | 1 | Document how to build your project here |
| [docs/tests.md](human_accountability_major/docs/tests.md#L1) | 1 | Document how to test your project here |
| [docs/modules.md](human_accountability_major/docs/modules.md#L20) | 20 | You can add or remove scopes to match your project |

#### `human_accountability_minor/`
| File | Line | TODO |
|------|------|------|
| [AGENTS.md](human_accountability_minor/AGENTS.md#L84) | 84 | Add more guidelines here |
| [CONTRIBUTING.md](human_accountability_minor/CONTRIBUTING.md#L70) | 70 | Add the right guidelines here |
| [CONTRIBUTING.md](human_accountability_minor/CONTRIBUTING.md#L74) | 74 | Add the right guidelines here |
| [CONTRIBUTING.md](human_accountability_minor/CONTRIBUTING.md#L78) | 78 | Add the right guidelines here |
| [CONTRIBUTING.md](human_accountability_minor/CONTRIBUTING.md#L103) | 103 | Add the right resources here |
| [docs/build.md](human_accountability_minor/docs/build.md#L1) | 1 | Document how to build your project here |
| [docs/tests.md](human_accountability_minor/docs/tests.md#L1) | 1 | Document how to test your project here |
| [docs/modules.md](human_accountability_minor/docs/modules.md#L20) | 20 | You can add or remove scopes to match your project |

#### `strict_no/`
| File | Line | TODO |
|------|------|------|
| [CONTRIBUTING.md](strict_no/CONTRIBUTING.md#L70) | 70 | Add the right guidelines here |
| [CONTRIBUTING.md](strict_no/CONTRIBUTING.md#L74) | 74 | Add the right guidelines here |
| [CONTRIBUTING.md](strict_no/CONTRIBUTING.md#L78) | 78 | Add the right guidelines here |
| [CONTRIBUTING.md](strict_no/CONTRIBUTING.md#L103) | 103 | Add the right resources here |
| [docs/build.md](strict_no/docs/build.md#L1) | 1 | Document how to build your project here |
| [docs/tests.md](strict_no/docs/tests.md#L1) | 1 | Document how to test your project here |
| [docs/modules.md](strict_no/docs/modules.md#L20) | 20 | You can add or remove scopes to match your project |

#### `live_die_ralphete/`
| File | Line | TODO |
|------|------|------|
| [docs/build.md](live_die_ralphete/docs/build.md#L1) | 1 | Document how to build your project here |
| [docs/tests.md](live_die_ralphete/docs/tests.md#L1) | 1 | Document how to test your project here |
| [docs/modules.md](live_die_ralphete/docs/modules.md#L20) | 20 | You can add or remove scopes to match your project |
| [PERSISTANCE.md](live_die_ralphete/PERSISTANCE.md#L31) | 31 | (deferred TODO template — document reason for deferral) |

> **Note:** When a TODO is resolved, mark it done here and link the commit or PR. Do not rely on text-searching for `TODO` — keep this table up to date manually.
