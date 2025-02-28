# PageRank Implementation

## Overview
This project implements the **PageRank** algorithm and applies it to the **Berkeley-Stanford web graph dataset** to analyze the importance of web pages.

## Dataset
- **Dataset Name**: Berkeley-Stanford Web Graph
- **Source**: [Stanford SNAP](https://snap.stanford.edu/data/web-BerkStan.html)
- **Format**: Edge list file where each line represents a directed edge between two nodes (web pages):
  ```
  source_node_id destination_node_id
  ```
- **Description**: The dataset consists of web pages from `berkeley.edu` and `stanford.edu`, with hyperlinks forming a directed graph.

## PageRank Algorithm
The PageRank algorithm assigns a numerical weight to each node in the graph, measuring its importance based on incoming links.

### Algorithm Steps:
1. **Initialize** ranks for all nodes (usually equally distributed).
2. **Iterate** using the formula:
   
   $$PR(p) = \frac{1 - d}{N} + d \sum_{q \in M(p)} \frac{PR(q)}{L(q)}$$
   
   where:
   - `PR(p)`: PageRank of page `p`
   - `d`: Damping factor (default: 0.85)
   - `N`: Total number of pages
   - `M(p)`: Set of pages linking to `p`
   - `L(q)`: Number of outgoing links from page `q`
3. **Repeat** until convergence (i.e., PageRank values stop changing significantly).
4. **Normalize** values to ensure they sum up to 1.

## Installation & Requirements

### Prerequisites
Ensure you have Python installed, along with the following libraries:
