# How to Use OpenShift AI Skills

This guide explains how to use each skill in Claude Code, Cursor, and other AI agents.

## Installation

### Option 1: Install via Full URL (Recommended)
```bash
npx skills add https://github.com/pramodmax/openshift-ai-skills.git
```

### Option 2: Install via Shorthand
```bash
npx skills add pramodmax/openshift-ai-skills
```

### Option 3: Install to Specific Agent
```bash
# Install to Cursor
npx skills add https://github.com/pramodmax/openshift-ai-skills.git -a cursor -y

# Install to Claude Code
npx skills add https://github.com/pramodmax/openshift-ai-skills.git -a claude-code -y
```

### Option 4: Clone Locally
```bash
git clone https://github.com/pramodmax/openshift-ai-skills.git ~/.skills/openshift-ai
```

---

## Using the Skills in Claude Code

Once installed, the skills are automatically available when you ask questions in Claude Code.

### Example 1: Ask About Platform Architecture

**You ask:**
```
I need to design a production OpenShift AI platform for 500+ data scientists.
What's the best architecture?
```

**The agent (with openshift-ai-3-4-expert skill) responds:**
- Recommends Models-as-a-Service pattern
- Explains OIDC federation for centralized auth
- Provides MLflow integration guidance
- Suggests HA/DR strategy
- References production YAML examples

---

### Example 2: Implement Multi-Tenant Governance

**You ask:**
```
How do I set up governance for our shared LLM platform?
We need token quotas per team and rate limiting.
```

**The agent (with maas-governance-expert skill) responds:**
- Explains Kuadrant policies (AuthPolicy, RateLimitPolicy)
- Provides exact YAML for RateLimitPolicy with team tiers
- Shows how to configure subscription CRDs
- Includes CLI commands to deploy
- References troubleshooting if policies don't apply

---

### Example 3: Optimize Inference Costs

**You ask:**
```
Our LLM serving costs $10K/month. Can we reduce this?
We're serving a 70B model on 8 A100s.
```

**The agent (with ai-inference-optimization skill) responds:**
- Recommends W8A8 quantization (30% smaller model)
- Calculates new cost: $7K/month (~30% savings)
- Shows LLM Compressor workflow
- Provides vLLM tuning parameters
- Benchmarks latency/throughput impact

---

### Example 4: Design Multi-Cloud Failover

**You ask:**
```
We want to use on-premises vLLM but fallback to
AWS Bedrock if on-prem goes down. How do we architect this?
```

**The agent (with ai-gateway-architect skill) responds:**
- Explains unified AI Gateway pattern
- Provides HTTPRoute configuration with weighted backends
- Shows request transformation logic
- Includes cost tracking setup
- References provider credential management

---

## Skill Selection Guide

### When to Use: `openshift-ai-3-4-expert`

**Use this skill when:**
- Designing or architecting an OpenShift AI platform
- Evaluating RHOAI 3.4 features (MaaS, OIDC, MLflow, AutoML)
- Planning production deployment patterns
- Understanding LLMInferenceService vs. InferenceService migration
- Setting up HA/DR strategies
- Implementing enterprise authentication

**Example questions:**
- "What's new in OpenShift AI 3.4?"
- "How do I deploy a production-grade LLM platform on OpenShift?"
- "Should we use MLflow? How do we integrate it?"
- "What's the difference between KServe and llm-d?"

---

### When to Use: `maas-governance-expert`

**Use this skill when:**
- Implementing Models-as-a-Service governance
- Designing multi-tenant access control
- Setting up token quotas and rate limiting
- Configuring API key self-service
- Defining tier-based access (free/pro/enterprise)
- Tracking costs and generating showback reports
- Using Kuadrant policies and Connectivity Link

**Example questions:**
- "How do I implement MaaS governance with Kuadrant?"
- "What's the right rate limit per team?"
- "How do I configure per-user vs. per-team quotas?"
- "How do I set up cost attribution for chargeback?"
- "What's an RateLimitPolicy and when do I use it?"

---

### When to Use: `ai-gateway-architect`

**Use this skill when:**
- Designing unified LLM access across multiple providers
- Setting up centralized authentication & authorization
- Routing requests to self-hosted + cloud LLM providers
- Implementing intelligent failover
- Optimizing costs by routing to cheapest provider
- Integrating AWS Bedrock, Azure OpenAI, Anthropic
- Building hybrid on-premises/cloud infrastructure

**Example questions:**
- "How do I create a unified API for multiple LLM providers?"
- "We want to migrate from Bedrock to on-prem vLLM. How?"
- "How do I implement smart failover between providers?"
- "What's the architecture for multi-cloud LLM routing?"
- "How do I track costs per provider and model?"

---

### When to Use: `ai-inference-optimization`

**Use this skill when:**
- Optimizing LLM inference performance
- Reducing LLM serving costs
- Selecting hardware (GPU type, number of GPUs)
- Quantizing models (W8A8, AWQ, sparsity)
- Tuning vLLM parameters
- Implementing multi-GPU inference
- Benchmarking models before/after optimization

**Example questions:**
- "How do I quantize my model with LLM Compressor?"
- "What batch size should I use for optimal throughput?"
- "Should I use tensor parallelism or data parallelism?"
- "How do I compare on-premises vLLM vs. AWS Bedrock costs?"
- "What's the right GPU for a 70B model?"

---

## Common Usage Patterns

### Pattern 1: "I'm Starting from Scratch"

**Recommended order:**
1. Start with `openshift-ai-3-4-expert` to understand the platform
2. Add `maas-governance-expert` to design governance
3. Add `ai-gateway-architect` if multi-cloud is needed
4. Add `ai-inference-optimization` to optimize costs

