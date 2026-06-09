# CodePath-AI301-AI-Open-Source-Capstone

# Contribution [#]: metrics: rename memory enrichment table counters to end with _total

**Contribution Number:** 1  
**Student:** Yanyue Wang  
**Issue:** [[GitHub issue link](https://github.com/vectordotdev/vector/issues/25455)]    
**Status:** [Phase I ] [In Progress]

---

## Why I Chose This Issue

I chose this issue because it offers a focused, well-scoped entry point into a production Rust codebase, making a targeted change in lib/vector-common/src/internal_event/metric_name.rs without needing to understand the entire system while also teaching me how real-world observability infrastructure enforces naming standards and handles breaking changes responsibly through deprecation aliases and changelog entries.

---

## Understanding the Issue

### Problem Description

Three counter metrics in Vector's memory enrichment table : memory_enrichment_table_failed_insertions, memory_enrichment_table_failed_reads, and memory_enrichment_table_ttl_expirations are missing the required _total suffix, violating Vector's instrumentation specification. This matters because the spec explicitly requires all counters to end with _total to ensure consistency across Vector's metrics and compatibility with systems like Prometheus that rely on naming conventions for correct metric interpretation. 

### Expected Behavior

The three memory enrichment table counter metrics should be named memory_enrichment_table_failed_insertions_total, memory_enrichment_table_failed_reads_total, and memory_enrichment_table_ttl_expirations_total, conforming to Vector's instrumentation spec which mandates that all counters end with _total.

### Current Behavior

The three counters are currently emitted without the _total suffix (memory_enrichment_table_failed_insertions, memory_enrichment_table_failed_reads, memory_enrichment_table_ttl_expirations), violating the instrumentation spec. This means anyone scraping these metrics. For example via Prometheus: receives non-compliant metric names that are inconsistent with the rest of Vector's counter conventions.

### Affected Components

lib/vector-common/src/internal_event/metric_name.rs 

---

## Reproduction Process

### Environment Setup

[Notes on setting up your local development environment - challenges you faced, how you solved them]

### Steps to Reproduce

1. [Step 1]
2. [Step 2]
3. [Observed result]

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:** [If applicable]
- **My findings:** [What you discovered during reproduction]

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]

### Proposed Solution

[High-level description of your fix approach]

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** [Restate the problem]

**Match:** [What similar patterns/solutions exist in the codebase?]

**Plan:** [Step-by-step implementation plan]
1. [Modify file X to do Y]
2. [Add function Z]
3. [Update tests]

**Implement:** [Link to your branch/commits as you work]

**Review:** [Self-review checklist - does it follow the project's contribution guidelines?]

**Evaluate:** [How will you verify it works?]

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
