# Awesome Agent Sandboxes

A curated list of sandboxing solutions for AI agents, organized by isolation layer.

Where applicable, each section links to the base technologies (isolation engines, runtimes) that underpin the listed sandboxes, in case you already have the platform plumbing and only need the engine itself.

---

## VMs & MicroVMs

Full or lightweight VMs provide the strongest isolation boundary and are the most common choice for running untrusted agent code at scale. Built on technologies like [Firecracker](https://github.com/firecracker-microvm/firecracker), [libkrun](https://github.com/containers/libkrun), and [Cloud Hypervisor](https://github.com/cloud-hypervisor/cloud-hypervisor).

- [E2B](https://e2b.dev) - Cloud sandbox platform powered by Firecracker microVMs for enterprise AI agents to safely execute code
- [Sprites](https://sprites.dev) / [Fly.io Sprites](https://fly.io) - Ephemeral Linux VMs secured through Firecracker with checkpoint/restore capabilities
- [Vercel Sandbox](https://github.com/vercel/sandbox) - Ephemeral compute service executing untrusted code in isolated Firecracker microVMs
- [yolo-cage](https://github.com/borenstein/yolo-cage) - VM-based sandbox for AI coding agents that blocks secret exfiltration and prevents agents from merging their own PRs
- [Matchlock](https://github.com/jingkaihe/matchlock) - CLI running AI agents in ephemeral microVMs (Firecracker on Linux, Virtualization.framework on macOS) with network allowlisting
- [Arrakis](https://github.com/abshkbh/arrakis) - Self-hosted microVM platform for AI agent code execution with checkpoint-and-restore functionality
- [BunkerVM](https://github.com/ashishgituser/bunkervm) - Self-hosted Firecracker microVMs that record every command, rewind to any earlier step, and diff two agent runs
- [ERA](https://github.com/BinSquare/ERA) - Local sandboxing using krunvm microVMs with container-like UX and optional Cloudflare Workers deployment
- [Gondolin](https://github.com/earendil-works/gondolin) - QEMU-based microVMs booting in under a second with programmatic network and filesystem control
- [Netclode](https://github.com/angristan/netclode) - Self-hosted cloud coding agent using Kata Containers with Cloud Hypervisor microVMs
- [Runloop](https://runloop.ai) - Enterprise AI infrastructure with dual-layer isolation (VM + container) for secure agent execution
- [Vibe](https://github.com/lynaghk/vibe) - Zero-configuration Debian Linux VMs on macOS using native Virtualization.framework for LLM agents
- [exe.dev](https://exe.dev) - Persistent SSH-accessible VMs with sudo access for development workflows
- [Daytona](https://daytona.io) - Secure infrastructure for running AI-generated code in cloud environments
- [Modal](https://modal.com) - Serverless platform with ephemeral environments for running untrusted code at scale

---

## Containers

OS-level isolation uses Linux namespaces, cgroups, or kernel-enforced policies; it is fast and flexible but shares the host kernel. Built on technologies like [gVisor](https://github.com/google/gvisor) and [LiteBox](https://github.com/microsoft/litebox).

- [Leash](https://github.com/strongdm/leash) - Policy enforcement wrapper for AI coding agents with Cedar-based rules and real-time monitoring
- [packnplay](https://github.com/obra/packnplay) - Docker wrapper for AI assistants with automatic git worktree and devcontainer support
- [yolobox](https://github.com/finbarr/yolobox) - CLI running AI agents in containers where home directory stays unmounted for safety
- [CodeRunner](https://github.com/instavm/coderunner) - Secure local sandbox to run LLM-generated code on macOS using Apple containers and MCP
- [SandboxAI](https://github.com/substratusai/sandboxai) - Docker-containerized runtime for safely executing AI-generated Python and shell commands
- [llm-sandbox](https://github.com/vndee/llm-sandbox) - Python library executing LLM-generated code in Docker/Kubernetes/Podman with customizable security
- [MCP Runner](https://github.com/abir-taheer/mcp-runner) - MCP server platform using Docker with gVisor runtime for multi-tenant isolation
- [PythonSafeEval](https://github.com/s3131212/PythonSafeEval) - Python execution using nsjail process jail inside Docker containers

---

## Process Sandboxes

Jails and namespace-based tools restrict syscalls, filesystem, and network access for individual processes with minimal overhead. Built on technologies like [Bubblewrap](https://github.com/containers/bubblewrap), [runjail](https://github.com/debfx/runjail), and [sydbox](https://gitlab.exherbo.org/sydbox/sydbox).

- [Anthropic Sandbox Runtime](https://github.com/anthropic-experimental/sandbox-runtime) - Lightweight sandboxing tool enforcing filesystem and network restrictions on arbitrary processes without requiring a container

---

## Filesystem Sandboxes

Copy-on-write and virtual filesystem layers isolate agent changes from the host or workspace while keeping performance high.

- [AgentFS](https://docs.turso.tech/agentfs/guides/sandbox) - Copy-on-write sandboxing isolating file changes from original source tree
- [LocalSandbox](https://github.com/coplane/localsandbox) - Python SDK with SQLite-backed virtual filesystem for bash and Python execution

---

## WASM Runtimes

WebAssembly provides strong sandboxing inside a language runtime and is useful when you need embedding or portable execution. Built on technologies like [Wasmtime](https://wasmtime.dev) and [Pyodide](https://pyodide.org).

- [Wassette](https://github.com/microsoft/wassette) - MCP server runtime executing WebAssembly components with browser-grade tool isolation
- [Capsule](https://github.com/mavdol/capsule) - Secure AI agent runtime executing tasks in isolated WASM sandboxes with resource limits
- [Eryx](https://github.com/eryx-org/eryx) - Rust library executing Python (CPython 3.14) in WebAssembly sandbox via Wasmtime
- [AgentVM](https://github.com/deepclause/agentvm) - Node.js library running WASM-based Alpine Linux in worker threads for shell execution
- [amla-sandbox](https://github.com/amlalabs/amla-sandbox) - WASM sandbox with capability enforcement preventing shell escapes and unauthorized access

---

## Embedded Interpreters

In-process execution with strict capability controls but no OS boundary; best for lightweight tasks or trusted environments.

- [Monty](https://github.com/pydantic/monty) - Minimal Python interpreter in Rust with microsecond startup and strict capability controls

---

## Contributing

Contributions welcome! Please submit a PR to add new sandboxing solutions.
