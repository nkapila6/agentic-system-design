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

---

## Web & Browser

### 8. WebMCP Protocol

_See the [Tools & Repositories](#tools--repositories-1) table for all WebMCP GitHub repositories._

---

### 9. Browser Automation Stacks

_See the [Tools & Repositories](#tools--repositories-1) table for all browser automation tools and repositories._

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

| Category | Key Papers | Repositories | Avg Stars | Resources |
|-----------|-------------|---------------|------------|-----------|
| Memory Systems | 9 | 5 | 80k+ | 14 |
| Sandboxes & Isolation | 7 | 8 | 4k+ | 30+ |
| MCP Protocol | 0 | 15+ | 10k+ | 25+ |
| Agent Architectures | 5 | 10+ | 2k+ | 20+ |
| Programmatic Tool Calling | 1 | 4 | N/A | 10+ |
| Multi-Agent Systems | 1 | 6+ | 4k+ | 15+ |
| Planning & Reasoning | 6 | 0 | N/A | 6 |
| WebMCP Protocol | 0 | 6 | 8 | 6 |
| Browser Automation | 0 | 8 | 500 | 8 |
| State Management | 2 | 0 | N/A | 5 |
| Observability & Debugging | 0 | 4 | 8k+ | 15+ |
| Evaluation & Benchmarking | 4 | 4 | 12k+ | 20+ |
| Error Handling | 0 | 0 | N/A | 6 |
| Human-in-the-Loop | 0 | 0 | N/A | 8 |
| Safety & Alignment | 1 | 3 | N/A | 8 |
| Skills & Capabilities | 2 | 30+ | 6k+ | 50+ |
| **Total** | **38** | **100+** | **~5k** | **250+** |

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
