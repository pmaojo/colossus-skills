---
name: graph-explorer
description: Interactive graph visualization and analysis skill
version: 0.1.0
author: Colossus Team
tags:
  - visualization
  - graph
  - analysis
  - dream-engine
tools:
  - name: graph_stats
    description: Get statistics about the knowledge graph (triples, clusters, contradictions, audit score)
    parameters:
      - name: namespace
        type: string
        required: false
        default: "memory"
        description: Namespace to analyze
    return_type: object
  - name: visualize_clusters
    description: Extract cluster information for visualization
    parameters:
      - name: namespace
        type: string
        required: false
        default: "memory"
        description: Namespace to analyze
    return_type: object
  - name: analyze_contradictions
    description: List contradictions detected in the knowledge graph
    parameters:
      - name: namespace
        type: string
        required: false
        default: "memory"
        description: Namespace to analyze
    return_type: object
  - name: dream_analysis
    description: Perform a full Dream Engine analysis (inference, cleaning, clustering, audit, patterns)
    parameters:
      - name: namespace
        type: string
        required: false
        default: "memory"
        description: Namespace to analyze
      - name: mode
        type: string
        required: false
        default: "full"
        enum: [full, infer, clean, summary, audit, improve]
        description: Analysis mode
      - name: depth
        type: number
        required: false
        default: 2
        description: Depth of transitive inference
      - name: limit
        type: number
        required: false
        default: 200
        description: Maximum triples to process
    return_type: object
---

# graph-explorer

Interactive graph visualization and analysis skill powered by Colossus Dream Engine.

## Tools

### graph_stats

Get comprehensive statistics about the knowledge graph:
- Number of triples
- Cluster count
- Contradictions detected
- Audit score (0.0–1.0)

**Parameters:**
- `namespace` (string, optional): Namespace to analyze (default: "memory")

**Returns:** Object with statistics.

### visualize_clusters

Extract semantic clusters from the graph for visualization.
Each cluster includes topic, size, central triple, and sample triples.

**Parameters:**
- `namespace` (string, optional): Namespace to analyze (default: "memory")

**Returns:** Object with cluster list.

### analyze_contradictions

List contradictions (value conflicts, type inconsistencies) detected by the Dream Engine.
Each contradiction includes type, description, confidence, and involved triples.

**Parameters:**
- `namespace` (string, optional): Namespace to analyze (default: "memory")

**Returns:** Object with contradiction list and audit score.

### dream_analysis

Perform a full Dream Engine analysis:
- Transitive inference
- Duplicate cleaning
- Semantic clustering
- Contradiction detection
- Pattern learning
- Audit scoring

**Parameters:**
- `namespace` (string, optional): Namespace to analyze (default: "memory")
- `mode` (string, optional): Analysis mode: full, infer, clean, summary, audit, improve (default: "full")
- `depth` (number, optional): Depth of transitive inference (default: 2)
- `limit` (number, optional): Maximum triples to process (default: 200)

**Returns:** Comprehensive analysis object.

## Installation

This skill can be installed via the Colossus marketplace:

```bash
colossus skills marketplace install graph-explorer
```

Or directly from this directory:

```bash
colossus skills marketplace install-url ./graph-explorer
```

## Usage Example

```bash
# Call via skill tool
colossus skills call graph-explorer graph_stats --namespace memory

# Or via MCP (if gateway is running)
# Tools: skill_graph-explorer_graph_stats, etc.
```