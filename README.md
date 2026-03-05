# Agentic System Design

A curated collection of research papers, blog posts, tools, and documentation for building agentic systems - AI agents that can reason, plan, use tools, and collaborate autonomously.

## Table of Contents

### [Core Infrastructure](#core-infrastructure)
1. [Memory Systems](#1-memory-systems)
2. [Sandboxes & Isolation](#2-sandboxes--isolation)
3. [MCP (Model Context Protocol)](#3-mcp-model-context-protocol)

### [Agent Architecture & Orchestration](#agent-architecture--orchestration)
4. [Agent Architectures & Orchestration](#4-agent-architectures--orchestration)
5. [Programmatic Tool Calling](#5-programmatic-tool-calling)
6. [Multi-Agent Systems](#6-multi-agent-systems)

### [Planning & Reasoning](#planning--reasoning)
7. [Planning & Reasoning](#7-planning--reasoning)

### [Web & Browser](#web--browser)
8. [WebMCP Protocol](#8-webmcp-protocol)
9. [Browser Automation Stacks](#9-browser-automation-stacks)

### [Operations & Observability](#operations--observability)
10. [State Management](#10-state-management)
11. [Observability & Debugging](#11-observability--debugging)
12. [Evaluation & Benchmarking](#12-evaluation--benchmarking)
13. [Error Handling & Recovery](#13-error-handling--recovery)

### [Safety & Human Interaction](#safety--human-interaction)
14. [Human-in-the-Loop](#14-human-in-the-loop)
15. [Safety & Alignment](#15-safety--alignment)

### [Capabilities](#capabilities)
16. [Skills & Capabilities](#16-skills--capabilities)

### [Appendix](#appendix)
- [Tools & Repositories](#tools--repositories-1)
- [Summary Statistics](#summary-statistics)
- [Recommended Reading Order](#recommended-reading-order)

---

## Core Infrastructure

### 1. Memory Systems

#### Research Papers (2026)

**EverMemOS: A Self-Organizing Memory Operating System for Structured Long-Horizon Reasoning**
- **Authors:** Chuanrui Hu, Xingze Gao, Zuyi Zhou, Dannong Xu, Yi Bai, Xintong Li, Hui Zhang, Tong Li, Chong Zhang, Lidong Bing, Yafeng Deng
- **Publication:** January 8, 2026
- **URL:** https://arxiv.org/abs/2601.02163
- **Why Relevant:** Implements an engram-inspired lifecycle for computational memory, converting dialogue streams into MemCells that capture episodic traces, atomic facts, and time-bounded Foresight signals.

**MemRL: Self-Evolving Agents via Runtime Reinforcement Learning on Episodic Memory**
- **Authors:** Shengtao Zhang, Jiaqian Wang, Ruiwen Zhou, Junwei Liao, Yuchen Feng, Zhuo Li, Yujie Zheng, Weinan Zhang, Ying Wen, Zhiyu Li, Feiyu Xiong, Yutao Qi, Bo Tang, Muning Wen
- **Publication:** January 12, 2026
- **URL:** https://arxiv.org/abs/2601.03192
- **Why Relevant:** Proposes a non-parametric approach that evolves via reinforcement learning on episodic memory, decoupling stable reasoning from plastic memory.

**Semantic XPath: Structured Agentic Memory Access for Conversational AI**
- **Authors:** Yifan Simon Liu, Ruifan Wu, Liam Gallagher, Jiazhou Liang, Armin Toroghi, Scott Sanner
- **Publication:** March 1, 2026
- **URL:** https://arxiv.org/abs/2603.01160
- **Why Relevant:** Introduces a tree-structured memory module for conversational AI that improves over flat-RAG baselines by 176.7% while using only 9.1% of the tokens required by in-context memory.

#### Research Papers (2025)

**HiMeS: Hippocampus-inspired Memory System for Personalized AI Assistants**
- **Authors:** Hailong Li, Feifei Li, Wenhui Que, Xingyu Fan
- **Publication:** January 6, 2026
- **URL:** https://arxiv.org/abs/2601.06152
- **Why Relevant:** Proposes an AI assistant architecture that fuses short-term and long-term memory, inspired by biological hippocampus-neocortex memory mechanisms.

**LUMA-RAG: Lifelong Multimodal Agents with Provably Stable Streaming Alignment**
- **Authors:** Rohan Wandre, Yash Gajewar, Namrata Patel, Vivek Dhalkari
- **Publication:** November 4, 2025
- **URL:** https://arxiv.org/abs/2511.02371
- **Why Relevant:** Presents a lifelong multimodal agent architecture with streaming, multi-tier memory system that dynamically spills embeddings from hot tier to compressed tier under strict memory budgets.

**MIRIX: Multi-Agent Memory System for LLM-Based Agents**
- **Authors:** Yu Wang, Xi Chen
- **Publication:** July 10, 2025
- **URL:** https://arxiv.org/abs/2507.07957
- **Why Relevant:** Introduces a modular, multi-agent memory system with six distinct memory types: Core, Episodic, Semantic, Procedural, Resource Memory, and Knowledge Vault.

**ID-RAG: Identity Retrieval-Augmented Generation for Long-Horizon Persona Coherence in Generative Agents**
- **Authors:** Daniel Platnick, Mohamed E. Bengueddache, Marjan Alirezaie, Dava J. Newman, Alex ''Sandy'' Pentland, Hossein Rahnama
- **Publication:** September 29, 2025
- **URL:** https://arxiv.org/abs/2509.25299
- **Why Relevant:** Addresses identity drift in long-horizon agents by introducing a mechanism to ground agent personas in dynamic, structured identity models.

**A Survey of Context Engineering for Large Language Models**
- **Authors:** Lingrui Mei, Jiayu Yao, Yuyao Ge, Yiwei Wang, Baolong Bi, Yujun Cai, Jiazhi Liu, Mingyu Li, Zhong-Zhi Li, Duzhen Zhang, Chenlin Zhou, Jiayi Mao, Tianze Xia, Jiafeng Guo, Shenghua Liu
- **Publication:** July 21, 2025
- **URL:** https://arxiv.org/abs/2507.13334
- **Why Relevant:** Comprehensive 166-page survey analyzing over 1400 research papers, establishing context engineering as a formal discipline for optimizing LLM information payloads.

#### Research Papers (2024-2022)

**ReAct: Synergizing Reasoning and Acting in Language Models**
- **Authors:** Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik Narasimhan, Yuan Cao
- **Publication:** October 6, 2022 (Revised March 10, 2023)
- **URL:** https://arxiv.org/abs/2210.03629
- **Why Relevant:** Foundational paper introducing ReAct pattern, enabling LLMs to generate both reasoning traces and task-specific actions in an interleaved manner.

#### Production & Engineering Blogs

**LangChain: "How we built Agent Builder's memory system"**
- **Publication:** February 21, 2026
- **URL:** https://blog.langchain.dev/how-we-built-agent-builders-memory-system/
- **Topics:** Production memory system using virtual filesystem backed by Postgres, mapping to COALA paper's procedural/semantic/episodic memory taxonomy.

**LangChain: "How to Use Memory in Agent Builder"**
- **Author:** Jacob Talbot
- **Publication:** February 19, 2026
- **URL:** https://blog.langchain.dev/how-to-use-memory-in-agent-builder/
- **Topics:** Short-term (per-thread) and long-term (persistent filesystem) memory, skills as specialized context.

**Weaviate: "Context Engineering - LLM Memory and Retrieval for AI Agents"**
- **Authors:** Femke Plantinga, Prajjwal Yadav, Victoria Slocum
- **Publication:** December 9, 2025
- **URL:** https://weaviate.io/blog/context-engineering
- **Topics:** Six pillars of context engineering, short-term vs. long-term agent memory architecture, failure modes (context poisoning/distraction/confusion/clash).

**Weaviate: "The Limit in the Loop"**
- **Authors:** Charles Pierse, Yaru Lin
- **Publication:** February 4, 2026
- **URL:** https://weaviate.io/blog/limit-in-the-loop
- **Topics:** Memory as infrastructure -- write control, deduplication, reconciliation, amendment, and purposeful forgetting for production agent memory.

**Zep: "Zep Is The New State of the Art In Agent Memory"**
- **Authors:** Preston Rasmussen, Daniel Chalef
- **Publication:** January 22, 2025
- **URL:** https://blog.getzep.com/state-of-the-art-agent-memory/
- **Topics:** Temporal knowledge graph architecture, benchmarking against MemGPT on DMR and LongMemEval, up to 100% accuracy gains.

**Zep: "The Retrieval Tradeoff: What 50 Experiments Taught Us About Context Engineering"**
- **Author:** Daniel Chalef
- **Publication:** December 9, 2025
- **URL:** https://blog.getzep.com/the-retrieval-tradeoff-what-50-experiments-taught-us-about-context-engineering/
- **Topics:** Recall vs. precision vs. efficiency tradeoff for one-shot agent memory retrieval across 50 experiments on LoCoMo benchmark.

**Zep: "Context Templates: Context Engineering Made Simple"**
- **Author:** Jack Ryan
- **Publication:** December 17, 2025
- **URL:** https://blog.getzep.com/context-templates-context-engineering-made-simple/
- **Topics:** Declarative context templates for controlling knowledge graph retrieval without writing retrieval code.

**Letta: "Sleep-time Compute"**
- **Publication:** April 21, 2025
- **URL:** https://letta.com/blog/sleep-time-compute
- **Topics:** Agents using idle periods to reorganize memory and reason proactively, creating Pareto improvement in performance.

**Letta: "Agent Memory: How to Build Agents that Learn and Remember"**
- **Publication:** July 7, 2025
- **URL:** https://letta.com/blog/agent-memory
- **Topics:** Building agents with persistent memory that learn across interactions, stateless-to-stateful transition.

**Letta: "Memory Blocks: The Key to Agentic Context Management"**
- **Publication:** May 14, 2025
- **URL:** https://letta.com/blog/memory-blocks
- **Topics:** Structured memory blocks as abstraction for context window management.

**Letta: "RAG is not Agent Memory"**
- **Publication:** February 13, 2025
- **URL:** https://letta.com/blog/rag-vs-agent-memory
- **Topics:** Why traditional RAG is insufficient for agent memory -- differences between document retrieval and true agent memory.

**Letta: "Stateful Agents: The Missing Link in LLM Intelligence"**
- **Publication:** February 6, 2025
- **URL:** https://letta.com/blog/stateful-agents
- **Topics:** Persistent memory and learning during deployment as the missing capability for production LLM intelligence.

**Letta: "Anatomy of a Context Window: A Guide to Context Engineering"**
- **Publication:** July 3, 2025
- **URL:** https://letta.com/blog/guide-to-context-engineering
- **Topics:** Designing and managing context windows for maximum agent effectiveness.

**Letta: "Continual Learning in Token Space"**
- **Publication:** December 11, 2025
- **URL:** https://letta.com/blog/continual-learning
- **Topics:** Agents carrying memories across model generations via learning in token space.

**Letta: "Introducing Context Repositories: Git-based Memory for Coding Agents"**
- **Publication:** February 12, 2026
- **URL:** https://letta.com/blog/context-repositories
- **Topics:** Programmatic context management with git-based versioning for agent memory.

**Letta: "Conversations: Shared Agent Memory across Concurrent Experiences"**
- **Publication:** January 21, 2026
- **URL:** https://letta.com/blog/conversations
- **Topics:** Conversations API for agents maintaining shared memory across parallel user experiences.

**Letta: "Letta Leaderboard: Benchmarking LLMs on Agentic Memory"**
- **Publication:** May 29, 2025
- **URL:** https://letta.com/blog/letta-leaderboard
- **Topics:** Benchmark suite evaluating LLM effectiveness at managing agentic memory tasks.

**Letta: "Benchmarking AI Agent Memory: Is a Filesystem All You Need?"**
- **Publication:** August 12, 2025
- **URL:** https://letta.com/blog/benchmarking-ai-agent-memory
- **Topics:** Filesystem-based memory scoring 74.0% on LoCoMo, beating specialized memory tool libraries.

**LlamaIndex: "Files Are All You Need"**
- **Author:** Jerry Liu
- **Publication:** January 15, 2026
- **URL:** https://www.llamaindex.ai/blog/files-are-all-you-need
- **Topics:** Agents converging on files/filesystems as primary context management interface.

---

### 2. Sandboxes & Isolation

#### Research Papers & Specifications (2024)

**Firecracker Specification Document**
- **URL:** https://github.com/firecracker-microvm/firecracker/blob/main/SPECIFICATION.md
- **Description:** Technical specification with performance characteristics enforced via CI testing.
- **Why Relevant:** Defines microVM architecture for secure, lightweight virtualization.

**Firecracker Design Document**
- **URL:** https://github.com/firecracker-microvm/firecracker/blob/main/docs/design.md
- **Description:** Architecture and component design documentation.
- **Why Relevant:** Comprehensive design documentation for understanding microVM internals.

#### Research Papers & Specifications (2021)

**RACK (Recent ACKnowledgement) TCP Loss-Detection Algorithm (RFC 8985)**
- **Standard:** RFC 8985
- **URL:** https://datatracker.ietf.org/doc/html/rfc8985
- **Implementation:** gVisor Network Stack
- **Reference:** https://gvisor.dev/blog/2021/08/31/gvisor-rack/
- **Why Relevant:** Foundation for gVisor's optimized networking stack.

#### Blog Posts (2024)

**gVisor: "Safe Ride into the Dangerzone: Reducing attack surface with gVisor"**
- **Authors:** Alexis Métaireau, Alex Pyrgiotis, Etienne Perot
- **Publication:** September 23, 2024
- **URL:** https://gvisor.dev/blog/2024/09/23/safe-ride-into-the-dangerzone/
- **Cross-posted:** https://dangerzone.rocks/news/2024-09-23-gvisor
- **Topics:** Dangerzone collaboration, document conversion security.

**E2B: "How Perplexity implemented advanced data analysis for Pro users in 1 week"**
- **URL:** https://www.e2b.dev/blog/how-perplexity-implemented-advanced-data-analysis-for-pro-users-in-1-week
- **Topics:** Data analysis, advanced features implementation.

**E2B: "How Hugging Face Is Using E2B to Replicate DeepSeek-R1"**
- **URL:** https://www.e2b.dev/blog/how-hugging-face-is-using-e2b-to-replicate-deepseek-r1
- **Topics:** Model replication, AI workloads.

**E2B: "How Manus Uses E2B to Provide Agents With Virtual Computers"**
- **URL:** https://www.e2b.dev/blog/how-manus-uses-e2b-to-provide-agents-with-virtual-computers
- **Topics:** AI agents, virtual computers.

**E2B: "Groq's Compound AI Models Are Powered by E2B"**
- **URL:** https://www.e2b.dev/blog/groqs-compound-ai-models-are-powered-by-e2b
- **Topics:** Compound AI systems.

**E2B: "Lindy Powers AI Workflows With E2B Code Action"**
- **URL:** https://www.e2b.dev/blog/lindy-powers-ai-workflows-with-e2b-code-action
- **Topics:** AI workflows, code execution.

#### Blog Posts (2023)

**gVisor: "Optimizing seccomp usage in gVisor"**
- **Author:** Etienne Perot
- **Publication:** February 1, 2024
- **URL:** https://gvisor.dev/blog/2024/02/01/seccomp/
- **Topics:** seccomp-bpf optimization, syscall filtering performance.

**gVisor: "Faster filesystem access with Directfs"**
- **Author:** Ayush Ranjan
- **Publication:** June 27, 2023
- **URL:** https://gvisor.dev/blog/2023/06/27/directfs/
- **Originally posted:** https://opensource.googleblog.com/2023/06/optimizing-gvisor-filesystems-with-directfs.html
- **Topics:** Direct filesystem access, performance improvements.

**gVisor: "Running Stable Diffusion on GPU with gVisor"**
- **Author:** Etienne Perot
- **Publication:** June 20, 2023
- **URL:** https://gvisor.dev/blog/2023/06/20/gpu-pytorch-stable-diffusion/
- **Related:** https://stability.ai/blog/stable-diffusion-public-release
- **Topics:** GPU support, NVIDIA CUDA, AI/ML workloads.

**gVisor: "Rootfs Overlay"**
- **Author:** Ayush Ranjan
- **Publication:** May 8, 2023
- **URL:** https://gvisor.dev/blog/2023/05/08/rootfs-overlay/
- **Originally posted:** https://opensource.googleblog.com/2023/04/gvisor-improves-performance-with-root-filesystem-overlay.html
- **Topics:** Filesystem performance, tmpfs overlay.

**gVisor: "Releasing Systrap - A high-performance gVisor platform"**
- **Author:** Konstantin Bogomolov
- **Publication:** April 28, 2023
- **URL:** https://gvisor.dev/blog/2023/04/28/systrap-release/
- **Topics:** Systrap platform, performance improvements.

#### Blog Posts (2022)

**gVisor: "How we Eliminated 99% of gVisor Networking Memory Allocations with Enhanced Buffer Pooling"**
- **Author:** Lucas Manning
- **Publication:** October 24, 2022
- **URL:** https://gvisor.dev/blog/2022/10/24/buffer-pooling/
- **Topics:** Netstack, memory optimization, userspace networking.

**gVisor: "Threat Detection in gVisor"**
- **Author:** Fabricio Voznika
- **Publication:** August 31, 2022
- **URL:** https://gvisor.dev/blog/2022/08/01/threat-detection/
- **Topics:** Runtime monitoring, threat detection, Falco integration: https://falco.org.

#### Blog Posts (2021)

**gVisor: "Running gVisor in Production at Scale in Ant"**
- **Authors:** Jianfeng Tan, Yong He (Ant Group)
- **Publication:** December 2, 2021
- **URL:** https://gvisor.dev/blog/2021/12/02/running-gvisor-in-production-at-scale-in-ant/
- **Related:** https://www.antgroup.com/
- **Topics:** Production deployment, large-scale infrastructure.

**gVisor: "gVisor RACK"**
- **Author:** Nayana Bidari
- **Publication:** August 31, 2021
- **URL:** https://gvisor.dev/blog/2021/08/31/gvisor-rack/
- **Topics:** TCP loss detection, networking improvements.

#### Blog Posts (2020)

**gVisor: "Platform Portability"**
- **Authors:** Ian Lewis, Michael Pratt
- **Publication:** October 22, 2020
- **URL:** https://gvisor.dev/blog/2020/10/22/platform-portability/
- **Topics:** Hardware virtualization alternatives, cross-platform support.

**gVisor: "Containing a Real Vulnerability"**
- **Author:** Fabricio Voznika
- **Publication:** September 18, 2020
- **URL:** https://gvisor.dev/blog/2020/09/18/containing-a-real-vulnerability/
- **Related CVE:** https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-14386
- **Topics:** Container escape vulnerabilities, gVisor security case study.

**gVisor: "gVisor Networking Security"**
- **Author:** Ian Gudger
- **Publication:** April 2, 2020
- **URL:** https://gvisor.dev/blog/2020/04/02/gvisor-networking-security/
- **Topics:** Network stack architecture, security principles.

**gVisor: "gVisor Security Basics - Part 1"**
- **Authors:** Jeremiah Spradlin, Zach Koopmans
- **Publication:** November 18, 2019
- **URL:** https://gvisor.dev/blog/2019/11/18/gvisor-security-basics-part-1/
- **Topics:** Security design principles, container-native security.

#### Blog Posts (2018)

**AWS Blog: "Firecracker – Lightweight Virtualization for Serverless Computing"**
- **Author:** Jeff Barr
- **Publication:** November 26, 2018
- **URL:** https://aws.amazon.com/blogs/aws/firecracker-lightweight-virtualization-for-serverless-computing/
- **Description:** Announcement of Firecracker technology, security features, performance characteristics (125ms startup, 5 MiB memory overhead).

**AWS Open Source Blog: "Announcing the Firecracker Open Source Technology: Secure and Fast microVM for Serverless Computing"**
- **Authors:** Arun Gupta, Linda Lian
- **Publication:** November 27, 2018
- **URL:** https://aws.amazon.com/blogs/opensource/firecracker-open-source-secure-fast-microvm-serverless/
- **Description:** Open source announcement, technical architecture, Rust language choice, integration with AWS Lambda and Fargate.

#### Production & Engineering Blogs

**E2B: "Firecracker vs QEMU"**
- **Publication:** March 2025
- **URL:** https://www.e2b.dev/blog/firecracker-vs-qemu
- **Topics:** Comparison of microVM technologies underpinning sandbox isolation for AI code execution.

**E2B: "How I taught an AI to use a computer"**
- **Publication:** January 2025
- **URL:** https://www.e2b.dev/blog/how-i-taught-an-ai-to-use-a-computer
- **Topics:** Giving AI agents full sandboxed computer access (browser, filesystem, terminal).

**E2B: "Code Interpreter Sandbox"**
- **Publication:** November 2023
- **URL:** https://www.e2b.dev/blog/e2b-sandbox
- **Topics:** Sandboxed code interpreter architecture for safe AI-generated code execution.

**E2B: "Up to 5x Faster Sandboxes"**
- **Publication:** February 2024
- **URL:** https://www.e2b.dev/blog/up-to-5x-faster-sandboxes
- **Topics:** Optimizing sandbox boot times using Firecracker microVMs for faster agent code execution.

**E2B: "LLM-powered Code Interpreters"**
- **Publication:** February 2024
- **URL:** https://www.e2b.dev/blog/llm-powered-code-interpreters
- **Topics:** Survey of LLM code interpreter architectures and why sandboxed execution is critical.

**E2B: "Limitations of Running AI Agents Locally"**
- **Publication:** February 2024
- **URL:** https://www.e2b.dev/blog/limitations-of-running-ai-agents-locally
- **Topics:** Why local execution is insufficient and cloud sandboxes provide better isolation.

**Fly.io: "Fly Machines: an API for fast-booting VMs"**
- **Author:** Kurt Mackey
- **Publication:** May 2022
- **URL:** https://fly.io/blog/fly-machines/
- **Topics:** Firecracker-based microVM API with 300ms boot times, scale-to-zero, per-tenant isolation.

**Fly.io: "The Design & Implementation of Sprites"**
- **Author:** Thomas Ptacek
- **Publication:** 2026
- **URL:** https://fly.io/blog/design-and-implementation/
- **Topics:** Architecture of Fly's Sprites system for running isolated execution environments.

**Fly.io: "Code And Let Live"**
- **Author:** Kurt Mackey
- **Publication:** 2026
- **URL:** https://fly.io/blog/code-and-let-live/
- **Topics:** Isolated code environments for the agent era, trust and isolation in computing.

**Fly.io: "Phoenix.new -- The Remote AI Runtime"**
- **Author:** Chris McCord
- **Publication:** 2025
- **URL:** https://fly.io/blog/phoenix-new-the-remote-ai-runtime/
- **Topics:** Remote AI runtime for coding agents on Fly Machines with sandboxed execution.

**Fly.io: "Our Best Customers Are Now Robots"**
- **Author:** Kurt Mackey
- **Publication:** 2025
- **URL:** https://fly.io/blog/fuckin-robots/
- **Topics:** AI agents as primary users driving demand for programmatically-created isolated environments.

**Fly.io: "The Serverless Server"**
- **Author:** Will Jordan
- **Publication:** 2022
- **URL:** https://fly.io/blog/the-serverless-server/
- **Topics:** Firecracker-based VM architecture providing stronger isolation than containers.

**Daytona: "Sandbox Firewall"**
- **Author:** Ivan Burazin
- **Publication:** August 2025
- **URL:** https://www.daytona.io/dotfiles/sandbox-firewall
- **Topics:** Fine-grained network firewall for AI sandboxes with zero-trust code execution.

**Daytona: "Securing AI Code: Building Safe Sandboxes with Daytona SDK"**
- **Author:** Nikola Balic
- **Publication:** February 2025
- **URL:** https://www.daytona.io/dotfiles/securing-ai-code-building-safe-sandboxes-with-daytona-sdk
- **Topics:** Building isolated sandboxes for AI-generated code with resource and security controls.

**Daytona: "Sandboxing AI Development with Agent-Agnostic Infrastructure"**
- **Author:** Nikola Balic
- **Publication:** October 2024
- **URL:** https://www.daytona.io/dotfiles/sandboxing-ai-development-with-agent-agnostic-infrastructure
- **Topics:** Agent-agnostic sandbox middleware for running AI coding agents in parallel isolated environments.

**Daytona: "Harnessing AI through Standardization and Isolation"**
- **Author:** Nikola Balic
- **Publication:** November 2023
- **URL:** https://www.daytona.io/dotfiles/harnessing-ai-through-standardization-and-isolation
- **Topics:** Standardized dev environments as AI sandboxes combining isolation with reproducibility.

**Daytona: "Daytona Raises $24M Series A to Give Every Agent a Computer"**
- **Author:** Ivan Burazin
- **Publication:** February 2026
- **URL:** https://www.daytona.io/dotfiles/daytona-raises-24m-series-a-to-give-every-agent-a-computer
- **Topics:** Providing isolated "computers" (sandboxes) for millions of AI agents as compute infrastructure.

**Cloudflare: "Mitigating Spectre and Other Security Threats: The Cloudflare Workers Security Model"**
- **Author:** Kenton Varda
- **Publication:** July 2020
- **URL:** https://blog.cloudflare.com/mitigating-spectre-and-other-security-threats-the-cloudflare-workers-security-model
- **Topics:** Workers' multi-layer isolation: V8 isolates, process sandboxing, capability-based API design, Spectre mitigations.

**Cloudflare: "Introducing Moltworker: a self-hosted personal AI agent"**
- **Authors:** Celso Martinho, Brian Brunner, Sid Chatterjee, Andreas Jansson
- **Publication:** January 2026
- **URL:** https://blog.cloudflare.com/moltworker-self-hosted-ai-agent/
- **Topics:** Self-hosted AI agent running on Cloudflare's Sandbox SDK with container isolation.

**Cloudflare: "Containers are available in public beta"**
- **Publication:** June 2025
- **URL:** https://blog.cloudflare.com/containers-are-available-in-public-beta-for-simple-global-and-programmable/
- **Topics:** Programmable, isolated container workloads alongside Workers for AI compute.

**Meta Engineering: "Building Private Processing for AI tools on WhatsApp"**
- **Publication:** April 2025
- **URL:** https://engineering.fb.com/2025/04/29/security/whatsapp-private-processing-ai-tools/
- **Topics:** Secure isolated execution environment for processing AI tool calls with privacy guarantees.

**Meta Engineering: "Scaling Privacy Infrastructure for GenAI Product Innovation"**
- **Publication:** October 2025
- **URL:** https://engineering.fb.com/2025/10/23/security/scaling-privacy-infrastructure-for-genai-product-innovation/
- **Topics:** Privacy isolation infrastructure for GenAI products at Meta scale.

**Cursor: "Implementing a secure sandbox for local agents"**
- **Publication:** February 18, 2026
- **URL:** https://www.cursor.com/blog/agent-sandboxing
- **Topics:** Building agent sandboxing on macOS, Linux, and Windows for secure autonomous execution.

---

### 3. MCP (Model Context Protocol)

#### Standards & Specifications (2025)

**MCP Specification (2025-06-18 Revision)**
- **URL:** https://spec.modelcontextprotocol.io/
- **Description:** Complete protocol specification with June 18, 2025 revision.
- **Why Relevant:** Defines the open standard for connecting AI applications to external systems.

**MCP Authorization Specification**
- **URL:** https://modelcontextprotocol.io/specification/2025-06-18/basic/authorization
- **Description:** Authorization flow specification for HTTP-based transports.
- **Publication:** June 18, 2025 (Protocol Revision).

**MCP Schema (TypeScript)**
- **URL:** https://github.com/modelcontextprotocol/specification/blob/main/schema/2025-11-25/schema.ts
- **Date:** November 25, 2025
- **Description:** Schema defined in TypeScript.

**MCP Schema (JSON)**
- **URL:** https://github.com/modelcontextprotocol/specification/blob/main/schema/2025-11-25/schema.json
- **Date:** November 25, 2025
- **Description:** JSON Schema for wider compatibility.

#### OAuth Standards Referenced

**OAuth 2.1 IETF DRAFT**
- **URL:** https://datatracker.ietf.org/doc/html/draft-ietf-oauth-v2-1-13
- **Type:** Standard (Draft)
- **Description:** OAuth 2.1 Authorization Framework.

**OAuth 2.0 Authorization Server Metadata (RFC 8414)**
- **URL:** https://datatracker.ietf.org/doc/html/rfc8414
- **Type:** Standard (RFC)
- **Description:** Authorization Server Metadata for OAuth 2.0.

**OAuth 2.0 Dynamic Client Registration Protocol (RFC 7591)**
- **URL:** https://datatracker.ietf.org/doc/html/rfc7591
- **Type:** Standard (RFC)
- **Description:** Dynamic Client Registration for OAuth 2.0.

**OAuth 2.0 Protected Resource Metadata (RFC 9728)**
- **URL:** https://datatracker.ietf.org/doc/html/rfc9728
- **Type:** Standard (RFC)
- **Description:** Protected Resource Metadata discovery for OAuth 2.0.

**OAuth 2.0 Resource Indicators (RFC 8707)**
- **URL:** https://www.rfc-editor.org/rfc/rfc8707.html
- **Type:** Standard (RFC)
- **Description:** Resource Indicators for OAuth 2.0.

#### Documentation

**Model Context Protocol Main Website**
- **URL:** https://modelcontextprotocol.io/
- **Description:** Official MCP homepage with overview, getting started guides, and architecture documentation.

**MCP Registry**
- **URL:** https://registry.modelcontextprotocol.io/
- **Description:** Discover and browse published MCP servers.

**MCP Registry GitHub**
- **URL:** https://github.com/modelcontextprotocol/registry
- **Description:** Registry source code and documentation.

**Anthropic MCP Documentation**
- **URL:** https://docs.anthropic.com/en/docs/build-with-claude/mcp
- **Description:** Official Anthropic documentation for integrating MCP with Claude applications.

#### Production & Engineering Blogs

**Anthropic: "Introducing the Model Context Protocol"**
- **Publication:** November 25, 2024
- **URL:** https://www.anthropic.com/news/model-context-protocol
- **Topics:** Original MCP announcement -- open standard for connecting AI assistants to data sources.

**Anthropic: "Code execution with MCP: Building more efficient agents"**
- **Authors:** Adam Jones, Conor Kelly
- **Publication:** November 4, 2025
- **URL:** https://www.anthropic.com/engineering/code-execution-with-mcp
- **Topics:** Agents writing code against MCP servers as APIs instead of direct tool calls -- 98.7% token reduction.

**Anthropic: "Desktop Extensions: One-click MCP server installation"**
- **Publication:** June 26, 2025
- **URL:** https://www.anthropic.com/engineering/desktop-extensions
- **Topics:** .mcpb packaging format for one-click MCP server installation, solving manual config friction.

**Cloudflare: "Build and deploy Remote MCP servers to Cloudflare"**
- **Authors:** Brendan Irvine-Broque, Dina Kozlov, Glen Maddern
- **Publication:** March 25, 2025
- **URL:** https://blog.cloudflare.com/remote-model-context-protocol-servers-mcp
- **Topics:** Remote MCP servers with OAuth 2.1 auth, McpAgent class on Durable Objects, mcp-remote adapter.

**Cloudflare: "Securing the AI Revolution: Introducing Cloudflare MCP Server Portals"**
- **Author:** Kenny Johnson
- **Publication:** August 26, 2025
- **URL:** https://blog.cloudflare.com/zero-trust-mcp-server-portals/
- **Topics:** Enterprise MCP security -- centralized gateway with Zero Trust policy enforcement and audit logging.

**Cloudflare: "Code Mode: give agents an entire API in 1,000 tokens"**
- **Author:** Matt Carey
- **Publication:** February 20, 2026
- **URL:** https://blog.cloudflare.com/code-mode-mcp/
- **Topics:** MCP server for entire Cloudflare API (2,500+ endpoints) collapsed into 2 tools -- 99.9% token reduction.

**Vercel: "The second wave of MCP: Building for LLMs, not developers"**
- **Publication:** September 9, 2025
- **URL:** https://vercel.com/blog/the-second-wave-of-mcp-building-for-llms-not-developers
- **Topics:** MCP evolving from developer-focused tools to LLM-native integrations.

**Vercel: "Building efficient MCP servers"**
- **Publication:** June 12, 2025
- **URL:** https://vercel.com/blog/building-efficient-mcp-servers
- **Topics:** Engineering guide with implementations from Zapier, Composio, and Solana teams.

**Vercel: "Addressing security and quality issues with MCP tools in AI Agents"**
- **Publication:** September 17, 2025
- **URL:** https://vercel.com/blog/generate-static-ai-sdk-tools-from-mcp-servers-with-mcp-to-ai-sdk
- **Topics:** mcp-to-ai-sdk for generating static MCP tools, addressing dynamic MCP security risks.

**Vercel: "How Vapi built their MCP server on Vercel"**
- **Publication:** May 21, 2025
- **URL:** https://vercel.com/blog/vapi-mcp-server-on-vercel
- **Topics:** Production case study of Vapi deploying MCP server on Vercel with Fluid Compute.

**LangChain: "MCP: Flash in the Pan or Future Standard?"**
- **Authors:** Harrison Chase, Nuno Campos
- **Publication:** March 8, 2025
- **URL:** https://blog.langchain.dev/mcp-fad-or-fixture/
- **Topics:** Debate on MCP's value -- useful for tools in agents you don't control, limited by tool selection reliability.

**LlamaIndex: "Skills vs MCP tools for agents: when to use what"**
- **Authors:** Clelia Astra Bertelli, Tuana Celik
- **Publication:** February 3, 2026
- **URL:** https://www.llamaindex.ai/blog/skills-vs-mcp-tools-for-agents-when-to-use-what
- **Topics:** MCP tools (deterministic API calls) vs Skills (natural language instructions) comparison.

**LlamaIndex: "Adding Native MCP to LlamaIndex Docs"**
- **Publication:** October 31, 2025
- **URL:** https://www.llamaindex.ai/blog/adding-native-mcp-to-llamaindex-docs
- **Topics:** Native MCP search implementation for LlamaIndex documentation.

**Simon Willison: "Introducing the Model Context Protocol"**
- **Author:** Simon Willison
- **Publication:** November 25, 2024
- **URL:** https://simonwillison.net/2024/Nov/25/model-context-protocol/
- **Topics:** Early independent analysis of MCP spec, Claude Desktop integration, and sqlite MCP server.

#### Metadata

**Authors:** David Soria Parra (@dsp) and Justin Spahr-Summers (@jspahrsummers)
**License:** Apache License 2.0 for code and specifications, Creative Commons Attribution 4.0 International for documentation
**Governance:** Model Context Protocol as a Series of LF Projects, LLC
**Governance Policies:** https://www.lfprojects.org/policies/

---

## Agent Architecture & Orchestration

### 4. Agent Architectures & Orchestration

#### Research Papers (2026)

**The Auton Agentic AI Framework**
- **Authors:** Sheng Cao, Zhao Chang, Chang Li, Hannan Li, Liyao Fu, Ji Tang
- **Publication:** February 27, 2026
- **URL:** https://arxiv.org/abs/2602.23720
- **Why Relevant:** Describes a principled architecture for standardizing autonomous agent systems, with hierarchical memory consolidation inspired by biological episodic memory.

#### Research Papers (2025)

**EvoTest: Evolutionary Test-Time Learning for Self-Improving Agentic Systems**
- **Authors:** Yufei He, Juncheng Liu, Yue Liu, Yibo Li, Tri Cao, Zhiyuan Hu, Xinxing Xu, Bryan Hooi
- **Publication:** October 15, 2025
- **URL:** https://arxiv.org/abs/2510.13220
- **Why Relevant:** Introduces evolutionary test-time learning framework that improves agents without fine-tuning by evolving the entire agentic system after every episode.

#### Research Papers (2023)

**Generative Agents: Interactive Simulacra of Human Behavior**
- **Authors:** J. Z. Shunyu Yao, Jiacheng Li, Yuyang Zhao, Izhak Shafran, Karthik Narasimhan
- **Publication:** April 2023
- **URL:** https://arxiv.org/abs/2304.03442
- **Why Relevant:** Simulation of human-like agent behavior in interactive environments.

**Agents: An Open-source Framework for Autonomous Language Agents**
- **Authors:** Wangchunshu Zhou, Yuchen Eleanor Jiang, Long Li, Jialong Wu, Tiannan Wang, Shi Qiu, Jintian Zhang, Jing Chen, Ruipu Wu, Shuai Wang, Shiding Zhu, Jiyu Chen, Wentao Zhang, Xiangru Tang, Ningyu Zhang, Huajun Chen, Peng Cui, Mrinmaya Sachan
- **Publication:** September 14, 2023 (Revised December 12, 2023)
- **URL:** https://arxiv.org/abs/2309.07870
- **Why Relevant:** Open-source library enabling non-specialists to build state-of-the-art autonomous language agents with planning, memory, tool usage, and multi-agent communication.

#### Research Papers (2010-2008)

**Pregel: A System for Large-Scale Graph Processing**
- **Authors:** Grzegorz Malewicz, Matthew H. Austern, Aart J.C Bik, James C. Dehnert, Ilan Horn, Naty Leiser, Grzegorz Czajkowski
- **Publication:** Proceedings of the 2010 International Conference on Management of Data, ACM, New York, NY, USA, pp. 135-146
- **URL:** https://research.google/pubs/pub37252/
- **Referenced by:** LangGraph
- **Why Relevant:** Foundational paper on distributed graph processing that inspired LangGraph's architecture.

**Exploring Network Structure, Dynamics, and Function Using NetworkX**
- **Authors:** Aric A. Hagberg, Daniel A. Schult, Pieter J. Swart
- **Publication:** Proceedings of the 7th Python in Science Conference (SciPy2008), August 2008
- **URL:** http://conference.scipy.org.s3-website-us-east-1.amazonaws.com/proceedings/scipy2008/paper_2/
- **PDF:** http://conference.scipy.org.s3-website-us-east-1.amazonaws.com/proceedings/scipy2008/paper_2/full_text.pdf
- **Referenced by:** LangGraph
- **Why Relevant:** The NetworkX paper that influenced LangGraph's interface design.

#### Documentation

**LangGraph Documentation**
- **Overview:** https://docs.langchain.com/oss/python/langgraph/overview
- **Quickstart:** https://docs.langchain.com/oss/python/langgraph/quickstart
- **Durable Execution:** https://docs.langchain.com/oss/python/langgraph/durable-execution
- **Human-in-the-Loop:** https://docs.langchain.com/oss/python/langgraph/interrupts
- **Memory:** https://docs.langchain.com/oss/python/langgraph/memory
- **LangGraph Studio:** https://docs.langchain.com/oss/python/langgraph/studio
- **Case Studies:** https://www.langchain.com/built-with-langgraph (LinkedIn, Uber, Klarna, GitLab)
- **Intro to LangGraph Course:** https://academy.langchain.com/courses/intro-to-langgraph

**CrewAI Documentation**
- **Official Documentation:** https://docs.crewai.com
- **Crew Concepts:** https://docs.crewai.com/concepts/crews
- **Flows:** https://docs.crewai.com/concepts/flows
- **LLM Connections:** https://docs.crewai.com/how-to/LLM-Connections/
- **Learning Platform:** https://learn.crewai.com - 100,000+ certified developers

#### Production & Engineering Blogs

**Anthropic: "Building effective agents"**
- **Authors:** Erik Schluntz, Barry Zhang
- **Publication:** December 19, 2024
- **URL:** https://www.anthropic.com/engineering/building-effective-agents
- **Topics:** Definitive guide to agent architecture patterns (prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer).

**Anthropic: "Effective harnesses for long-running agents"**
- **Publication:** November 26, 2025
- **URL:** https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents
- **Topics:** Production patterns for building reliable harnesses around long-running agents.

**Anthropic: "Effective context engineering for AI agents"**
- **Publication:** September 29, 2025
- **URL:** https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
- **Topics:** Techniques for managing and engineering context in agentic systems.

**Anthropic: "Claude Code: Best practices for agentic coding"**
- **Publication:** April 18, 2025
- **URL:** https://www.anthropic.com/engineering/claude-code-best-practices
- **Topics:** Production best practices for agentic coding including task decomposition and verification loops.

**Anthropic: "Beyond permission prompts: making Claude Code more secure and autonomous"**
- **Publication:** October 20, 2025
- **URL:** https://www.anthropic.com/engineering/claude-code-sandboxing
- **Topics:** Security architecture for autonomous coding agents, sandboxing for safe long-running execution.

**LangChain: "Agent Engineering: A New Discipline"**
- **Author:** Harrison Chase
- **Publication:** December 2025
- **URL:** https://blog.langchain.dev/agent-engineering-a-new-discipline/
- **Topics:** Agent engineering as emerging discipline requiring new skills around orchestration, evaluation, and observability.

**LangChain: "On Agent Frameworks and Agent Observability"**
- **Author:** Harrison Chase
- **Publication:** February 2026
- **URL:** https://blog.langchain.dev/on-agent-frameworks-and-agent-observability/
- **Topics:** Why orchestration and observability remain critical even as LLMs improve.

**LangChain: "You don't know what your agent will do until it's in production"**
- **Publication:** February 2026
- **URL:** https://blog.langchain.dev/you-dont-know-what-your-agent-will-do-until-its-in-production/
- **Topics:** Production monitoring challenges -- non-deterministic behavior, infinite inputs, building evaluation from traces.

**LangChain: "Improving Deep Agents with harness engineering"**
- **Publication:** February 2026
- **URL:** https://blog.langchain.dev/improving-deep-agents-with-harness-engineering/
- **Topics:** How harness engineering moved a coding agent from Top 30 to Top 5 on Terminal Bench.

**LangChain: "The two patterns by which agents connect sandboxes"**
- **Publication:** February 2026
- **URL:** https://blog.langchain.dev/the-two-patterns-by-which-agents-connect-sandboxes/
- **Topics:** Architectural patterns for connecting agents to sandboxed execution environments.

**LangChain: "LangChain and LangGraph Agent Frameworks Reach v1.0 Milestones"**
- **Publication:** October 2025
- **URL:** https://blog.langchain.dev/langchain-langgraph-1dot0/
- **Topics:** LangGraph v1.0 as graph-based orchestration framework for production stateful agent workflows.

**LlamaIndex: "LlamaAgents Builder: Idea To Deployed Agent in Minutes"**
- **Publication:** January 28, 2026
- **URL:** https://www.llamaindex.ai/blog/llamaagents-builder-idea-to-deployed-agent-in-minutes
- **Topics:** Agent builder generating workflows from natural language for document processing.

**LlamaIndex: "Long Horizon Document Agents"**
- **Publication:** February 12, 2026
- **URL:** https://www.llamaindex.ai/blog/long-horizon-document-agents
- **Topics:** Long-running autonomous agents with event triggers and persistent task backlogs.

**Cursor: "The third era of AI software development"**
- **Publication:** February 26, 2026
- **URL:** https://www.cursor.com/blog/third-era
- **Topics:** Autonomous cloud agents taking on larger tasks over longer timescales.

**Cursor: "Cursor agents can now control their own computers"**
- **Publication:** February 24, 2026
- **URL:** https://www.cursor.com/blog/agent-computer-use
- **Topics:** Cloud agents using browser-based computer use to verify code changes autonomously.

**Cursor: "Build agents that run automatically"**
- **Publication:** March 5, 2026
- **URL:** https://www.cursor.com/blog/automations
- **Topics:** Event-driven agent automations with triggers for continuous autonomous operation.

**Cognition: "An Early Preview of SWE-1.6 and Research Update"**
- **Authors:** Carlo Baronio, Ben Pan, Sam Lee, et al.
- **Publication:** March 1, 2026
- **URL:** https://www.cognition.ai/blog/swe-1-6-preview
- **Topics:** Latest agent model optimized for software engineering with improved planning and execution.

**Cognition: "Rebuilding Devin for Claude Sonnet 4.5: Lessons and Challenges"**
- **Publication:** September 29, 2025
- **URL:** https://www.cognition.ai/blog/devin-sonnet-4-5-lessons-and-challenges
- **Topics:** Engineering lessons from rebuilding the Devin agent architecture for a new foundation model.

**Cognition: "Devin's 2025 Performance Review"**
- **Publication:** November 14, 2025
- **URL:** https://www.cognition.ai/blog/devin-annual-performance-review-2025
- **Topics:** 18-month retrospective on Devin's production patterns, failure modes, and lessons.

**Cognition: "Closing the Agent Loop: Devin Autofixes Review Comments"**
- **Publication:** February 10, 2026
- **URL:** https://www.cognition.ai/blog/closing-the-agent-loop-devin-autofixes-review-comments
- **Topics:** Autonomous feedback loop where Devin automatically fixes review comments on its PRs.

**Replit: "Introducing Agent 3: Our Most Autonomous Agent Yet"**
- **Publication:** September 10, 2025
- **URL:** https://blog.replit.com/introducing-agent-3-our-most-autonomous-agent-yet
- **Topics:** 10x more autonomous agent with browser-based self-testing and auto-fix capabilities.

**LinkedIn: "Contextual agent playbooks and tools"**
- **Author:** Ajay Prakash
- **Publication:** January 27, 2026
- **URL:** https://www.linkedin.com/blog/engineering/ai/contextual-agent-playbooks-and-tools-how-linkedin-gave-ai-coding-agents-organizational-context
- **Topics:** How LinkedIn provides AI coding agents with organization-specific context at enterprise scale.

**Stripe: "Can AI agents build real Stripe integrations?"**
- **Authors:** Carol Liang, Kevin Ho
- **Publication:** March 2, 2026
- **URL:** https://stripe.com/blog/can-ai-agents-build-real-stripe-integrations
- **Topics:** Benchmark for AI agents building real Stripe integrations end-to-end.

**Sourcegraph: "A New Era for Sourcegraph: The Intelligence Layer for AI Coding Agents"**
- **Author:** Graham McBain
- **Publication:** February 25, 2026
- **URL:** https://sourcegraph.com/blog/a-new-era-for-sourcegraph-the-intelligence-layer-for-ai-coding-agents-and-developers
- **Topics:** Code intelligence layer that agents rely on for codebase understanding.

**Microsoft Research: "CORPGEN advances AI agents for real work"**
- **Publication:** February 26, 2026
- **URL:** https://www.microsoft.com/en-us/research/blog/corpgen-advances-ai-agents-for-real-work/
- **Topics:** "Digital employees" with GUI automation, hierarchical planning, and memory isolation.

**Microsoft Research: "Agent Lightning: Adding RL to AI agents without code rewrites"**
- **Publication:** December 11, 2025
- **URL:** https://www.microsoft.com/en-us/research/blog/agent-lightning-adding-reinforcement-learning-to-ai-agents-without-code-rewrites/
- **Topics:** Decoupling agent behavior from training, turning each step into RL data.

**OpenAI: "Practices for Governing Agentic AI Systems"**
- **Publication:** December 14, 2023
- **URL:** https://openai.com/index/practices-for-governing-agentic-ai-systems/
- **Topics:** Defining agentic AI systems and governance practices for safe autonomous operation.

---

### 5. Programmatic Tool Calling

#### Research Papers (2023)

**Toolformer: Language Models Can Teach Themselves to Use Tools**
- **Authors:** Timo Schick, Jane Dwivedi-Yu, Roberto Dessì, Roberta Raileanu, Maria Lomeli, Luke Zettlemoyer, Nicola Cancedda, Thomas Scialom
- **Publication:** February 2023
- **URL:** https://arxiv.org/abs/2302.04761
- **Why Relevant:** Framework for learning to use tools via self-supervised learning, enabling LLMs to call external APIs.

#### Documentation

**OpenAI Function Calling**
- **URL:** https://platform.openai.com/docs/guides/gpt/function-calling
- **Description:** Structured tool calling for OpenAI models.
- **Why Relevant:** Official guide for implementing function calling with OpenAI models.

**Anthropic Tool Use**
- **URL:** https://docs.anthropic.com/en/docs/tool-use
- **Description:** Tool use for Claude models.
- **Why Relevant:** Official guide for implementing tool use with Claude models.

**MCP Tool Orchestration**
- **URL:** https://modelcontextprotocol.io/
- **Description:** Open-source standard for connecting AI applications to external systems.
- **Why Relevant:** Standardized protocol for tool orchestration across different AI applications.

#### Best Practices & Patterns

**Tool Selection Strategy**
- Choose tools based on agent capabilities and task requirements
- Implement tool capabilities and descriptions clearly
- Use appropriate tool parameters and return types

**Tool Error Handling**
- Implement robust error handling for tool calls
- Use try-catch patterns and retry mechanisms
- Handle tool failures gracefully with fallback strategies

**Tool Authorization**
- Implement proper security controls for tool access
- Use authentication and authorization for sensitive tools
- Audit and log tool usage for security

**Tool Parallelization**
- Optimize performance through parallel tool calls
- Batch independent tool calls when possible
- Use async/await patterns for concurrent tool execution

#### Production & Engineering Blogs

**Anthropic: "Writing effective tools for agents -- with agents"**
- **Publication:** September 11, 2025
- **URL:** https://www.anthropic.com/engineering/writing-tools-for-agents
- **Topics:** Best practices for designing agent-computer interfaces (ACI) and tool definitions.

**Anthropic: "Introducing advanced tool use on the Claude Developer Platform"**
- **Publication:** November 24, 2025
- **URL:** https://www.anthropic.com/engineering/advanced-tool-use
- **Topics:** Advanced patterns for tool use in production agent systems.

**Anthropic: "The 'think' tool: Enabling Claude to stop and think"**
- **Publication:** March 20, 2025
- **URL:** https://www.anthropic.com/engineering/claude-think-tool
- **Topics:** Extended thinking tool for complex multi-tool orchestration scenarios.

---

### 6. Multi-Agent Systems

#### Research Papers (2023)

**LLM Powered Autonomous Agents (Lilian Weng)**
- **URL:** https://lilianweng.github.io/posts/2023-06-23-agent/
- **Description:** Comprehensive blog on agent architecture.
- **Why Relevant:** Foundational overview of autonomous agent systems and design patterns.

#### Online Courses

**Multi AI Agent Systems with CrewAI**
- **URL:** https://www.deeplearning.ai/short-courses/multi-ai-agent-systems-with-crewai/
- **Platform:** DeepLearning.AI
- **Description:** Master fundamentals of multi-agent systems with CrewAI.

**Practical Multi AI Agents and Advanced Use Cases**
- **URL:** https://www.deeplearning.ai/short-courses/practical-multi-ai-agents-and-advanced-use-cases-with-crewai/
- **Platform:** DeepLearning.AI
- **Description:** Deep dive into advanced multi-agent implementations.

#### Best Practices & Patterns

**Agent Communication Protocols**
- Define clear communication patterns between agents
- Use structured message formats
- Implement message routing and filtering

**Task Distribution**
- Decompose complex tasks across multiple agents
- Use specialized agents for different capabilities
- Implement task queue and scheduling

**Agent Orchestration**
- Use a coordinator agent for complex workflows
- Implement supervisor pattern for task delegation
- Use event-driven architecture for agent coordination

**Conflict Resolution**
- Implement mechanisms to resolve agent conflicts
- Use consensus algorithms for decision making
- Handle competing agent requests gracefully

#### Production & Engineering Blogs

**Anthropic: "How we built our multi-agent research system"**
- **Authors:** Jeremy Hadfield, Barry Zhang, Kenneth Lien, Florian Scholz, Jeremy Fox, Daniel Ford
- **Publication:** June 13, 2025
- **URL:** https://www.anthropic.com/engineering/multi-agent-research-system
- **Topics:** Production multi-agent orchestrator-worker system for Research, including prompt engineering for delegation and reliability challenges.

**Anthropic: "Building a C compiler with a team of parallel Claudes"**
- **Publication:** February 5, 2026
- **URL:** https://www.anthropic.com/engineering/building-c-compiler
- **Topics:** Parallel Claude agents building a C compiler, demonstrating multi-agent task decomposition and coordination.

**Google Research: "Towards a science of scaling agent systems"**
- **Authors:** Yubin Kim, Xin Liu
- **Publication:** January 28, 2026
- **URL:** https://research.google/blog/towards-a-science-of-scaling-agent-systems-when-and-why-agent-systems-work/
- **Topics:** First quantitative scaling principles for multi-agent systems from 180 configurations -- multi-agent helps +81% on parallelizable tasks but degrades -70% on sequential ones.

---

## Planning & Reasoning

### 7. Planning & Reasoning

#### Research Papers (2023)

**Chain of Thought (CoT) Prompting Elicits Reasoning in Large Language Models**
- **Authors:** Jason Wei, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Brian Ichter, Fei Xia, Ed Chi, Quoc Le, Denny Zhou
- **Publication:** January 2023
- **URL:** https://arxiv.org/abs/2201.11903
- **Why Relevant:** Foundational paper introducing chain-of-thought prompting for enhanced reasoning in complex tasks.

**Tree of Thoughts: Deliberate Problem Solving with Large Language Models**
- **Authors:** Shunyu Yao, Jeffrey Zhao, Dian Yu, Izhak Shafran, Yuan Cao, Karthik Narasimhan
- **Publication:** May 2023
- **URL:** https://arxiv.org/abs/2305.10601
- **Why Relevant:** Systematic exploration of reasoning paths through tree-based search and backtracking.

**ReAct: Synergizing Reasoning and Acting in Language Models**
- **Authors:** Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik Narasimhan, Yuan Cao
- **Publication:** October 2022 (Revised March 2023)
- **URL:** https://arxiv.org/abs/2210.03629
- **Why Relevant:** Integrates reasoning and acting for knowledge tasks, enabling LLMs to generate both reasoning traces and task-specific actions.

**Reflexion: Language Agents with Verbal Reinforcement Learning**
- **Authors:** Noah Shinn, Federico Cassano, Edward Grefenstette, Tim Rocktäschel, Yoram Bachrach
- **Publication:** March 2023
- **URL:** https://arxiv.org/abs/2303.11366
- **Why Relevant:** Self-reflection framework for improving agent performance through verbal reinforcement learning.

#### Research Papers (2022-2023)

**LLM+P: Empowering Large Language Models with Optimal Planning Proficiency**
- **Authors:** Qingying Xiao, Kaiwen Wen, Yanchen Deng, Haobo Du, Qianlan Yang, Yuhui Wu, Wenjie Ruan, Chaojie Wang
- **Publication:** April 2023
- **URL:** https://arxiv.org/abs/2304.11477
- **Why Relevant:** Integrates classical planners for long-horizon planning with LLM reasoning.

**Algorithm Distillation**
- **Authors:** H. Jerry Qi, Lulwah Al-Khulaifi, Brian Ichter, J. Z. Shunyu Yao, Karthik Narasimhan, Izhak Shafran, Yuan Cao
- **Publication:** October 2022
- **URL:** https://arxiv.org/abs/2210.14215
- **Why Relevant:** Learn algorithms from trajectories, enabling LLMs to execute complex algorithms.

#### Best Practices

**Prompt Engineering**
- Structure prompts for better reasoning
- Use chain-of-thought prompting for complex tasks
- Implement few-shot learning with examples

**Planning Strategies**
- Design prompts for effective task decomposition
- Use hierarchical planning for complex goals
- Implement subgoal decomposition and tracking

**Multi-step Reasoning**
- Implement complex reasoning chains
- Use tree-of-thoughts for exploring multiple paths
- Implement backtracking and revision strategies

#### Production & Engineering Blogs

**Replit: "Decision-Time Guidance: Keeping Replit Agent Reliable"**
- **Publication:** January 20, 2026
- **URL:** https://blog.replit.com/decision-time-guidance
- **Topics:** Guiding agents during execution using environment-based feedback, improving reliability on long trajectories.

**Cognition: "Introducing SWE-grep and SWE-grep-mini: RL for Multi-Turn, Fast Context Retrieval"**
- **Authors:** Ben Pan, Carlo Baronio, et al.
- **Publication:** October 16, 2025
- **URL:** https://www.cognition.ai/blog/swe-grep
- **Topics:** RL-trained agentic models for parallel multi-turn context retrieval, matching frontier models at 10x less time.

**Google Research: "Teaching LLMs to reason like Bayesians"**
- **Publication:** March 4, 2026
- **URL:** https://research.google/blog/teaching-llms-to-reason-like-bayesians/
- **Topics:** Training LLMs to perform Bayesian reasoning for improved agent decision-making.

**Microsoft Research: "Multimodal RL with agentic verifier for AI agents"**
- **Publication:** January 20, 2026
- **URL:** https://www.microsoft.com/en-us/research/blog/multimodal-reinforcement-learning-with-agentic-verifier-for-ai-agents/
- **Topics:** Argos framework evaluating whether agent reasoning aligns with observations over time.

---

## Web & Browser

### 8. WebMCP Protocol

_See the [Tools & Repositories](#tools--repositories-1) table for all WebMCP GitHub repositories._

---

### 9. Browser Automation Stacks

_See the [Tools & Repositories](#tools--repositories-1) table for all browser automation tools and repositories._

#### Production & Engineering Blogs

**Browserbase: "Building the future of web automation"**
- **Author:** Paul Klein
- **Publication:** June 18, 2025
- **URL:** https://www.browserbase.com/blog/series-b-and-beyond
- **Topics:** Browser infrastructure as an AI primitive, Director.ai and Stagehand Python launch.

**Browserbase: "We built caching into Stagehand. Here's how it works"**
- **Author:** Sameel Arif
- **Publication:** February 24, 2026
- **URL:** https://www.browserbase.com/blog/stagehand-caching
- **Topics:** Caching resolved selectors to skip LLM calls on repeated browser actions, ~80% speedup.

**Browserbase: "Your AI browser is one malicious div away from going rogue"**
- **Author:** Jane Manchun Wong
- **Publication:** February 13, 2026
- **URL:** https://www.browserbase.com/blog/ai-browser-prompt-injection-containment-security
- **Topics:** Prompt injection attacks on AI browser agents and containment via isolated VM sessions.

**Browserbase: "How we built Browserbase Functions"**
- **Authors:** Adam McQuilkin, Viv Nepenthe
- **Publication:** February 10, 2026
- **URL:** https://www.browserbase.com/blog/building-browserbase-functions
- **Topics:** Co-locating browser automation code with the browser via serverless functions to eliminate latency.

**Browserbase: "The best browser automation framework, in every language"**
- **Author:** Nick Sweeting
- **Publication:** January 13, 2026
- **URL:** https://www.browserbase.com/blog/browser-automation-all-languages-with-stagehand
- **Topics:** Stagehand v3 multi-language SDK (Python, Go, Rust, Java, Ruby) with parallel multi-browser support.

**Browserbase: "How Amplitude Transformed Sales Demos with AI-Powered Browser Automation"**
- **Author:** Erika Bricky
- **Publication:** February 23, 2026
- **URL:** https://www.browserbase.com/blog/how-amplitude-transformed-sales-demos-with-browser-automation
- **Topics:** Case study of Amplitude using Browserbase for AI-driven browser automation in sales demos.

**Steel: "Introducing Steel CLI v0.2.0: Browser Automation Built for Agents"**
- **Publication:** 2026
- **URL:** https://steel.dev/blog/steel-cli-and-agent-skill
- **Topics:** CLI and agent skill for running browser workflows returning markdown, screenshots, or PDFs.

**Steel: "Reducing False Positives for Production Agents"**
- **Publication:** 2025
- **URL:** https://steel.dev/blog/production-agents
- **Topics:** Distinguishing legitimate AI agent traffic from malicious bots in production.

**Steel: "How Websites Decide You're Human"**
- **Publication:** 2025
- **URL:** https://steel.dev/blog/anti-bot-defense
- **Topics:** Anti-bot detection layers (network, device, behavioral, challenge) that AI browser agents must navigate.

**Steel: "Profiles: Your Agent's Persistent Identity"**
- **Publication:** 2025
- **URL:** https://steel.dev/blog/profiles
- **Topics:** Persistent browser profiles (auth, cookies, cache) across sessions for authenticated agent access.

**Steel: "Agent Logs: Action Traces for Agent Actions"**
- **Publication:** 2025
- **URL:** https://steel.dev/blog/agent-logs
- **Topics:** Observability for tracing and debugging AI agent actions inside cloud browser sessions.

**TinyFish: "OpenAI Operator scores 43% on hard web tasks. We scored 81%."**
- **Publication:** February 12, 2026
- **URL:** https://www.tinyfish.io/blog/mind2web
- **Topics:** Head-to-head benchmark of TinyFish Mino vs. OpenAI Operator on Mind2Web hard web tasks.

**TinyFish: "Codified Learning: The Backbone of Reliable, Scalable Enterprise Web Agents"**
- **Publication:** September 9, 2025
- **URL:** https://www.tinyfish.io/blog/codified-learning-the-backbone-of-reliable-scalable-enterprise-web-agents
- **Topics:** Converting successful agent runs into deterministic, reusable scripts for enterprise web agents.

**TinyFish: "Proving I'm Human (When I'm Not)"**
- **Publication:** November 8, 2025
- **URL:** https://www.tinyfish.io/blog/proving-i-m-human-when-i-m-not
- **Topics:** How Mino enterprise web agent navigates thousands of anti-bot tests.

**Microsoft Research: "Magentic-UI, an experimental human-centered web agent"**
- **Publication:** May 19, 2025
- **URL:** https://www.microsoft.com/en-us/research/blog/magentic-ui-an-experimental-human-centered-web-agent/
- **Topics:** Human-centered web agent planning and executing browser actions with user oversight.

**Microsoft Research: "Magma: A foundation model for multimodal AI agents"**
- **Publication:** February 25, 2025
- **URL:** https://www.microsoft.com/en-us/research/blog/magma-a-foundation-model-for-multimodal-ai-agents-across-digital-and-physical-worlds/
- **Topics:** Foundation model for agents operating in both digital (browser/GUI) and physical environments.

---

## Operations & Observability

### 10. State Management

#### Documentation

**LangGraph Memory**
- **URL:** https://docs.langchain.com/oss/python/langgraph/memory/
- **Description:** Memory management for stateful agents.
- **Why Relevant:** Comprehensive memory management with checkpointing and persistence.

**LangGraph Checkpointing**
- **URL:** https://docs.langchain.com/oss/python/langgraph/durable-execution
- **Description:** Durable execution and state persistence.
- **Why Relevant:** Enables state persistence across agent executions with checkpointing.

#### Research Papers (2026)

**ReMe: A Dynamic Procedural Memory Framework for Experience-Driven Agent Evolution**
- **Publication:** December 2026
- **URL:** https://arxiv.org/abs/2512.10696
- **Why Relevant:** Experience-driven agent evolution with dynamic procedural memory.

**MemOS: Memory Operating System for AI System**
- **Publication:** January 2026
- **URL:** https://arxiv.org/abs/2507.03724
- **Why Relevant:** Memory operating system for AI systems with efficient memory retrieval and storage.

#### Best Practices & Patterns

**Context Window Management**
- Optimize context usage for efficient token consumption
- Use context compression techniques
- Implement context summarization and pruning

**Memory Compression**
- Implement efficient storage and retrieval
- Use compression algorithms for long-term memory
- Implement hierarchical memory storage

**State Persistence**
- Implement reliable state management
- Use checkpointing for fault tolerance
- Implement state synchronization across agents

#### Production & Engineering Blogs

**LangChain: "How we built Agent Builder's memory system"**
- **Publication:** February 21, 2026
- **URL:** https://blog.langchain.dev/how-we-built-agent-builders-memory-system/
- **Topics:** Virtual filesystem backed by Postgres for agent state, mapping to COALA paper's memory taxonomy.

**Letta: "Conversations: Shared Agent Memory across Concurrent Experiences"**
- **Publication:** January 21, 2026
- **URL:** https://letta.com/blog/conversations
- **Topics:** Conversations API for managing shared state across parallel agent experiences.

**Letta: "Introducing Context Repositories: Git-based Memory for Coding Agents"**
- **Publication:** February 12, 2026
- **URL:** https://letta.com/blog/context-repositories
- **Topics:** Git-based versioning for agent state management.

---

### 11. Observability & Debugging

#### Documentation

**Phoenix Documentation**
- **URL:** https://arize.com/docs/phoenix
- **Integrations:**
  - OpenAI: https://arize.com/docs/phoenix/tracing/integrations-tracing/openai
  - LangChain: https://arize.com/docs/phoenix/tracing/integrations-tracing/langchain
  - LlamaIndex: https://arize.com/docs/phoenix/tracing/integrations-tracing/llamaindex
  - Anthropic: https://arize.com/docs/phoenix/tracing/integrations-tracing/anthropic
  - Google GenAI: https://arize.com/docs/phoenix/tracing/integrations-tracing/google-gen-ai
  - AWS Bedrock: https://arize.com/docs/phoenix/tracing/integrations-tracing/bedrock
  - Vercel AI SDK: https://arize.com/docs/phoenix/tracing/integrations-tracing/vercel-ai-sdk
  - CrewAI: https://arize.com/docs/phoenix/tracing/integrations-tracing/crewai
  - DSPy: https://arize.com/docs/phoenix/tracing/integrations-tracing/dspy
  - LangGraph: https://arize.com/docs/phoenix/tracing/integrations-tracing/langgraph
  - Mastra: https://arize.com/docs/phoenix/integrations/typescript/mastra

#### Best Practices & Patterns

**Structured Logging**
- Use structured logs for better debugging
- Implement consistent log formats
- Use log levels appropriately

**Span Management**
- Implement efficient span management
- Use span context for tracing
- Implement span sampling for high-volume systems

**Trace Sampling**
- Use sampling for high-volume systems
- Implement intelligent sampling strategies
- Use span filtering for relevant traces

#### Production & Engineering Blogs

**Braintrust: "The Three Pillars of AI Observability"**
- **Author:** Ankur Goyal
- **Publication:** November 18, 2025
- **URL:** https://www.braintrust.dev/blog/three-pillars-ai-observability
- **Topics:** Redefining observability for AI as traces, evals, and annotation.

**Braintrust: "Building Observable AI Agents with Temporal"**
- **Publication:** January 20, 2026
- **URL:** https://www.braintrust.dev/blog/temporal-braintrust-integration
- **Topics:** Combining Temporal's durable workflow engine with Braintrust tracing for fault-tolerant agents.

**LangChain: "Agent Observability Powers Agent Evaluation"**
- **Publication:** February 2026
- **URL:** https://blog.langchain.dev/agent-observability-powers-agent-evaluation/
- **Topics:** Connecting observability traces to systematic evaluation workflows.

**Langfuse: "Trace Complex LLM Applications with the Langfuse Decorator"**
- **Authors:** Marc Klingen, Hassie Pakzad
- **Publication:** April 24, 2024
- **URL:** https://langfuse.com/blog/2024-04-python-decorator
- **Topics:** `@observe()` decorator for tracing agent workflows -- design decisions, async safety, interoperability.

**Honeycomb: "How Honeycomb Supercharges OpenTelemetry for AI"**
- **Author:** Fahim Zaman
- **Publication:** February 6, 2026
- **URL:** https://www.honeycomb.io/blog/how-honeycomb-supercharges-opentelemetry-for-ai
- **Topics:** Software instrumentation changes for AI-generated code and agent features.

**Honeycomb: "AI in Production Is Growing Faster Than We Can Trust It"**
- **Author:** Fahim Zaman
- **Publication:** January 23, 2026
- **URL:** https://www.honeycomb.io/blog/ai-in-production-is-growing-faster-than-we-can-trust-it
- **Topics:** Dedicated AI observability for production trust-building.

**Honeycomb: "Observability in a World of AI-Generated Code"**
- **Author:** Charity Majors
- **Publication:** February 11, 2026
- **URL:** https://www.honeycomb.io/blog/honeycomb-10-year-manifesto-part-1
- **Topics:** How observability must evolve for AI-generated code from first principles.

**Honeycomb: "Measuring Claude Code ROI and Adoption in Honeycomb"**
- **Author:** Mae Capozzi
- **Publication:** January 22, 2026
- **URL:** https://www.honeycomb.io/blog/measuring-claude-code-roi-adoption-honeycomb
- **Topics:** Using OpenTelemetry to send Claude Code telemetry to Honeycomb for ROI measurement.

**Humanloop: "What is LLM Observability and Monitoring?"**
- **Author:** Conor Kelly
- **Publication:** March 31, 2025
- **URL:** https://humanloop.com/blog/llm-monitoring
- **Topics:** Five pillars of LLM observability (model performance, data quality, bias, system perf, UX).

**Arize: "How America First Credit Union Built a GenAI Decision Explainer"**
- **Publication:** February 2026
- **URL:** https://arize.com/blog/how-america-first-credit-union-built-a-genai-decision-explainer-with-tracing-that-scales/
- **Topics:** Production case study of GenAI with end-to-end tracing at a financial institution.

**LlamaIndex: "Observability in Agentic Document Workflows"**
- **Publication:** November 19, 2025
- **URL:** https://www.llamaindex.ai/blog/observability-in-agentic-document-workflows
- **Topics:** OpenTelemetry tracing for multi-step agent document pipelines.

---

### 12. Evaluation & Benchmarking

#### Documentation

**OpenAI Evals Documentation**
- **URL:** https://platform.openai.com/docs/guides/evals
- **Building an Eval:** https://github.com/openai/evals/blob/main/docs/build-eval.md
- **Running Evals:** https://github.com/openai/evals/blob/main/docs/run-evals.md
- **Eval Templates:** https://github.com/openai/evals/blob/main/docs/eval-templates.md

**RAGAS Documentation**
- **URL:** https://docs.ragas.io
- **Metrics Overview:** https://docs.ragas.io/en/latest/concepts/metrics/overview/
- **Available Metrics:** https://docs.ragas.io/en/latest/concepts/metrics/available_metrics/
- **Test Data Generation:** https://docs.ragas.io/en/latest/concepts/test_data_generation/
- **Integrations:** LangChain, LangGraph, LlamaIndex, LangSmith, Arize, Haystack, Griptape

#### Academic Benchmarks

**CoQA (Conversational Question Answering)**
- **URL:** https://stanfordnlp.github.io/coqa/
- **Description:** Conversational QA dataset for evaluating question answering systems.

**LAMBADA**
- **URL:** https://arxiv.org/abs/1712.03718
- **Description:** Language modeling benchmark for evaluating text prediction.

**MMLU (Massive Multitask Language Understanding)**
- **URL:** https://github.com/hendrycks/testbed
- **Description:** Multitask understanding benchmark covering 57 subjects.

**API-Bank: A Benchmark for Tool-Augmented LLMs**
- **URL:** https://arxiv.org/abs/2304.08244
- **Description:** Benchmark for evaluating tool-augmented LLM capabilities.

#### Best Practices & Patterns

**Evaluation Metrics**
- Define appropriate metrics for agent tasks
- Use task-specific evaluation criteria
- Combine multiple metrics for comprehensive evaluation

**A/B Testing**
- Compare different models systematically
- Use statistical significance testing
- Implement controlled experiments

**Human Evaluation**
- Incorporate human feedback in evaluation
- Use expert annotation for quality assessment
- Implement evaluation pipelines with human review

#### Production & Engineering Blogs

**Applied LLMs: "What We've Learned From A Year of Building with LLMs"**
- **Authors:** Eugene Yan, Bryan Bischof, Charles Frye, Hamel Husain, Jason Liu, Shreya Shankar
- **Publication:** June 8, 2024
- **URL:** https://applied-llms.org/
- **Topics:** Seminal practitioner guide covering eval strategies, LLM-as-Judge pitfalls, HITL design, guardrails, and hallucination mitigation.

**Hamel Husain: "Your AI Product Needs Evals"**
- **Author:** Hamel Husain
- **Publication:** March 29, 2024
- **URL:** https://hamel.dev/blog/posts/evals/index.html
- **Topics:** Why evals are critical, with a practical multi-level framework for AI product teams.

**Hamel Husain: "Using LLM-as-a-Judge For Evaluation: A Complete Guide"**
- **Author:** Hamel Husain
- **Publication:** October 29, 2024
- **URL:** https://hamel.dev/blog/posts/llm-judge/index.html
- **Topics:** End-to-end LLM-as-Judge evaluation, agreement with humans improved from 68% to 94%.

**Hamel Husain: "LLM Evals: Everything You Need to Know"**
- **Author:** Hamel Husain
- **Publication:** January 15, 2026
- **URL:** https://hamel.dev/blog/posts/evals-faq/index.html
- **Topics:** Comprehensive FAQ covering eval questions and anti-patterns from consulting 500+ companies.

**Hamel Husain: "A Field Guide to Rapidly Improving AI Products"**
- **Author:** Hamel Husain
- **Publication:** March 24, 2025
- **URL:** https://hamel.dev/blog/posts/field-guide/index.html
- **Topics:** Using evals and data analysis to rapidly iterate on AI product quality in production.

**Hamel Husain: "Evals Skills for Coding Agents"**
- **Author:** Hamel Husain
- **Publication:** March 2, 2026
- **URL:** https://hamel.dev/blog/posts/evals-skills/index.html
- **Topics:** Evaluation methodology for coding agents covering benchmarks, harness engineering, and scoring.

**Braintrust: "Evaluating Agents"**
- **Author:** Ornella Altunyan
- **Publication:** January 22, 2025
- **URL:** https://www.braintrust.dev/blog/evaluating-agents
- **Topics:** Concrete scorer implementations (code-based, LLM-as-judge, autoevals) for every agentic pattern.

**Braintrust: "Five Hard-Learned Lessons About AI Evals"**
- **Publication:** July 17, 2025
- **URL:** https://www.braintrust.dev/blog/five-lessons-evals
- **Topics:** Production lessons including why A/B testing fails for AI and building eval feedback loops.

**LangChain: "Evaluating Skills"**
- **Author:** Robert Xu
- **Publication:** March 2026
- **URL:** https://blog.langchain.dev/evaluating-skills/
- **Topics:** Evaluating skills for coding agents including benchmark design and harness engineering.

**LangChain: "monday Service + LangSmith: Building a Code-First Evaluation Strategy"**
- **Publication:** March 2026
- **URL:** https://blog.langchain.dev/customers-monday/
- **Topics:** monday.com building eval-driven development for production service agents using LangSmith.

**Deepchecks: "Know Your Agent (KYA): From Zero to a Full Strengths & Weaknesses Report"**
- **Author:** Philip Tannor
- **Publication:** February 24, 2026
- **URL:** https://deepchecks.com/know-your-agent-strengths-weaknesses-report/
- **Topics:** Automated agent evaluation generating comprehensive strengths/weaknesses reports.

**Deepchecks: "LLM-as-a-Judge Calibration: When Automated Evaluation Goes Wrong"**
- **Author:** Yaron Friedman
- **Publication:** March 5, 2026
- **URL:** https://deepchecks.com/llm-judge-calibration-automated-issues/
- **Topics:** Failure modes when LLM-as-Judge evaluators produce miscalibrated scores.

**Humanloop: "LLM as a Judge"**
- **Author:** Conor Kelly
- **Publication:** May 4, 2025
- **URL:** https://humanloop.com/blog/llm-as-a-judge
- **Topics:** LLM-as-Judge methodology, benefits, challenges, and best practices.

**Arize: "How TheFork Leverages Online Evals To Boost Conversions"**
- **Publication:** December 2025
- **URL:** https://arize.com/blog/how-thefork-leverages-online-evals-to-boost-conversions-with-arize-ax-on-aws/
- **Topics:** Production case study using online evaluation to improve business conversion metrics.

---

### 13. Error Handling & Recovery

#### Best Practices & Patterns

**Retry Mechanisms**
- Exponential backoff with jitter
- Implement configurable retry strategies
- Use retry decorators and middleware

**Circuit Breaker Patterns**
- Detect cascading failures and switch approaches
- Implement circuit breaker state machine
- Use timeout and fallback mechanisms

**Graceful Degradation**
- Gradually reduce resource usage on failures
- Implement fallback strategies
- Use degraded mode for critical operations

**Error Classification**
- Categorize errors by type for appropriate handling
- Implement error handling by error category
- Use error codes and messages for debugging

**Fallback Strategies**
- Implement alternative approaches when tools fail
- Use multiple tool providers
- Implement caching for fallback results

**Idempotency Keys**
- Prevent duplicate operations
- Use idempotency keys for critical operations
- Implement deduplication logic

#### Production & Engineering Blogs

**Braintrust: "Resilient Observability by Design"**
- **Publication:** April 3, 2025
- **URL:** https://www.braintrust.dev/blog/resilient-design
- **Topics:** Building fault-tolerant observability infrastructure that handles failures without losing trace data.

**Braintrust: "Debugging Ralph Wiggum with Braintrust Logs"**
- **Publication:** January 13, 2026
- **URL:** https://www.braintrust.dev/blog/ralph-wiggum-debugging
- **Topics:** Practical debugging walkthrough using production logs to diagnose LLM agent errors.

**Hamel Husain: "Debugging AI With Adversarial Validation"**
- **Author:** Hamel Husain
- **Publication:** April 12, 2024
- **URL:** https://hamel.dev/blog/posts/drift/index.html
- **Topics:** Adversarial validation to detect distribution drift and debug AI system failures.

**Deepchecks: "LLM Hallucination Detection and Mitigation: Best Techniques"**
- **Author:** Yaron Friedman
- **Publication:** February 25, 2026
- **URL:** https://deepchecks.com/llm-hallucination-detection-and-mitigation-best-techniques/
- **Topics:** Detecting and mitigating hallucinations in production LLM systems.

**Deepchecks: "Retrieval Quality vs. Answer Quality: Why RAG Evaluation Often Fails"**
- **Author:** Amos Rimon
- **Publication:** February 26, 2026
- **URL:** https://deepchecks.com/retrieval-vs-answer-quality-rag-evaluation/
- **Topics:** Distinguishing retrieval errors from generation errors with diagnostic strategies.

---

## Safety & Human Interaction

### 14. Human-in-the-Loop

#### Documentation

**LangGraph Interrupts**
- **URL:** https://docs.langchain.com/oss/python/langgraph/interrupts/
- **Description:** Human-in-the-loop support in LangGraph.
- **Why Relevant:** Enables human intervention and approval in agent workflows.

**OpenAI Human Feedback**
- **URL:** https://platform.openai.com/docs/guides/human-feedback
- **Description:** Human-in-the-loop alignment for AI systems.
- **Why Relevant:** Official guide for implementing human feedback loops.

**Anthropic Approvals**
- **URL:** https://docs.anthropic.com/en/docs/approvals
- **Description:** Evaluation with human feedback integration.
- **Why Relevant:** Anthropic's approach to human-in-the-loop evaluation.

#### Best Practices & Patterns

**Approval Workflows**
- Design approval mechanisms for agent actions
- Implement approval gates for critical operations
- Use approval queues for human review

**Feedback Loops**
- Continuous improvement through human feedback
- Implement feedback collection mechanisms
- Use feedback for model fine-tuning

**Override Mechanisms**
- Allow human intervention in agent decisions
- Implement manual override capabilities
- Use kill switches for emergency shutdown

**User Interface Design**
- Clear communication for human operators
- Implement intuitive approval interfaces
- Use progress indicators and status updates

#### Production & Engineering Blogs

**Braintrust: "Evals Are a Team Sport: How We Built Loop"**
- **Publication:** November 25, 2025
- **URL:** https://www.braintrust.dev/blog/collaborative-evals-loop
- **Topics:** Collaborative human review workflows where product teams and domain experts evaluate AI outputs.

**Braintrust: "Turn Production Data into Better AI with Loop"**
- **Publication:** November 24, 2025
- **URL:** https://www.braintrust.dev/blog/loop
- **Topics:** Turning production traces into curated datasets via human annotation for continuous feedback.

**Anthropic: "Measuring AI Agent Autonomy in Practice"**
- **Publication:** February 18, 2026
- **URL:** https://www.anthropic.com/research/measuring-agent-autonomy
- **Topics:** Measuring and calibrating AI agent autonomy levels for designing appropriate human oversight.

**Anthropic: "Disempowerment Patterns in Real-World AI Usage"**
- **Publication:** January 28, 2026
- **URL:** https://www.anthropic.com/research/disempowerment-patterns
- **Topics:** How AI usage can disempower human users and patterns requiring HITL safeguards.

**Humanloop: "AI Is Blurring the Line Between PMs and Engineers"**
- **Author:** Raza Habib
- **Publication:** February 25, 2025
- **URL:** https://humanloop.com/blog/ai-is-blurring-the-lines-between-pms-and-engineers
- **Topics:** HITL as first-class product concern, PMs and domain experts driving AI product creation.

---

### 15. Safety & Alignment

#### Research Papers (2023)

**Constitutional AI: Harmlessness from Large Language Models**
- **URL:** https://arxiv.org/abs/2307.07407
- **Publication:** July 2023
- **Why Relevant:** Foundational paper on constitutional AI principles for ensuring AI harmlessness and alignment.

#### Documentation

**Anthropic AI Safety**
- **URL:** https://www.anthropic.com/research/team/alignment
- **Description:** Safety measures for AI systems.
- **Why Relevant:** Anthropic's research on AI safety and alignment.

**AI Safety Research**
- **URL:** https://www.alignresearch.org
- **Description:** Research organizations working on AI safety.
- **Why Relevant:** Comprehensive AI safety research resources.

#### Best Practices & Patterns

**Safety Guidelines**
- Safety best practices for AI development
- Implement content filtering and moderation
- Use safety classifiers and guardrails

**Risk Assessment**
- Systematic risk evaluation
- Implement risk scoring and mitigation
- Use risk matrices for decision making

**Adversarial Testing**
- Testing against adversarial attacks
- Implement red teaming exercises
- Use adversarial examples for robustness testing

#### Production & Engineering Blogs

**Anthropic: "Constitutional Classifiers: Defending Against Universal Jailbreaks"**
- **Publication:** February 3, 2025
- **URL:** https://www.anthropic.com/research/constitutional-classifiers
- **Topics:** Classifiers filtering majority of jailbreaks, withstood 3,000+ hours of red teaming.

**Anthropic: "Alignment Faking in Large Language Models"**
- **Publication:** December 18, 2024
- **URL:** https://www.anthropic.com/research/alignment-faking
- **Topics:** First empirical demonstration of alignment faking without explicit training.

**Anthropic: "The Persona Selection Model"**
- **Publication:** February 23, 2026
- **URL:** https://www.anthropic.com/research/persona-selection-model
- **Topics:** How models select behavioral personas, ensuring safe and consistent agent behavior.

**OpenAI: "Updated Preparedness Framework"**
- **Publication:** April 15, 2025
- **URL:** https://openai.com/index/updating-our-preparedness-framework/
- **Topics:** Framework for evaluating catastrophic risks from frontier models.

**OpenAI: "An Update on Disrupting Deceptive Uses of AI"**
- **Publication:** October 9, 2024
- **URL:** https://openai.com/global-affairs/an-update-on-disrupting-deceptive-uses-of-ai/
- **Topics:** Threat intelligence disrupting covert influence operations and deceptive AI usage.

**Guardrails AI: "Guardrails AI and NVIDIA NeMo Guardrails"**
- **Publication:** September 25, 2025
- **URL:** https://www.guardrailsai.com/blog/nemoguardrails-integration
- **Topics:** Layered safety covering PII, toxicity, and output quality in production.

**Guardrails AI: "Introducing Snowglobe"**
- **Publication:** August 14, 2025
- **URL:** https://www.guardrailsai.com/blog/intro
- **Topics:** Simulation environment testing how LLM applications respond to real-world user behavior.

**Guardrails AI: "Scaling AI Safety Testing for Educational Applications"**
- **Publication:** August 13, 2025
- **URL:** https://www.guardrailsai.com/blog/scaling-ai-safety-testing
- **Topics:** Safeguarding chatbot interactions across diverse student personas.

**Guardrails AI: "Introducing the AI Guardrails Index"**
- **Publication:** February 12, 2025
- **URL:** https://www.guardrailsai.com/blog/introducing-the-ai-guardrails-index
- **Topics:** Comprehensive index cataloging available AI guardrails across safety, quality, and compliance.

**Deepchecks: "Prompt Injection vs. Jailbreaks: Key Differences"**
- **Author:** Amos Rimon
- **Publication:** January 8, 2026
- **URL:** https://deepchecks.com/prompt-injection-vs-jailbreaks-key-differences/
- **Topics:** Detection and mitigation strategies for prompt injection attacks vs. jailbreaks.

---

## Capabilities

### 16. Skills & Capabilities

#### Official Anthropic Resources (2025)

**Claude Skills Official Announcement**
- **Publication:** October 16, 2025
- **URL:** https://www.anthropic.com/news/skills
- **Why Relevant:** Official announcement of Claude Skills feature.

**Skills Explained (Official)**
- **Publication:** November 13, 2025
- **URL:** https://claude.com/blog/skills-explained
- **Why Relevant:** Official guide explaining Claude Skills concepts and usage.

**Agent Skills Standard**
- **URL:** http://agentskills.io
- **Description:** Specification for agent skills.
- **Why Relevant:** Standard specification for defining agent skills.

#### Documentation

**Claude Developer Platform**
- **URL:** https://docs.claude.com/
- **Description:** Main documentation for Claude developer platform.
- **What are Skills?:** https://support.claude.com/en/articles/12512176-what-are-skills
- **Using Skills:** https://support.claude.com/en/articles/12512180-using-skills-in-claude
- **Creating Custom Skills:** https://support.claude.com/en/articles/12512198-creating-custom-skills
- **Skills API Quickstart:** https://docs.claude.com/en/api/skills-guide#creating-a-skill

#### Research Papers (2026)

**KAPSO: A Knowledge-grounded framework for Autonomous Program Synthesis and Optimization**
- **Authors:** Alireza Nadafian, Alireza Mohammadshahi, Majid Yazdani
- **Publication:** January 31, 2026
- **URL:** https://arxiv.org/abs/2601.21526
- **Why Relevant:** Modular framework for autonomous program synthesis with git-native experimentation engine, knowledge system ingesting heterogeneous sources, and cognitive memory layer with episodic store of reusable lessons.

**CoWork-X: Experience-Optimized Co-Evolution for Multi-Agent Collaboration System**
- **Authors:** Zexin Lin, Jiachen Yu, Haoyang Zhang, Yuzhao Li, Zhonghang Li, Yujiu Yang, Junjie Wang, Xiaoqiang Ji
- **Publication:** February 4, 2026
- **URL:** https://arxiv.org/abs/2602.05004
- **Why Relevant:** Casts peer collaboration as closed-loop optimization with Skill-Agent executing via HTN-based skill retrieval from structured skill library, and Co-Optimizer performing patch-style skill consolidation.

#### Blog Posts (2025)

**Simon Willison: "Claude Skills are awesome, maybe a bigger deal than MCP"**
- **Publication:** October 16, 2025
- **URL:** https://simonwillison.net/2025/Oct/16/claude-skills/
- **Why Relevant:** Analysis of Claude Skills significance and impact.

**Jesse Vincent: "Superpowers"**
- **Publication:** October 9, 2025
- **URL:** https://blog.fsck.com/2025/10/09/superpowers/
- **Why Relevant:** Introduction to superpowers concept for Claude Skills.

**Jesse Vincent: "Naming Claude Plugins"**
- **Publication:** October 23, 2025
- **URL:** https://blog.fsck.com/2025/10/23/naming-claude-plugins/
- **Why Relevant:** Best practices for naming Claude skills/plugins.

**Anthropic: "Equipping Agents for the Real World with Agent Skills"**
- **Publication:** October 2025
- **URL:** https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills
- **Why Relevant:** Technical deep dive on agent skills architecture.

**Vercel: "Agent skills explained: An FAQ"**
- **Publication:** January 26, 2026
- **URL:** https://vercel.com/blog/agent-skills-explained-an-faq
- **Why Relevant:** Compares Skills to MCP, explaining trade-offs in security, reliability, and prompt-tuned control.

**LlamaIndex: "Skills vs MCP tools for agents: when to use what"**
- **Authors:** Clelia Astra Bertelli, Tuana Celik
- **Publication:** February 3, 2026
- **URL:** https://www.llamaindex.ai/blog/skills-vs-mcp-tools-for-agents-when-to-use-what
- **Why Relevant:** Practical comparison of MCP tools vs Skills based on experience building LlamaAgents Builder.

---

## Appendix

### Tools & Repositories

All tools, SDKs, libraries, and repositories referenced throughout this document are consolidated below.

#### Memory Systems

| Name | URL | Description |
|------|-----|-------------|
| MCP Memory Server | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) | Knowledge graph-based persistent memory system for AI agents |
| Elasticsearch Memory | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/elastic-search-memory) | Persistent memory with hierarchical categorization and semantic search |
| Neo4j Agent Memory | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/neo4j-agent-memory) | Memory management using Neo4j knowledge graphs |
| LangGraph Memory | [Docs](https://docs.langchain.com/oss/python/langgraph/memory) | Memory management for stateful agents with checkpointing |
| Mem0 | [arXiv](https://arxiv.org/abs/2507.03724) | Memory operating system for large models |

#### Sandboxes & Isolation

| Name | URL | Description |
|------|-----|-------------|
| E2B | [GitHub](https://github.com/e2b-dev/E2B) | Open-source secure sandboxes for code execution with real-time collaboration |
| gVisor | [GitHub](https://github.com/google/gvisor) | Application kernel for containers providing secure isolation boundary |
| Firecracker | [GitHub](https://github.com/firecracker-microvm/firecracker) | Lightweight microVMs with 125ms startup and 5 MiB memory overhead |
| Docker-in-Docker | [GitHub](https://github.com/docker-in-docker) | Docker-in-Docker for secure containerization |
| Kata Containers | [GitHub](https://github.com/kata-containers/documentation/wiki/Initial-release-of-Kata-Containers-with-Firecracker-support) | Kata Containers with Firecracker support |
| Flintlock | [GitHub](https://github.com/liquidmetal-dev/flintlock) | Firecracker-based container runtime |
| Firecracker-containerd | [GitHub](https://github.com/firecracker-microvm/firecracker-containerd) | containerd integration for Firecracker |

#### MCP SDKs & Libraries

| Name | URL | Description |
|------|-----|-------------|
| MCP TypeScript SDK | [GitHub](https://github.com/modelcontextprotocol/typescript-sdk) | Official TypeScript implementation (11.8k stars) |
| MCP Python SDK | [GitHub](https://github.com/modelcontextprotocol/python-sdk) | Official Python implementation (22k stars) |
| MCP Go SDK | [GitHub](https://github.com/modelcontextprotocol/go-sdk) | Official Go implementation (4k stars) |
| MCP C# SDK | [GitHub](https://github.com/modelcontextprotocol/csharp-sdk) | Official C# implementation (4k stars) |
| MCP Java SDK | [GitHub](https://github.com/modelcontextprotocol/java-sdk) | Official Java implementation |
| MCP Kotlin SDK | [GitHub](https://github.com/modelcontextprotocol/kotlin-sdk) | Official Kotlin implementation |
| MCP PHP SDK | [GitHub](https://github.com/modelcontextprotocol/php-sdk) | Official PHP implementation |
| MCP Ruby SDK | [GitHub](https://github.com/modelcontextprotocol/ruby-sdk) | Official Ruby implementation |
| MCP Rust SDK | [GitHub](https://github.com/modelcontextprotocol/rust-sdk) | Official Rust implementation (3.1k stars) |
| MCP Swift SDK | [GitHub](https://github.com/modelcontextprotocol/swift-sdk) | Official Swift implementation |

#### MCP NPM Packages

| Package | Description |
|---------|-------------|
| `@modelcontextprotocol/server` | Build MCP servers (requires zod v4) |
| `@modelcontextprotocol/client` | Build MCP clients (requires zod v4) |
| `@modelcontextprotocol/node` | Node.js Streamable HTTP transport wrapper |
| `@modelcontextprotocol/express` | Express helpers with Host header validation |
| `@modelcontextprotocol/hono` | Hono helpers with JSON body parsing and validation |

#### MCP Servers

| Name | URL | Description |
|------|-----|-------------|
| MCP Servers (Reference) | [GitHub](https://github.com/modelcontextprotocol/servers) | Reference implementations (80.2k stars) |
| MCP Inspector | [GitHub](https://github.com/modelcontextprotocol/inspector) | Visual testing tool for MCP servers (8.9k stars) |
| GitHub MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/github) | Official GitHub integration |
| Notion MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/notion) | Notion integration |
| Slack MCP | [GitHub](https://github.com/Zencoder/zencoder-mcp-server) | Slack messaging and channel management |
| Filesystem MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | Secure file operations |
| Memory MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) | Knowledge graph-based persistent memory |
| Brave Search MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search) | Web search integration |
| Puppeteer MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer) | Browser automation via Puppeteer |
| PostgreSQL MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) | PostgreSQL database integration |
| SQLite MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/sqlite) | SQLite database integration |
| Sequential Thinking MCP | [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/sequential-thinking) | Chain-of-thought reasoning |

#### Agent Frameworks & Orchestration

| Name | URL | Description |
|------|-----|-------------|
| LangGraph | [GitHub](https://github.com/langchain-ai/langgraph) | Graph-based framework for stateful agents with control flow and memory |
| LangGraph.js | [GitHub](https://github.com/langchain-ai/langgraphjs) | JavaScript/TypeScript implementation of LangGraph |
| CrewAI | [GitHub](https://github.com/joaomdmcdonald/crewAI) | Role-playing autonomous agent framework with crew-based collaboration |
| AutoGPT | [GitHub](https://github.com/Significant-Gravitas/Auto-GPT) | Autonomous agent for complex tasks |
| BabyAGI | [GitHub](https://github.com/yoheinakajima/babyagi) | Task management and autonomous agent framework |
| GPT-Engineer | [GitHub](https://github.com/AntonOsika/gpt-engineer) | Software development autonomous agent |
| OpenClaw Multi-Agent Team | [GitHub](https://github.com/Richchen-maker/openclaw-multi-agent-team) | Multi-agent team framework with Blackboard coordination (31 stars) |
| Agent Protocol | [Website](https://agentprotocol.ai/) | Standard for agent communication and interoperability |
| LangChain Deep Agents | [GitHub](https://github.com/langchain-ai/deepagents) | LangChain's advanced agent framework with planning capabilities |
| AgentScope | [GitHub](https://github.com/agentscope-ai/agentscope) | Multi-agent simulation framework with evaluation capabilities |
| LangChain | [GitHub](https://github.com/langchain-ai/langchain) | Comprehensive tool use patterns and integrations |
| Toolformer | [GitHub](https://github.com/Shinn93/toolformer) | Reference implementation of the Toolformer paper |

#### Observability & Evaluation

| Name | URL | Description |
|------|-----|-------------|
| Phoenix | [GitHub](https://github.com/Arize-ai/phoenix) | Open-source AI Observability & Evaluation platform (8.7k stars) |
| LangSmith | [Website](https://smith.langchain.com/) | LangChain's observability and evaluation platform |
| Weights & Biases | [Website](https://wandb.ai/) | Experiment tracking for ML models |
| AgentOps | [Website](https://www.agentops.ai/) | Observability for AI agents |
| OpenTelemetry | [GitHub](https://github.com/open-telemetry/open-telemetry) | Open-source observability framework |
| OpenAI Evals | [GitHub](https://github.com/openai/evals) | Framework for evaluating LLMs (17.9k stars) |
| RAGAS | [GitHub](https://github.com/vibrantlabsai/ragas) | Evaluation framework for RAG systems (12.8k stars) |
| AgentEvals | [GitHub](https://github.com/langchain-ai/agentevals) | Agent evaluation framework with pytest/vitest integration (489 stars) |
| Deepeval | [GitHub](https://github.com/confident-ai/deepeval) | External evaluator |
| Cleanlab | [Website](https://cleanlab.ai/) | Data quality and evaluation |

#### Safety & Guardrails

| Name | URL | Description |
|------|-----|-------------|
| NVIDIA NeMo Guardrails | [GitHub](https://github.com/NVIDIA/NeMo-Guardrails) | Safety guardrails framework for AI applications |
| AI Safety Kits | [GitHub](https://github.com/aisafetykit/aisafetykit) | Libraries for AI safety evaluation |

#### WebMCP Protocol

| Name | URL | Description |
|------|-----|-------------|
| WebMCP Music Composer | [GitHub](https://github.com/Leanmcp-Community/music-composer-webmcp) | Functional demonstration of WebMCP Protocol (40 stars) |
| WebMCP Playground | [GitHub](https://github.com/WebMCP-org/webmcp-sh) | Web-based MCP playground for testing (10 stars) |
| WebMCP Wix Integration | [GitHub](https://github.com/Startuvit/webmcp) | Wix App with WebMCP protocol support |
| WebMCP WordPress Plugin | [GitHub](https://github.com/fellyph/webmcp-plugin) | WordPress plugin exposing site content via MCP |
| WebMCP CDP Tooling Suite | [GitHub](https://github.com/tech-sumit/webmcp-cdp) | Node.js library for WebMCP tools in Chrome via CDP |
| WebMCP Demo Apps | [GitHub](https://github.com/SrinivasanTarget/WebMCP-demo) | Multiple demonstration apps showcasing WebMCP |

#### Browser Automation

| Name | URL | Description |
|------|-----|-------------|
| PinchTab | [GitHub](https://github.com/pinchtab/pinchtab) | Browser control for AI agents - 12MB Go binary, HTTP API (4.9k stars) |
| PinchTab MCP Wrapper | [GitHub](https://github.com/BDuba/pinchtab-mcp-wrapper) | Token-efficient browser automation MCP server |
| PinchTab MCP (Ai-firelab) | [GitHub](https://github.com/Ai-firelab/mcp-pinchtab) | MCP server for PinchTab |
| PinchTab MCP (Domci) | [GitHub](https://github.com/domci/pinchtab-mcp) | MCP stdio server for PinchTab |
| PinchTab Skill | [GitHub](https://github.com/polly3223/pinchtab-skill) | Browser automation via PinchTab HTTP API |
| icewm/pinchtab | [GitHub](https://github.com/icewm/pinchtab) | Lightweight HTTP browser bridge for AI automation |
| Playwright Skill | [GitHub](https://github.com/lackeyjb/playwright-skill) | Browser automation using Playwright |
| TinyFish BLS-Premium | [GitHub](https://github.com/gitoutofhere7/BLS-Premium) | TinyFish browser automation for price tracking |

#### Skills & Capabilities - Awesome Lists

| Name | Stars | URL | Description |
|------|-------|-----|-------------|
| hesreallyhim/awesome-claude-code | 26.4k | [GitHub](https://github.com/hesreallyhim/awesome-claude-code) | Skills, hooks, slash-commands, agent orchestrators for Claude Code |
| sickn33/antigravity-awesome-skills | 20.4k | [GitHub](https://github.com/sickn33/antigravity-awesome-skills) | 1000+ agentic skills for Claude Code/Antigravity/Cursor |
| Marketing Skills | 11.2k | [GitHub](https://github.com/coreyhaines31/marketingskills) | Marketing skills: CRO, copywriting, SEO, analytics |
| VoltAgent/awesome-agent-skills | 9.3k | [GitHub](https://github.com/VoltAgent/awesome-agent-skills) | 500+ agent skills from official dev teams and community |
| OpenSkills | 8.8k | [GitHub](https://github.com/numman-ali/openskills) | Universal skills loader for AI coding agents |
| AI Research Skills | 4.4k | [GitHub](https://github.com/Orchestra-Research/AI-Research-SKILLs) | AI research and engineering skills |
| heilcheng/awesome-agent-skills | 2.7k | [GitHub](https://github.com/heilcheng/awesome-agent-skills) | Skills, tools, tutorials for AI coding agents |
| libukai/awesome-agent-skills | 2.5k | [GitHub](https://github.com/libukai/awesome-agent-skills) | Agent Skills guide: Quick Start, Skills, News, Cases |
| Agent Scan (Snyk) | 1.7k | [GitHub](https://github.com/snyk/agent-scan) | Security scanner for AI agents, MCP servers, and skills |
| tech-leads-club/agent-skills | 1.6k | [GitHub](https://github.com/tech-leads-club/agent-skills) | Secure, validated skill registry for AI coding agents |

#### Skills & Capabilities - Core & Specialized

| Name | URL | Description |
|------|-----|-------------|
| anthropics/skills | [GitHub](https://github.com/anthropics/skills) | Official Anthropic skills repository |
| mcp-builder skill | [GitHub](https://github.com/anthropics/skills/tree/main/skills/mcp-builder) | Official skill for building MCP servers |
| obra/superpowers | [GitHub](https://github.com/obra/superpowers) | Core skills library for Claude Code (20+ skills) |
| obra/superpowers-lab | [GitHub](https://github.com/obra/superpowers-lab) | Experimental skills repository |
| K-Dense-AI/claude-scientific-skills | [GitHub](https://github.com/K-Dense-AI/claude-scientific-skills) | Skills for research, science, engineering, finance |
| ffuf-web-fuzzing | [GitHub](https://github.com/jthack/ffuf_claude_skill) | Expert guidance for ffuf web fuzzing |
| trailofbits/skills | [GitHub](https://github.com/trailofbits/skills) | Security skills: static analysis, CodeQL/Semgrep, code auditing |
| web-asset-generator | [GitHub](https://github.com/alonw0/web-asset-generator) | Generates favicons, app icons, social media images |

#### Claude Code Tools

| Category | Name | URL |
|----------|------|-----|
| Orchestrator | Auto-Claude | [GitHub](https://github.com/AndyMik90/Auto-Claude) |
| Orchestrator | Claude Code Flow | [GitHub](https://github.com/ruvnet/claude-code-flow) |
| Orchestrator | Claude Squad | [GitHub](https://github.com/smtg-ai/claude-squad) |
| Orchestrator | sudocode | [GitHub](https://github.com/sudocode-ai/sudocode) |
| Usage Monitor | CC Usage | [GitHub](https://github.com/ryoppippi/ccusage) |
| Usage Monitor | ccflare | [GitHub](https://github.com/snipeship/ccflare) |
| Usage Monitor | better-ccflare | [GitHub](https://github.com/tombii/better-ccflare/) |
| Usage Monitor | Claude Code Usage Monitor | [GitHub](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor) |
| Status Line | CCometixLine | [GitHub](https://github.com/Haleclipse/CCometixLine) |
| Status Line | ccstatusline | [GitHub](https://github.com/sirmalloc/ccstatusline) |
| Status Line | claude-powerline | [GitHub](https://github.com/Owloops/claude-powerline) |
| Hook | Dippy | [GitHub](https://github.com/ldayton/Dippy) |
| Hook | parry | [GitHub](https://github.com/vaporif/parry) |
| Hook | Claude Hook Comms (HCOM) | [GitHub](https://github.com/aannoo/claude-hook-comms) |
| IDE Integration | claude-code.nvim | [GitHub](https://github.com/greggh/claude-code.nvim) |
| IDE Integration | claude-code.el | [GitHub](https://github.com/stevemolitor/claude-code.el) |
| IDE Integration | claude-code-ide.el | [GitHub](https://github.com/manzaltu/claude-code-ide.el) |
| IDE Integration | Claudix (VSCode) | [GitHub](https://github.com/Haleclipse/Claudix) |

---

### Summary Statistics

| Category | Key Papers | Eng. Blogs | Repositories | Resources |
|-----------|-------------|------------|---------------|-----------|
| Memory Systems | 9 | 19 | 5 | 33+ |
| Sandboxes & Isolation | 7 | 22 | 8 | 55+ |
| MCP Protocol | 0 | 14 | 15+ | 40+ |
| Agent Architectures | 5 | 27 | 10+ | 50+ |
| Programmatic Tool Calling | 1 | 3 | 4 | 15+ |
| Multi-Agent Systems | 1 | 3 | 6+ | 20+ |
| Planning & Reasoning | 6 | 4 | 0 | 15+ |
| WebMCP Protocol | 0 | 0 | 6 | 6 |
| Browser Automation | 0 | 16 | 8 | 25+ |
| State Management | 2 | 3 | 0 | 10+ |
| Observability & Debugging | 0 | 11 | 4 | 25+ |
| Evaluation & Benchmarking | 4 | 14 | 4 | 35+ |
| Error Handling | 0 | 5 | 0 | 12+ |
| Human-in-the-Loop | 0 | 5 | 0 | 15+ |
| Safety & Alignment | 1 | 10 | 3 | 20+ |
| Skills & Capabilities | 2 | 2 | 30+ | 55+ |
| **Total** | **38** | **158** | **100+** | **430+** |

---

### Recommended Reading Order

For practitioners starting with agentic system design:

#### Phase 1: Fundamentals (Week 1-2)
1. **Foundational Concepts:** Start with ReAct paper (2022) and Chain of Thought (2023)
2. **Memory Systems:** Read EverMemOS (2026), MIRIX (2025), and HiMeS (2026)
3. **Tool Integration:** Explore MCP documentation and Toolformer (2023)

#### Phase 2: Architecture & Planning (Week 3-4)
4. **Architecture Patterns:** Study LangGraph and CrewAI documentation
5. **Planning & Reasoning:** Read Tree of Thoughts (2023) and LLM+P (2023)
6. **Multi-Agent Systems:** Explore Generative Agents (2023) and AutoGPT

#### Phase 3: Operations & Safety (Week 5-6)
7. **Observability:** Set up Phoenix or LangSmith for agent tracing
8. **Evaluation:** Implement OpenAI Evals and RAGAS for benchmarking
9. **Safety:** Review Constitutional AI (2023) and implement guardrails

#### Phase 4: Advanced Topics (Week 7-8)
10. **Skills Development:** Browse awesome-agent-skills collections
11. **Browser Automation:** Experiment with PinchTab and Playwright
12. **Sandboxing:** Deploy E2B or Firecracker for secure execution

---

## Contributing

To contribute corrections or additions, please reference the source URLs provided with each resource. This document is a living compilation updated regularly to reflect the rapidly evolving field of agentic system design.

**Last Updated:** March 5, 2026

---

## License

This repository maintains an MIT License. See LICENSE file for details.
