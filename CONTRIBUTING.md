# Contributing to OpenShift AI Skills

We welcome contributions! This guide explains how to add new skills, improve existing ones, or suggest enhancements.

## Ways to Contribute

- **Add a new skill** — Cover a new OpenShift AI topic (e.g., storage, networking, CI/CD integration)
- **Improve a skill** — Add examples, fix errors, clarify documentation
- **Report issues** — Found a bug or outdated information? Let us know
- **Suggest features** — Ideas for new skills or improvements?

---

## Adding a New Skill

### Step 1: Choose Your Topic

Skills should cover a focused area of expertise relevant to OpenShift AI. Examples:

- "openshift-ai-storage-optimization" — PVC, StorageClass, persistent models, training data
- "openshift-ai-networking" — Networking policies, ingress, multi-cluster, service mesh
- "openshift-ai-cicd-integration" — Tekton pipelines, model CI/CD, automated retraining
- "openshift-ai-monitoring" — Prometheus, Grafana, logging, tracing for AI workloads
- "openshift-ai-security" — RBAC, network policies, secrets management, audit logging

**Tips:**
- Pick a topic you're expert in (or willing to research deeply)
- Ensure it's specific enough (not "OpenShift AI Overview" — that's too broad)
- Check existing skills to avoid overlap

### Step 2: Create the Skill Directory

```bash
mkdir -p <skill-name>
cd <skill-name>
touch SKILL.md
```

### Step 3: Write the SKILL.md File

Every skill must be a single `SKILL.md` file (400+ lines) with YAML frontmatter.

**Template:**

```markdown
---
name: <skill-slug>
description: <one-line description of the skill>
---

# <Skill Title>

You are a <domain> specialist with deep expertise in <specific focus>.

## Your Expertise

### Core Technologies
- Technology 1
- Technology 2

### Key Patterns
- Pattern 1
- Pattern 2

## Your Responsibilities

When helping with <topic> projects, you:

1. **Assess Requirements**: ...
2. **Recommend Architecture**: ...
3. **Design Production Deployments**: ...
4. ...

## Key Architecture Patterns

### Pattern 1: [Name]

**Best for:** [Use case]  
**Components:** [Tech stack]  

[Description + YAML example]

### Pattern 2: [Name]

...

## Core YAML Examples

### Example 1: [Description]

\`\`\`yaml
# Full YAML manifest
apiVersion: ...
kind: ...
\`\`\`

### Example 2: [Description]

...

## CLI Commands & Deployment

### Step 1: [Action]

\`\`\`bash
# Command with explanation
oc apply -f ...
\`\`\`

### Step 2: [Action]

...

## Troubleshooting

| Issue | Cause | Solution |
|-------|-------|----------|
| ... | ... | ... |

## Best Practices

1. **Practice 1**: [Explanation]
2. **Practice 2**: [Explanation]

## References

- [Link Title](https://example.com)
- [Docs](https://docs.example.com)

---

**Key Takeaway**: [Summary of why this skill matters]
```

### Step 4: Quality Checklist

Before submitting, ensure your skill has:

- ✅ **Frontmatter**: `name` and `description` fields
- ✅ **Length**: 400+ lines (demonstrates depth)
- ✅ **Structure**: Sections for technologies, patterns, examples, CLI, troubleshooting
- ✅ **YAML Examples**: At least 3 production-ready manifests
- ✅ **CLI Commands**: Real commands users can copy-paste
- ✅ **Troubleshooting**: Common issues + fixes (5+ items)
- ✅ **Best Practices**: At least 5 actionable recommendations
- ✅ **No external code**: Self-contained guidance (links for reference only)
- ✅ **Grammar & spelling**: Proofread for clarity
- ✅ **Formatting**: Proper markdown (code blocks, tables, lists)

### Step 5: Test the Skill

```bash
# Install locally to test
npx skills add ./openshift-ai-skills

# Or in a specific agent
npx skills add ./openshift-ai-skills -a claude-code -y

# Test by asking questions in your agent
```

### Step 6: Submit a Pull Request

