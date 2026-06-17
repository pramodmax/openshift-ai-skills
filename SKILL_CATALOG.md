# OpenShift AI Skills Catalog

Complete reference guide for all skills in this repository.

---

## 1. openshift-ai-3-4-expert

**Full Name:** OpenShift AI 3.4 Platform Fundamentals  
**File:** `openshift-ai-3-4-expert/SKILL.md`  
**Lines of Expertise:** 350+  
**Difficulty:** Intermediate to Advanced

### What This Skill Covers

Deep expertise in Red Hat OpenShift AI 3.4 architecture, new capabilities, and production deployment patterns for enterprise AI/ML platforms.

### Key Topics

- OpenShift AI 3.4 platform architecture & components
- Models-as-a-Service (MaaS) — native capability, no additional tooling
- OIDC authentication & identity provider federation
- MLflow Operator — managed component with workbench integration
- LLMInferenceService — KServe's GenAI-first CRD vs. legacy InferenceService
- Distributed inference — llm-d, tensor parallelism, prefill-decode separation
- AutoML (Tech Preview) — model training & comparison
- Model registry & Hugging Face integration
- Technology previews & production readiness
- HA/DR strategies & multi-region failover

### Core Technologies

- KServe (InferenceService, LLMInferenceService)
- Open Data Hub
- Kuadrant (API governance)
- Connectivity Link (AI Gateway)
- Envoy, Istio, Gateway API
- vLLM, llm-d (distributed serving)
- Model compression & quantization

### Architecture Patterns

1. **Single-Model Inference** — Small/medium models on single GPU
2. **Multi-Tenant Models-as-a-Service** — Shared infrastructure with governance
3. **Distributed Inference** — Large models (70B+) across multiple GPUs
4. **Hybrid Inference Gateway** — Multi-provider (self-hosted + external)

### Key YAML Artifacts

- LLMInferenceService (single-node)
- LLMInferenceService (multi-GPU with TP)
- Gateway & GatewayClass
- HTTPRoute for model exposure
- DataScienceCluster with MLflow

### CLI Commands

- `oc get LLMInferenceService`
- `oc describe lis <model-name>`
- `oc logs -f deployment/<model-name>-predictor`
- Model deployment via UI or manifest

### When to Use This Skill

**Ask about this skill when:**
- Designing or architecting an OpenShift AI platform
- Evaluating RHOAI 3.4 features and capabilities
- Planning production deployment patterns
- Understanding model serving options (KServe vs. llm-d)
- Setting up HA/DR strategies
- Implementing enterprise authentication
- Choosing between serving platforms

**Example questions:**
- "What's new in OpenShift AI 3.4?"
- "How do I deploy a production LLM platform?"
- "Should I use KServe or llm-d for a 70B model?"
- "How does MLflow integrate with OpenShift AI?"
- "What's the architecture for 500+ concurrent users?"

### Related Skills

- `maas-governance-expert` — Multi-tenant governance & quotas
- `ai-inference-optimization` — Performance tuning & quantization

---

## 2. maas-governance-expert

**Full Name:** Models-as-a-Service (MaaS) Governance & Management  
**File:** `maas-governance-expert/SKILL.md`  
**Lines of Expertise:** 380+  
**Difficulty:** Intermediate to Advanced

### What This Skill Covers

Enterprise-grade governance, access control, and cost management for shared Models-as-a-Service infrastructure using Kubernetes-native CRDs and Kuadrant policies.

### Key Topics

- Models-as-a-Service architecture & benefits
- Kuadrant policies (AuthPolicy, RateLimitPolicy)
- Kubernetes-native governance via CRDs
- Token quotas & rate limiting (per-user, per-team, per-tier)
- API key self-service with instant revocation
- Tier-based access control (free/standard/premium/enterprise)
- Connectivity Link & AI Gateway integration
- Gateway API (HTTPRoute, Gateway, GatewayClass)
- Authorino (OIDC-compatible authorization)
- Limitador (distributed rate limiting)
- Cost attribution & showback dashboards
- Multi-tenant isolation & RBAC

