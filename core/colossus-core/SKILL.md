---
name: colossus-core
description: Core Colossus functionality
version: 1.0.0
tools:
  - name: echo
    description: Echo a message back
    parameters:
      - name: message
        type: string
        required: true
  - name: sum
    description: Sum two numbers
    parameters:
      - name: a
        type: number
        required: true
      - name: b
        type: number
        required: true
  - name: parse_code
    description: Parse Go source code
    parameters:
      - name: path
        type: string
        required: false
      - name: format
        type: string
        required: false
  - name: synapse_query
    description: Query Synapse
    parameters:
      - name: query
        type: string
        required: false
      - name: namespace
        type: string
        required: false
      - name: limit
        type: number
        required: false
  - name: dream
    description: Perform offline reasoning on the knowledge graph
    parameters:
      - name: namespace
        type: string
        required: false
      - name: mode
        type: string
        required: false
        enum: [batch, infer, clean, summary, full, audit, improve]
      - name: depth
        type: number
        required: false
      - name: limit
        type: number
        required: false
---
# Colossus Core Skill

Basic tools.