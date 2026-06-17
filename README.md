<div align="center">

# 🚀 OpenShift AI Skills

### Enterprise-Grade AI/ML Platform Architecture & Operations

*4 production-ready skills for Claude Code, Cursor, and AI agents leveraging OpenShift AI 3.4+*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Skills](https://img.shields.io/badge/Skills-4-orange.svg)](#-skill-catalog)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Agent Skills](https://img.shields.io/badge/Format-Agent%20Skills-blueviolet.svg)](https://agentskills.io)
[![skills.sh](https://img.shields.io/badge/skills.sh-cli-000000.svg)](https://skills.sh)

<br />

**[Install Now](#-quick-start)** · **[Browse Skills](#-skill-catalog)** · **[Contribute](CONTRIBUTING.md)** · **[Docs](USAGE.md)**

<br />

<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/kubernetes/kubernetes-plain.svg" width="40" />&nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/redhat/redhat-original.svg" width="40" />&nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/terraform/terraform-original.svg" width="40" />&nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" width="40" />&nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/azure/azure-original.svg" width="40" />&nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" width="40" />&nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original.svg" width="40" />&nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/grafana/grafana-original.svg" width="40" />

</div>

---

## Why This Exists

Install these skills and your AI agent gains **expert-level knowledge** to:

| Skill | What Your Agent Learns |
|-------|----------------------|
| **openshift-ai-3-4-expert** | Platform fundamentals, OIDC authentication, Models-as-a-Service architecture, MLflow integration, production deployment patterns |
| **maas-governance-expert** | Kubernetes-native governance (Kuadrant policies), token quotas, rate limiting, tier-based access control, showback dashboards |
| **ai-gateway-architect** | Multi-provider LLM routing (self-hosted + AWS Bedrock + Azure OpenAI), centralized authentication, cost optimization, failover patterns |
| **ai-inference-optimization** | vLLM performance tuning, model quantization (W8A8, AWQ, sparsity), LLM Compressor workflows, multi-GPU inference, cost analysis |

---

## ⚡ 30-Second Install

```bash
# Install all 4 OpenShift AI skills
npx skills add https://github.com/pramodmax/openshift-ai-skills.git

# Or by shorthand (if repo is public)
npx skills add pramodmax/openshift-ai-skills

# Install to specific agent (e.g., Cursor)
npx skills add https://github.com/pramodmax/openshift-ai-skills.git -a cursor -y

# Clone directly to local agent directory
git clone https://github.com/pramodmax/openshift-ai-skills.git ~/.skills/openshift-ai
```

Works with **Claude Code**, **Cursor**, **Codex**, **Cline**, and [all Agent Skills–compatible agents](https://github.com/vercel-labs/skills#supported-agents).

---

## What Makes This Different

Most "AI platforms" documentation gives you links. This repo gives your AI agent **production-ready knowledge** it can immediately act on:

✅ **Real YAML Manifests** — Copy-pasteable LLMInferenceService, HTTPRoute, AuthPolicy, RateLimitPolicy examples  
✅ **Exact CLI Commands** — `oc`, `kubectl`, `npx skills` commands you can run today  
✅ **Architecture Patterns** — Proven patterns for single-model, multi-tenant, distributed, and hybrid deployments  
✅ **Enterprise Best Practices** — 20+ years of Red Hat consulting expertise distilled into guidance  
✅ **Troubleshooting Guides** — Common issues with root causes and solutions  
✅ **Cost Analysis** — Break-even calculations, quantization ROI, hardware right-sizing  

### Example: What's in Each Skill

```
skill/
├── SKILL.md                    # 300-500+ lines of expert knowledge
│   ├── Core Technologies       # What you'll use
│   ├── Your Expertise          # What the agent embodies
│   ├── Your Responsibilities   # What to guide on
│   ├── Key Architecture Patterns # Reference implementations
│   ├── Core YAML Examples      # Production-ready manifests
│   ├── CLI Commands            # Step-by-step deployments
│   ├── Cost Analysis           # TCO calculations
│   ├── Troubleshooting         # Common issues + fixes
│   └── Best Practices          # Consultant wisdom
```

---

## 📚 Skill Catalog

### 1. **openshift-ai-3-4-expert**
**OpenShift AI 3.4 Platform Fundamentals**

Deep expertise in Red Hat OpenShift AI 3.4 architecture, new capabilities, and enterprise deployment patterns.

- OIDC authentication & federation (Azure AD, Okta, Keycloak)
- Models-as-a-Service (MaaS) with Kubernetes-native CRDs
- MLflow Operator integration with workbench automation
- LLMInferenceService migration from legacy InferenceService
- Distributed inference (llm-d, tensor parallelism, prefill-decode separation)
- AutoML & model registry patterns
- Production readiness & HA/DR strategies

**When to use:** Platform architecture, deployment planning, feature evaluation, governance strategy

### 2. **maas-governance-expert**
**Models-as-a-Service (MaaS) & Governance**

Specialist guidance on implementing enterprise-grade Models-as-a-Service with Kubernetes-native governance.

- Kuadrant policies (AuthPolicy, RateLimitPolicy) for API governance
- Token quotas & rate limiting (per-user, per-team, per-tier)
- API key self-service with instant revocation
- Tier-based access control (standard/premium/enterprise)
- Showback dashboards for cost attribution & chargeback
- Connectivity Link integration
- Gateway API & HTTPRoute routing patterns

**When to use:** Multi-tenant governance, cost control, quota enforcement, API gateway design

### 3. **ai-gateway-architect**
**Red Hat AI Gateway Architecture**

Expert architecture for centralized LLM routing across self-hosted and external providers.

- Multi-provider routing strategies (vLLM + Bedrock + Azure OpenAI + Anthropic)
- Intelligent fallback & cost optimization
- Unified authentication & authorization
- Request transformation & payload translation
- Circuit breaking & health checks
- Cost tracking per provider & model
- Hybrid on-premises/cloud strategies

**When to use:** Multi-cloud LLM access, cost optimization, provider consolidation, failover design

### 4. **ai-inference-optimization**
**Red Hat AI Inference Server & Optimization**

Enterprise guidance on optimizing LLM inference for cost and performance.

- vLLM performance tuning (batch size, GPU memory utilization, KV cache)
- Model quantization workflows (W8A8, AWQ, SparseGPT, distillation)
- LLM Compressor integration & benchmarking
- Multi-GPU inference (tensor parallelism, data parallelism, prefill-decode)
- Hardware right-sizing (A100 vs. L40S vs. MI300X)
- Multi-accelerator support (NVIDIA, AMD, TPU)
- Cost-per-token analysis & ROI calculations

**When to use:** Performance optimization, cost reduction, hardware selection, model compression strategy

---

## 🚀 Quick Start by Use Case

### "We need to serve multiple proprietary LLMs to 500+ users"
→ Use: **openshift-ai-3-4-expert** + **maas-governance-expert**  
→ Implement: Multi-tenant MaaS with token quotas, per-team rate limits, OIDC federation

### "Our large model inference is too expensive; latency is critical"
→ Use: **ai-inference-optimization** + **ai-gateway-architect**  
→ Implement: W8A8 quantization, tensor parallelism, failover to cheaper provider

### "We're migrating from cloud (Bedrock) to on-premises to reduce costs"
→ Use: **ai-gateway-architect** + **ai-inference-optimization**  
→ Implement: Hybrid gateway with unified API, on-prem vLLM as primary, Bedrock as fallback

### "We need production-grade LLM infrastructure on OpenShift, but don't know where to start"
→ Use: All 4 skills  
→ Get: Complete platform design, deployment, governance, and optimization

---

## 📖 Documentation

- **[USAGE.md](USAGE.md)** — Detailed guide on how to use each skill in Claude Code
- **[SKILL_CATALOG.md](SKILL_CATALOG.md)** — Comprehensive skill reference with examples
- **[CONTRIBUTING.md](CONTRIBUTING.md)** — How to contribute new skills or improve existing ones
- **[Red Hat OpenShift AI Docs](https://docs.redhat.com/en/documentation/red_hat_openshift_ai_self-managed/3.4/)** — Official platform documentation

---

## 💡 What's Included in Every Skill

Each SKILL.md file contains:

### Architecture & Design
- Core technology overview
- When to use this skill
- Key architecture patterns with diagrams
- Reference implementations

### Production Examples
- Real YAML manifests (copy-pasteable)
- Exact `oc`, `kubectl`, CLI commands
- Configuration templates
- Integration examples

### Operations & Optimization
- Performance tuning parameters
- Cost analysis & break-even calculations
- Monitoring & observability
- Troubleshooting guide with root causes

### Best Practices
- Enterprise patterns proven in production
- Security considerations
- HA/DR strategies
- Common mistakes & how to avoid them

---

## 🎯 Target Audience

- **Enterprise Architects** — Design AI/ML platforms on OpenShift
- **Platform Engineers** — Deploy and operate RHOAI at scale
- **ML Engineers** — Optimize model serving and inference
- **DevOps/SRE Teams** — Implement governance and multi-tenancy
- **Consultants** — Deliver Red Hat AI solutions to enterprises
- **AI Developers** — Build apps on OpenShift AI

---

## 🛠️ Technology Stack

**Platform:** Red Hat OpenShift AI 3.4  
**Serving:** KServe, LLMInferenceService, llm-d, vLLM  
**Governance:** Kuadrant, Connectivity Link, Gateway API  
**Optimization:** LLM Compressor, Quantization, Model Compression  
**Cloud Providers:** AWS Bedrock, Azure OpenAI, Google Vertex AI, Anthropic  
**Accelerators:** NVIDIA, AMD, Google TPU  

---

## 📝 Examples

### Example 1: Deploy an LLMInferenceService

```bash
# Your agent provides this when asked to deploy a model:
oc apply -f - <<EOF
apiVersion: serving.kserve.io/v1alpha1
kind: LLMInferenceService
metadata:
  name: llama-3-70b
  namespace: llm-serving
spec:
  model:
    name: meta-llama/Llama-3.1-70B-Instruct-w8a8
    uri: hf://RedHatAI/Llama-3-70B-Instruct-W8A8
  replicas: 2
  template:
    containers:
      - name: main
        resources:
          limits:
            nvidia.com/gpu: "8"
            memory: 256Gi
  router:
    gateway: {}
EOF
```

### Example 2: Apply Governance Policies

```bash
# Your agent understands how to build RateLimitPolicy:
oc apply -f - <<EOF
apiVersion: kuadrant.io/v1
kind: RateLimitPolicy
metadata:
  name: team-tier-limits
  namespace: maas
spec:
  targetRef:
    group: gateway.networking.k8s.io
    kind: HTTPRoute
    name: llama-3-route
  limits:
    team-premium:
      rates:
        - limit: 500
          window: 1m
      conditions:
        - expression: "auth.identity.user.groups.contains('tier-premium')"
EOF
```

---

## ✨ Key Features

✅ **4 specialized skills** with 1,700+ lines of expert guidance  
✅ **300+ production YAML examples** you can copy-paste  
✅ **Step-by-step CLI commands** for every deployment pattern  
✅ **Real cost analysis** with break-even calculations  
✅ **Troubleshooting guides** for common issues  
✅ **Best practices** from 20+ years of Red Hat consulting  
✅ **Multi-cloud integration** (on-premises + AWS + Azure + GCP)  
✅ **Enterprise patterns** (MaaS, governance, HA/DR, failover)  

---

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- How to add new skills
- Skill quality standards
- Documentation requirements
- Review process

---

## 📄 License

MIT License — See [LICENSE](LICENSE) for details.

---

## 🔗 Links

- **Repository:** https://github.com/pramodmax/openshift-ai-skills
- **Install:** `npx skills add https://github.com/pramodmax/openshift-ai-skills.git`
- **Red Hat OpenShift AI:** https://www.redhat.com/en/products/ai/openshift-ai
- **Connectivity Link:** https://docs.redhat.com/en/documentation/red_hat_connectivity_link/
- **KServe:** https://kserve.github.io
- **Kuadrant:** https://kuadrant.io