1. **Fork the repo** on GitHub
2. **Create a branch**: `git checkout -b add-<skill-name>`
3. **Add your skill**: Create `<skill-name>/SKILL.md`
4. **Update README**: Add your skill to the skill catalog section
5. **Commit**: `git commit -m "Add <skill-name> skill"`
6. **Push**: `git push origin add-<skill-name>`
7. **Open PR**: Submit pull request with description of your skill

**PR Template:**

```markdown
## Description

Brief description of what your skill covers.

## Skill Details

- **Skill Name**: openshift-ai-<topic>
- **Topic**: [What it covers]
- **Expertise Level**: Intermediate / Advanced
- **Use Cases**: 
  - Use case 1
  - Use case 2

## Testing

Tested with:
- Claude Code ✅
- Cursor ✅
- Codex ❌ (not tested)

## Checklist

- [x] SKILL.md has 400+ lines
- [x] All YAML examples are valid
- [x] CLI commands are tested
- [x] Troubleshooting section included
- [x] No spelling/grammar errors
- [x] Markdown formatting is correct
```

---

## Improving Existing Skills

### If You Find an Error

1. **Open an Issue**: Describe the error and provide context
2. **Fork the repo**: Create a fix branch
3. **Update the SKILL.md**: Correct the error with explanation
4. **Submit PR**: Reference the issue

### If You Want to Add More Examples

1. **Create a branch**: `git checkout -b enhance-<skill-name>`
2. **Add examples** to the relevant skill's SKILL.md
3. **Test thoroughly**: Ensure examples are accurate
4. **Submit PR** with description of what you added

### If You Want to Add a New Section

Common sections to add:
- **Monitoring & Observability** — Prometheus queries, Grafana dashboards
- **Multi-Region** — Failover, federation, latency optimization
- **Security Deep-Dive** — Encryption, RBAC, compliance
- **Cost Optimization** — Specific cost-saving strategies
- **Advanced Patterns** — Enterprise-grade patterns

---

## Skill Guidelines

### Do's ✅

- **Be specific**: Focus on one topic (e.g., "MaaS governance", not "OpenShift AI")
- **Be practical**: Include real YAML, real CLI commands, real examples
- **Be opinionated**: Share best practices from experience
- **Be complete**: Cover architecture, deployment, troubleshooting, costs
- **Be current**: Reference OpenShift AI 3.4+ features and latest tools
- **Link references**: Cite official docs for attribution
- **Think enterprise**: Consider HA, scaling, security, compliance

### Don'ts ❌

- **Don't be too broad**: Avoid "What is OpenShift?" or generic Kubernetes topics
- **Don't be theoretical**: Include real, runnable examples
- **Don't skip troubleshooting**: Every pattern has edge cases
- **Don't plagiarize**: Reference official docs, add your interpretation
- **Don't ignore edge cases**: Mention limitations and workarounds
- **Don't assume knowledge**: Assume intermediate (not expert) level

---

## Skill Structure Template

Use this outline for new skills:

```
1. Title & Frontmatter
2. Your Expertise (tech, patterns, focus)
3. Your Responsibilities (what you guide on)
4. Architecture Overview (diagram or text)
5. Core CRDs & YAML Examples (3+ examples)
6. Deployment Workflow (step-by-step)
7. Advanced Patterns (optional)
8. Monitoring & Observability
9. Troubleshooting (5+ issues with fixes)
10. Best Practices (5+ actionable items)
11. References & Links
12. Key Takeaway (summary)
```

---

## Code of Conduct

- Be respectful and inclusive
- Assume good intent
- Focus on technical discussions
- No spam, harassment, or discrimination

---

## Questions?

- **GitHub Issues**: [Create an issue](https://github.com/pramodmax/openshift-ai-skills/issues)
- **GitHub Discussions**: [Start a discussion](https://github.com/pramodmax/openshift-ai-skills/discussions)

---

## Recognition

Contributors will be:
- Listed in the commit message
- Mentioned in skill documentation
- Acknowledged in the README contributor section (coming soon)

Thank you for contributing! 🙌
