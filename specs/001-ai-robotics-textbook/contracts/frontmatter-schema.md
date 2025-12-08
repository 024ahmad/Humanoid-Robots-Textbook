# Frontmatter Schema for Textbook Content

## Purpose
This document defines the expected frontmatter schema for all textbook content files in the Physical AI & Humanoid Robotics Textbook. All Markdown/MDX files in the `docs/` directory must include appropriate frontmatter following this schema.

## Schema Definition

### Required Fields
- `title` (string): The display title of the document
- `description` (string): A brief description of the content
- `sidebar_label` (string): The label to appear in the sidebar navigation
- `sidebar_position` (number): Position in the sidebar hierarchy

### Module-Specific Fields
- `module` (string): The module this content belongs to (e.g., "module-1-ros2")
- `week` (number): The week number in the curriculum (1-13)
- `word_count` (number): The actual word count of the content
- `estimated_time` (number): Estimated reading time in minutes

### Content Metadata Fields
- `authors` (array of strings): List of content authors
- `tags` (array of strings): Content tags for searchability
- `draft` (boolean): Whether the content is still in draft state
- `date_updated` (string): ISO date of last update (YYYY-MM-DD)

### Example and Diagram References
- `examples` (array of strings): IDs of examples referenced in this content
- `diagrams` (array of strings): IDs of diagrams referenced in this content
- `prerequisites` (array of strings): Prerequisites for understanding this content

### Accessibility Fields
- `alt_descriptions` (object): Alt text for images in this document
- `accessibility_notes` (array of strings): Additional accessibility information

## Example Implementation

```yaml
title: "Introduction to ROS 2 Concepts"
description: "Understanding the fundamentals of ROS 2 for humanoid robotics applications"
sidebar_label: "ROS 2 Concepts"
sidebar_position: 1
module: "module-1-ros2"
week: 1
word_count: 1250
estimated_time: 25
authors: ["AI Assistant"]
tags: ["ros2", "concepts", "nodes", "topics"]
draft: false
date_updated: "2025-12-08"
examples: ["module-1-example-1", "module-1-example-2"]
diagrams: ["module-1-diagram-1", "module-1-diagram-2"]
prerequisites: ["Basic Python knowledge", "Linux command line familiarity"]
alt_descriptions:
  ros2_architecture: "Architecture diagram showing ROS 2 nodes, topics, and services"
accessibility_notes: ["Diagram includes color contrast compliant elements"]
```

## Validation Rules
- All required fields must be present
- `sidebar_position` must be a positive number
- `word_count` must be a positive integer
- `estimated_time` must be a positive integer
- `week` must be between 1 and 13
- `module` must match one of the defined modules
- `date_updated` must be in ISO format