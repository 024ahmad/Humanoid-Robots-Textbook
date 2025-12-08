# Diagram Metadata Schema

## Purpose
This document defines the expected schema for diagram metadata in the Physical AI & Humanoid Robotics Textbook. Each diagram in the `diagrams/` directory should have appropriate metadata that follows this schema, either in a separate file or as part of a central metadata file.

## Schema Definition

### Required Fields
- `id` (string): Unique identifier for the diagram
- `title` (string): Display title of the diagram
- `path` (string): Relative path to the diagram file
- `alt_text` (string): Alternative text for accessibility (WCAG 2.1 AA compliance)
- `module` (string): The module this diagram belongs to
- `accessibility_compliant` (boolean): Whether the diagram meets WCAG 2.1 AA standards

### Content and Description
- `caption` (string): Descriptive caption for the diagram
- `description` (string): Longer description for complex diagrams
- `keywords` (array of strings): Keywords for searchability
- `format` (string): File format ("SVG" or "PNG")

### Accessibility Information
- `color_contrast_compliant` (boolean): Whether the diagram meets color contrast requirements
- `text_size_appropriate` (boolean): Whether text elements are appropriately sized
- `focusable_elements` (array of strings): List of interactive elements if applicable
- `accessibility_notes` (array of strings): Any additional accessibility considerations

### Usage and Context
- `related_content` (array of strings): IDs of related content pages
- `related_examples` (array of strings): IDs of related examples
- `target_audience` (string): Intended audience level (e.g., "beginner", "intermediate", "advanced")
- `complexity_level` (number): Complexity on a scale of 1-5

## Example Implementation

```yaml
id: "module-1-diagram-1"
title: "ROS 2 Architecture Overview"
path: "./diagrams/module-1/ros2-architecture.svg"
alt_text: "Architecture diagram showing ROS 2 nodes, topics, services, and the DDS communication layer"
module: "module-1-ros2"
accessibility_compliant: true
caption: "ROS 2 architecture showing the communication layer and node interactions"
description: "This diagram illustrates how ROS 2 nodes communicate through topics and services using the DDS (Data Distribution Service) communication layer."
keywords: ["ros2", "architecture", "nodes", "topics", "dds"]
format: "SVG"
color_contrast_compliant: true
text_size_appropriate: true
focusable_elements: []
accessibility_notes: ["Uses high contrast colors", "Text is large enough for readability"]
related_content: ["module-1-ros2-concepts", "module-1-nodes-and-topics"]
related_examples: ["module-1-example-1", "module-1-example-2"]
target_audience: "beginner"
complexity_level: 3
```

## Validation Rules
- `id` must be unique across all diagrams
- `alt_text` must not be empty (accessibility requirement)
- `format` must be either "SVG" or "PNG"
- `accessibility_compliant` must be true (constitution requirement)
- `color_contrast_compliant` must be true (WCAG 2.1 AA requirement)
- `text_size_appropriate` must be true (WCAG 2.1 AA requirement)