### Core Technologies

- Kuadrant (policy engine)
- Connectivity Link (AI Gateway)
- Kubernetes Gateway API
- Authorino (authorization)
- Limitador (rate limiting)
- KServe (LLMInferenceService)
- Envoy Proxy
- Istio (optional service mesh)

### Architecture Patterns

1. **Basic MaaS** — Single model, multiple users, shared inference
2. **Tiered MaaS** — Multiple tiers (free/pro/enterprise) with different quotas
3. **Team-Based Governance** — Per-team rate limits & quotas
4. **Multi-Provider MaaS** — Multiple models with unified governance

### Key YAML Artifacts

- Kuadrant setup (kuadrant.io/v1beta1)
- GatewayClass (openshift.io/gateway-controller)
- Gateway (HTTPS termination)
- HTTPRoute (per-model routing)
- AuthPolicy (OIDC + K8s token review)
- RateLimitPolicy (per-user, per-team, per-tier)
- LLMInferenceService (model deployment)

### CLI Commands

- `oc apply -f kuadrant.yaml`
- `oc apply -f gateway.yaml`
- `oc get HTTPRoute`
- `oc describe RateLimitPolicy`
- `oc get AuthPolicy -n openshift-ingress`
- Model endpoint testing with Bearer tokens

### When to Use This Skill

**Ask about this skill when:**
- Implementing multi-tenant shared model infrastructure
- Designing governance & cost control
- Setting up rate limiting & quotas
- Configuring API key management
- Defining team-based access tiers
- Tracking LLM usage & costs
- Ensuring compliance & audit

**Example questions:**
- "How do I implement MaaS governance?"
- "What's a RateLimitPolicy and when do I use it?"
- "How do I set per-team quotas?"
- "How do I configure API key self-service?"
- "How do I track costs for chargeback?"

### Related Skills

- `openshift-ai-3-4-expert` — Platform & model deployment
- `ai-gateway-architect` — Multi-provider routing & unified API
- `ai-inference-optimization` — Cost optimization through quantization

---

## 3. ai-gateway-architect

**Full Name:** Red Hat AI Gateway Architecture & Multi-Provider Routing  
**File:** `ai-gateway-architect/SKILL.md`  
**Lines of Expertise:** 450+  
**Difficulty:** Advanced

### What This Skill Covers

Expert architecture for centralized LLM routing via Red Hat AI Gateway, enabling cost-optimized access to self-hosted vLLM and external providers with unified authentication and governance.

### Key Topics

- Red Hat AI Gateway (Connectivity Link) architecture
- Multi-provider routing (self-hosted + external)
- Provider integration patterns (vLLM, AWS Bedrock, Azure OpenAI, Anthropic, GCP)
- Unified OpenAI-compatible API across all providers
- Intelligent failover & provider selection
- Cost optimization strategies (route to cheapest provider)
- Request transformation & payload translation
- Authentication & authorization (mTLS, API keys, OIDC)
- Rate limiting per provider
- Cost tracking & attribution
- Circuit breaking & health checks
- Hybrid on-premises/cloud strategies

### Core Technologies

- Red Hat Connectivity Link (AI Gateway)
- Kuadrant (policies, routing)
- Envoy Proxy (ingress, traffic management)
- Istio (optional service mesh)
- Gateway API (HTTPRoute, Gateway)
- AWS Bedrock (external provider)
- Azure OpenAI (external provider)
- Anthropic Claude API (external provider)
- Google Vertex AI (external provider)
- OpenAI-compatible API spec

### Architecture Patterns

1. **Single Unified Endpoint** — All providers behind one /v1/chat/completions
2. **Provider-Specific Endpoints** — Separate URLs per provider
3. **Intelligent Failover** — Primary → secondary → tertiary with cost awareness
4. **Multi-Cloud Redundancy** — On-prem primary, cloud providers as fallback
5. **Cost-Optimized Routing** — Route to cheapest provider first

### Key YAML Artifacts

