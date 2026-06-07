# Opencode with Free Nemotron 3 Super Setup

Minimal guide to configure Opencode to use free Nemotron 3 Super models.

For scripts setup reference, see the [NVIDIA Nemotron 3 example](https://github.com/j3soon/local-llm-notes/blob/main/examples/basic-secure-api/README.md#nvidia-nemotron-3).

## Installation

You can [install Opencode](https://opencode.ai/docs/#install) using the following command:

```bash
curl -fsSL https://opencode.ai/install | bash
```

or

```bash
npm install -g opencode-ai
```

## Option 1: Default Opencode Built-in Nemotron
Opencode includes free Nemotron 3 Super by default. Note that this option may train on your data to improve the service. See Opencode's [privacy policy](https://opencode.ai/docs/zen/#privacy) for details.

## Option 2: Use Open Router
Configure Opencode to use free Nemotron 3 Super through Open Router, which to the best of my knowledge does not train on your data. Refer to the [NVIDIA Nemotron documentation](https://docs.nvidia.com/nemotron/latest/usage-cookbook/Nemotron-3-Super/OpenScaffoldingResources/README.html).

## Option 3: Use build.nvidia.com
Configure Opencode to use free Nemotron 3 Super via NVIDIA's build service, which to the best of my knowledge does not train on your data. Learn more in the [NVIDIA blog introducing Nemotron 3 Super](https://developer.nvidia.com/blog/introducing-nemotron-3-super-an-open-hybrid-mamba-transformer-moe-for-agentic-reasoning/#see_it_in_action).

## Self-hosting (For Large GPUs)
If you have sufficient GPU resources (DGX Spark or RTX PRO 6000), you can self-host Nemotron 3 Super:

1. NVIDIA NeMo VLLM Cookbook: [GitHub link](https://github.com/NVIDIA-NeMo/Nemotron/blob/main/usage-cookbook/Nemotron-3-Super/vllm_cookbook.ipynb)
2. NVIDIA Spark Deployment Guide: [Official guide](https://docs.nvidia.com/nemotron/nightly/usage-cookbook/Nemotron-3-Super/SparkDeploymentGuide/README.html)
3. Unsloth Documentation (with llama.cpp): [Unsloth Nemotron 3 Super](https://unsloth.ai/docs/models/nemotron-3/nemotron-3-super)

After setting up the self-hosted endpoint, configure Opencode to point to your local server.

## Permissions
Opencode allows all [tools](https://opencode.ai/docs/tools/) to run without explicit permission prompts by default. This is similar to running Codex with `codex --yolo` or Claude Code with `claude --dangerously-skip-permissions`, so it is convenient but risky.

For sensitive codebases, consider running Opencode in Docker or configuring [permissions](https://opencode.ai/docs/permissions/) to restrict tool access.

## Notes

One good use I have personally tested is asking questions about a codebase. For most questions I tried, it felt comparable to Codex / Claude Code.