**Example conversation:**
```
You: "I need to build a production OpenShift AI platform for our company."
Agent (with all 4 skills):
  1. Explains RHOAI 3.4 architecture
  2. Recommends MaaS pattern with Kuadrant governance
  3. Suggests multi-cloud gateway for provider diversity
  4. Provides quantization strategy for cost savings
  5. Gives deployment roadmap with CLI commands
```

---

### Pattern 2: "We Already Have a Platform, But It's Slow/Expensive"

**Recommended order:**
1. Use `ai-inference-optimization` to reduce costs
2. Use `ai-gateway-architect` to explore multi-provider routing
3. Use `maas-governance-expert` if adding multi-tenancy

**Example conversation:**
```
You: "Our LLM platform costs $15K/month. Can we reduce it?"
Agent (with ai-inference-optimization):
  1. Analyzes model size vs. hardware
  2. Recommends quantization strategy
  3. Calculates savings: e.g., $15K → $9K with W8A8
  4. Provides LLM Compressor workflow
  5. Benchmarks impact on latency
```

---

### Pattern 3: "We Need Enterprise Governance"

**Recommended order:**
1. Use `maas-governance-expert` to implement governance
2. Use `openshift-ai-3-4-expert` for platform setup
3. Use `ai-gateway-architect` if routing between providers

**Example conversation:**
```
You: "We need to serve models to 20 teams with cost control."
Agent (with maas-governance-expert):
  1. Explains RateLimitPolicy and AuthPolicy
  2. Provides YAML for team-based quotas
  3. Shows how to set up API key self-service
  4. Includes troubleshooting for quota enforcement
  5. Suggests showback dashboard for transparency
```

---

## Asking the Right Questions

### Good Questions (Skills Will Help More)
- "What's the architecture pattern for [specific use case]?"
- "How do I implement [feature] with OpenShift AI?"
- "Show me the YAML for [component]."
- "What CLI commands do I run to [action]?"
- "How do I troubleshoot [error]?"
- "What's the cost comparison between [options]?"

### Vague Questions (Less Helpful)
- "Tell me about OpenShift AI" (too broad)
- "How do I use the skills?" (meta, not about the platform)
- "Is OpenShift AI good?" (opinion-based)

### Best Practice
Combine question context with the skill:
- **Include the use case:** "We're deploying models for 200 users..."
- **Mention the scale:** "We're serving 70B+ models..."
- **State the constraint:** "We need sub-50ms latency..."
- **Ask for specific output:** "Show me the YAML..." or "Give me the CLI commands..."

---

## Tips & Tricks

### Tip 1: Ask for Multiple Formats
```
"Show me the YAML for RateLimitPolicy, 
plus the CLI command to deploy it, 
plus troubleshooting if it doesn't work."
```

### Tip 2: Request Comparisons
```
"Compare tensor parallelism vs. data parallelism 
for a 70B model on our 8-GPU cluster. 
Which is better for throughput?"
```

### Tip 3: Ask for Cost Analysis
```
"We're running Llama 3 70B on 8 A100s. 
Calculate cost/token and compare to AWS Bedrock. 
Is on-prem cheaper?"
```

### Tip 4: Request Troubleshooting
```
"My RateLimitPolicy isn't being enforced. 
What are the common causes? 
How do I debug this?"
```

### Tip 5: Ask for Production Readiness
```
"Give me a production-ready LLMInferenceService manifest
with HA (3 replicas), resource limits, affinity rules,
tolerations, and monitoring."
```

---

## What Each Skill Won't Do

The skills are focused on OpenShift AI 3.4 and enterprise deployment patterns. They won't:

- Debug application-specific bugs in your code
- Recommend non-OpenShift platforms (but can compare)
- Provide generic Kubernetes/Istio help (some guidance, but not exhaustive)
- Recommend specific models for your task (but can guide selection criteria)
- Provide generic Python/ML knowledge (assumes intermediate AI/ML background)

---

## Troubleshooting the Skills

### Skill Not Appearing in Suggestions
```bash
# Reinstall the skill
npx skills remove pramodmax/openshift-ai-skills
npx skills add https://github.com/pramodmax/openshift-ai-skills.git -y
```

### Agent Not Using the Skill
- **Tip 1:** Ask a specific OpenShift AI question (agent chooses relevant skill)
- **Tip 2:** Mention "show me YAML" or "give me CLI commands"
- **Tip 3:** Use keywords like "Kuadrant", "vLLM", "quantization", "MaaS"

### Skills Outdated
```bash
# Update to latest version
npx skills update pramodmax/openshift-ai-skills
```

---

## Examples Repository

For more examples, see:
- [openshift-ai-3-4-expert/SKILL.md](openshift-ai-3-4-expert/SKILL.md) — Architecture patterns and YAML
- [maas-governance-expert/SKILL.md](maas-governance-expert/SKILL.md) — Kuadrant policies and CRDs
- [ai-gateway-architect/SKILL.md](ai-gateway-architect/SKILL.md) — Multi-provider routing
- [ai-inference-optimization/SKILL.md](ai-inference-optimization/SKILL.md) — Performance tuning and quantization

---

## Support & Feedback

- **Report Issues:** [GitHub Issues](https://github.com/pramodmax/openshift-ai-skills/issues)
- **Contribute Skills:** [CONTRIBUTING.md](CONTRIBUTING.md)
- **Discuss:** [GitHub Discussions](https://github.com/pramodmax/openshift-ai-skills/discussions)

---

**Happy building! 🚀**
