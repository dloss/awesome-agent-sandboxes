# Awesome Agent Sandboxes

A curated list of sandboxing solutions for AI agents, organized by isolation mechanism.

---

## MicroVMs

Lightweight virtual machines providing hardware-level isolation with fast startup times.

### Base Technologies

- [Firecracker](https://github.com/firecracker-microvm/firecracker) - Minimalist VMM combining hardware virtualization security with container-like speed for serverless workloads
- [libkrun](https://github.com/containers/libkrun) - C library enabling applications to run isolated processes in lightweight VMs with minimal overhead
- [Cloud Hypervisor](https://github.com/cloud-hypervisor/cloud-hypervisor) - Virtual Machine Monitor for modern cloud workloads running on KVM or Microsoft Hypervisor

### Agent Sandboxes

- [E2B](https://e2b.dev) - Cloud sandbox platform powered by Firecracker microVMs for enterprise AI agents to safely execute code
- [Sprites](https://sprites.dev) / [Fly.io Sprites](https://fly.io) - Ephemeral Linux VMs secured through Firecracker with checkpoint/restore capabilities
- [Vercel Sandbox](https://github.com/vercel/sandbox) - Ephemeral compute service executing untrusted code in isolated Firecracker microVMs
- [Matchlock](https://github.com/jingkaihe/matchlock) - CLI running AI agents in ephemeral microVMs (Firecracker on Linux, Virtualization.framework on macOS) with network allowlisting
- [Arrakis](https://github.com/abshkbh/arrakis) - Self-hosted microVM platform for AI agent code execution with checkpoint-and-restore functionality
- [ERA](https://github.com/BinSquare/ERA) - Local sandboxing using krunvm microVMs with container-like UX and optional Cloudflare Workers deployment
- [Gondolin](https://github.com/earendil-works/gondolin) - QEMU-based microVMs booting in under a second with programmatic network and filesystem control
- [Netclode](https://github.com/angristan/netclode) - Self-hosted cloud coding agent using Kata Containers with Cloud Hypervisor microVMs
- [Runloop](https://runloop.ai) - Enterprise AI infrastructure with dual-layer isolation (VM + container) for secure agent execution

---

## Containers

OS-level virtualization using Linux namespaces and cgroups.

### Agent Sandboxes

- [Leash](https://github.com/strongdm/leash) - Policy enforcement wrapper for AI coding agents with Cedar-based rules and real-time monitoring
- [packnplay](https://github.com/obra/packnplay) - Docker wrapper for AI assistants with automatic git worktree and devcontainer support
- [yolobox](https://github.com/finbarr/yolobox) - CLI running AI agents in containers where home directory stays unmounted for safety
- [SandboxAI](https://github.com/substratusai/sandboxai) - Docker-containerized runtime for safely executing AI-generated Python and shell commands
- [llm-sandbox](https://github.com/vndee/llm-sandbox) - Python library executing LLM-generated code in Docker/Kubernetes/Podman with customizable security
- [MCP Runner](https://github.com/abir-taheer/mcp-runner) - MCP server platform using Docker with gVisor runtime for multi-tenant isolation
- [PythonSafeEval](https://github.com/s3131212/PythonSafeEval) - Python execution using nsjail process jail inside Docker containers

---

## Local VMs

Full virtual machines running on local hardware.

- [Vibe](https://github.com/lynaghk/vibe) - Zero-configuration Debian Linux VMs on macOS using native Virtualization.framework for LLM agents
- [exe.dev](https://exe.dev) - Persistent SSH-accessible VMs with sudo access for development workflows

---

## Remote VMs / Cloud Sandboxes

Cloud-hosted virtual machine environments.

- [Daytona](https://daytona.io) - Secure infrastructure for running AI-generated code in cloud environments
- [Modal](https://modal.com) - Serverless platform with ephemeral environments for running untrusted code at scale
- [sandbox-agent](https://github.com/rivet-dev/sandbox-agent) - Universal HTTP/SSE agent controller designed to run inside E2B, Daytona, Vercel, or Docker sandboxes

---

## User-space Kernels

Application kernels that intercept and handle syscalls in userspace.

- [gVisor](https://github.com/google/gvisor) - Memory-safe Go application kernel sandboxing containers by reimplementing Linux syscalls
- [LiteBox](https://github.com/microsoft/litebox) - Modular library OS sandboxing applications via minimal syscall interface across platforms

---

## Process Jails

Lightweight isolation using Linux kernel security features.

- [Bubblewrap](https://github.com/containers/bubblewrap) - Unprivileged sandboxing using Linux namespaces and seccomp, used by Flatpak
- [runjail](https://github.com/debfx/runjail) - CLI for isolating processes with granular filesystem and network permission control
- [sydbox](https://gitlab.exherbo.org/sydbox/sydbox) - Security-focused application kernel written in Rust for sandboxing and integrity

---

## Filesystem Virtualization

Copy-on-write and virtual filesystem approaches.

- [AgentFS](https://docs.turso.tech/agentfs/guides/sandbox) - Copy-on-write sandboxing isolating file changes from original source tree
- [LocalSandbox](https://github.com/coplane/localsandbox) - Python SDK with SQLite-backed virtual filesystem for bash and Python execution

---

## WebAssembly (WASM)

Browser-grade isolation through WebAssembly sandboxing.

### Runtimes

- [Wasmtime](https://wasmtime.dev) - Fast and secure WebAssembly runtime by Bytecode Alliance with WASI support
- [Pyodide](https://pyodide.org) - CPython distribution compiled to WebAssembly for browser and Node.js execution

### Agent Sandboxes

- [Wassette](https://github.com/microsoft/wassette) - MCP server runtime executing WebAssembly components with browser-grade tool isolation
- [Capsule](https://github.com/mavdol/capsule) - Secure AI agent runtime executing tasks in isolated WASM sandboxes with resource limits
- [Eryx](https://github.com/eryx-org/eryx) - Rust library executing Python (CPython 3.14) in WebAssembly sandbox via Wasmtime
- [AgentVM](https://github.com/deepclause/agentvm) - Node.js library running WASM-based Alpine Linux in worker threads for shell execution
- [amla-sandbox](https://github.com/amlalabs/amla-sandbox) - WASM sandbox with capability enforcement preventing shell escapes and unauthorized access

---

## Embedded Interpreters

In-process sandboxed code execution without OS-level isolation.

- [Monty](https://github.com/pydantic/monty) - Minimal Python interpreter in Rust with microsecond startup and strict capability controls

---

## Contributing

Contributions welcome! Please submit a PR to add new sandboxing solutions.
