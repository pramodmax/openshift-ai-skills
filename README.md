# OpenShift AI Skills

A comprehensive skill repository for Red Hat OpenShift AI platform experts with 20+ years of enterprise consulting experience. This collection of skills provides guidance on designing, deploying, and operating enterprise AI/ML platforms on Red Hat OpenShift.

## Skills Included

### 1. **openshift-ai-3-4-expert** — OpenShift AI 3.4 Platform Fundamentals
Deep expertise in Red Hat OpenShift AI 3.4 architecture, new features, and enterprise deployment patterns. Covers MLflow integration, OIDC authentication, technology previews, and production readiness.

### 2. **maas-governance-expert** — Models-as-a-Service (MaaS) & Governance
Specialist guidance on implementing enterprise-grade Models-as-a-Service with Kubernetes-native governance. Covers Kuadrant policies, token quotas, rate limiting, API key self-service, and tier-based access control using Connectivity Link.

### 3. **ai-gateway-architect** — Red Hat AI Gateway Architecture
Expert architecture patterns for centralized AI model routing via Red Hat AI Gateway (Connectivity Link). Includes external model provider integration (AWS Bedrock, Azure OpenAI, Anthropic), self-hosted vLLM routing, and production-grade API governance.

### 4. **ai-inference-optimization** — Red Hat AI Inference Server & Optimization
Enterprise guidance on optimizing LLM inference with Red Hat AI Inference Server, vLLM, LLM Compressor, quantization strategies (W8A8, AWQ, sparsity), and multi-accelerator support (NVIDIA, AMD, TPU) for cost-effective production deployments.

## Installation

```bash
npx skills add https://github.com/pramodmax/openshift-ai-skills.git
```

Or by shorthand (if repo is public):
```bash
npx skills add pramodmax/openshift-ai-skills
```

Install globally:
```bash
npx skills add https://github.com/pramodmax/openshift-ai-skills.git -g
```

## Use a Specific Skill

```bash
npx skills use https://github.com/pramodmax/openshift-ai-skills.git@openshift-ai-3-4-expert
npx skills use https://github.com/pramodmax/openshift-ai-skills.git@maas-governance-expert
npx skills use https://github.com/pramodmax/openshift-ai-skills.git@ai-gateway-architect
npx skills use https://github.com/pramodmax/openshift-ai-skills.git@ai-inference-optimization
```

Or by shorthand:
```bash
npx skills use pramodmax/openshift-ai-skills@openshift-ai-3-4-expert
npx skills use pramodmax/openshift-ai-skills@maas-governance-expert
npx skills use pramodmax/openshift-ai-skills@ai-gateway-architect
npx skills use pramodmax/openshift-ai-skills@ai-inference-optimization
```

## Prerequisites

- Claude Code or Claude AI web interface
- Familiarity with Kubernetes, OpenShift, or enterprise containerized workloads
- Recommended: Access to Red Hat OpenShift AI documentation (docs.redhat.com)

## Target Audience

- **Enterprise Architects** designing AI/ML platforms on OpenShift
- **Platform Engineers** deploying and operating RHOAI at scale
- **ML Engineers** optimizing model serving and inference performance
- **DevOps/SRE teams** implementing governance and multi-tenancy
- **Consultants** delivering Red Hat AI solutions to enterprises

## Features

✅ Enterprise-grade architecture patterns  
✅ Production-ready deployment manifests & YAML examples  
✅ Kubernetes-native governance (Kuadrant, Gateway API)  
✅ Cost optimization through quantization & compression  
✅ Multi-tenant, multi-cloud routing strategies  
✅ Security-first authentication & authorization  
✅ vLLM distributed inference (tensor parallelism, prefill-decode separation)  
✅ Integration with external AI providers  

## Documentation References

- [Red Hat OpenShift AI 3.4 Release Notes](https://docs.redhat.com/en/documentation/red_hat_openshift_ai_self-managed/3.4/html/release_notes/index)
- [Govern LLM Access with Models-as-a-Service](https://docs.redhat.com/en/documentation/red_hat_openshift_ai_self-managed/3.4/html/govern_llm_access_with_models-as-a-service/index)
- [Red Hat Connectivity Link Documentation](https://docs.redhat.com/en/documentation/red_hat_connectivity_link/1.0/)
- [Red Hat AI Inference Server](https://developers.redhat.com/products/red-hat-ai/inference-server)
- [KServe LLMInferenceService](https://kserve.github.io/website/docs/model-serving/generative-inference/llmisvc/llmisvc-overview)

## License

MIT

## Contributing

Contributions, bug reports, and feature requests are welcome. Please open an issue or pull request.

---

**Author:** Pramod Padmanabhan ()  
**Based on:** 20+ years of Red Hat enterprise consulting experience  
**Last Updated:** June 2026