- Gateway (unified ingress)
- HTTPRoute (multi-backend with weights)
- AuthPolicy (unified authentication)
- RateLimitPolicy (per-provider limits)
- Backend configuration (vLLM, Bedrock proxy, Azure proxy)

### CLI Commands

- `oc get Gateway`
- `oc describe HTTPRoute`
- `curl https://ai-gateway/v1/chat/completions`
- Provider credential setup & rotation
- Health check configuration

### When to Use This Skill

**Ask about this skill when:**
- Designing unified LLM access across multiple providers
- Migrating from cloud providers to on-premises
- Implementing cost-optimized provider routing
- Setting up intelligent failover
- Managing hybrid on-premises/cloud infrastructure
- Centralizing authentication for multiple providers
- Building multi-cloud disaster recovery

**Example questions:**
- "How do I create a unified API for multiple LLM providers?"
- "We're moving from Bedrock to on-premises. How do we architect this?"
- "How do I implement smart failover to cheaper providers?"
- "What's the cost difference between on-prem vLLM and AWS Bedrock?"
- "How do I track costs across multiple providers?"

### Related Skills

- `openshift-ai-3-4-expert` — Platform & LLMInferenceService deployment
- `maas-governance-expert` — Unified governance & rate limiting
- `ai-inference-optimization` — vLLM tuning for cost efficiency

---

## 4. ai-inference-optimization

**Full Name:** Red Hat AI Inference Server Optimization & Cost Efficiency  
**File:** `ai-inference-optimization/SKILL.md`  
**Lines of Expertise:** 515+  
**Difficulty:** Intermediate to Advanced

### What This Skill Covers

Expert guidance on optimizing LLM inference for maximum throughput and minimum cost using Red Hat AI Inference Server, vLLM, LLM Compressor, and model quantization techniques.

### Key Topics

- Red Hat AI Inference Server (vLLM-based)
- vLLM architecture & optimization
- LLM Compressor integration
- Quantization methods:
  - W8A8 (8-bit weight & activation)
  - W4A4 (extreme compression)
  - AWQ (activation-aware)
  - SparseGPT (structured sparsity)
  - Distillation (teacher-student)
- Inference optimization techniques:
  - PagedAttention (GPU memory optimization)
  - Continuous batching (dynamic token batching)
  - Tensor parallelism (TP) — distribute across GPUs
  - Data parallelism (DP) — replicate for throughput
  - Prefill-decode separation
  - Speculative decoding
- Hardware right-sizing & selection
- Multi-accelerator support (NVIDIA, AMD, TPU, CPU)
- Batch size & sequence length tuning
- KV cache optimization
- Performance benchmarking
- Cost-per-token analysis

### Core Technologies

- Red Hat AI Inference Server
- vLLM (inference engine)
- LLM Compressor (quantization & pruning)
- KServe (LLMInferenceService)
- llm-d (distributed serving)
- PyTorch (model optimization)
- Hugging Face (model repos)
- Neural Magic (LLM Compressor provider)

### Hardware Considerations

- **NVIDIA**: A100 (80GB), H100, L40S (cost-effective)
- **AMD**: MI300X (alternative, cost-effective)
- **Google**: TPU v5e, v6e (cloud-native)
- **CPU**: Fallback inference (slow but useful for edge)

### Quantization Decision Tree

| Model Size | Quantization | Hardware | Notes |
|-----------|--------------|----------|-------|
| < 7B | fp16 | 1× A100 40GB | Single GPU sufficient |
| 7-13B | W8A8 | 1× A100 40GB | 1.3x smaller, 95%+ quality |
| 13-70B | W8A8 or AWQ | 2-4× A100 (TP) | Multi-GPU with TP |
| > 70B | W8A8 (required) | 8-16× A100 (TP) | Must quantize, TP essential |

### Key YAML Artifacts

- LLMInferenceService (single-node)
- LLMInferenceService (multi-GPU TP)
- LLMInferenceService (prefill-decode separation)
- vLLM configuration parameters
- Resource requests/limits
- Affinity & tolerance rules

### CLI Commands

- `oc apply -f lis-manifest.yaml`
- `oc logs -f pod/<model>-predictor`
- vLLM startup parameters (batch size, TP, KV cache)
- LLM Compressor CLI
- Benchmark script execution
- Cost calculation

### When to Use This Skill

**Ask about this skill when:**
- Optimizing LLM inference performance
- Reducing LLM serving costs
- Selecting hardware (GPU type & count)
- Quantizing models before deployment
- Tuning vLLM parameters
- Implementing multi-GPU inference
- Benchmarking models
- Doing cost-per-token analysis

**Example questions:**
- "How do I quantize my model?"
- "Our inference costs $10K/month. How do we reduce this?"
- "What batch size should I use?"
- "Should I use tensor parallelism or data parallelism?"
- "Is A100 or L40S better for a 20B model?"

### Related Skills

- `openshift-ai-3-4-expert` — LLMInferenceService deployment
- `ai-gateway-architect` — Provider cost comparison
- `maas-governance-expert` — Token quota tracking & cost attribution

---

## Skill Selection Matrix

Use this matrix to find the right skill for your question:

| Question Type | Best Skill | Secondary | Tertiary |
|---|---|---|---|
| "What's new in RHOAI 3.4?" | openshift-ai-3-4-expert | — | — |
| "How do I deploy a model?" | openshift-ai-3-4-expert | ai-inference-optimization | — |
| "How do I set up governance?" | maas-governance-expert | openshift-ai-3-4-expert | — |
| "How do I reduce costs?" | ai-inference-optimization | ai-gateway-architect | maas-governance-expert |
| "How do I set up multi-cloud?" | ai-gateway-architect | ai-inference-optimization | — |
| "How do I quantize a model?" | ai-inference-optimization | openshift-ai-3-4-expert | — |
| "How do I implement MaaS?" | maas-governance-expert | openshift-ai-3-4-expert | ai-gateway-architect |
| "How do I add a rate limit?" | maas-governance-expert | ai-gateway-architect | — |
| "How do I optimize latency?" | ai-inference-optimization | openshift-ai-3-4-expert | — |

---

## Skill Development Roadmap

### Currently Available (v1.0)

✅ openshift-ai-3-4-expert  
✅ maas-governance-expert  
✅ ai-gateway-architect  
✅ ai-inference-optimization  

### Planned for Future Releases

- **openshift-ai-storage** — PVC, StorageClass, distributed training
- **openshift-ai-monitoring** — Prometheus, Grafana, logging, tracing
- **openshift-ai-networking** — Network policies, ingress, multi-cluster
- **openshift-ai-cicd** — Tekton pipelines, automated retraining
- **openshift-ai-security** — RBAC, mTLS, secrets, compliance

---

## Contributing New Skills

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding new skills.

**Skill proposal template:**

```
Skill Name: openshift-ai-<topic>
Topic: [One-line description]
Expertise Level: Intermediate / Advanced
Expected Lines: 400-500
Key Technologies: 
  - Tech 1
  - Tech 2
Architecture Patterns: 2-3 patterns
YAML Examples: 3+
Use Cases: [3-5 realistic scenarios]
```

---

## How Skills Relate

```
openshift-ai-3-4-expert (Platform Foundation)
    ├→ maas-governance-expert (Add governance)
    ├→ ai-inference-optimization (Add performance)
    └→ ai-gateway-architect (Add multi-cloud)

maas-governance-expert (Governance)
    ├→ openshift-ai-3-4-expert (Platform)
    └→ ai-gateway-architect (Unified routing)

ai-gateway-architect (Multi-cloud)
    ├→ openshift-ai-3-4-expert (On-prem vLLM)
    ├→ ai-inference-optimization (Cost optimization)
    └→ maas-governance-expert (Unified policies)

ai-inference-optimization (Cost)
    ├→ openshift-ai-3-4-expert (Deployment)
    ├→ ai-gateway-architect (Provider comparison)
    └→ maas-governance-expert (Quota tracking)
```

---

**Last Updated:** June 2026
