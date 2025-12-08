# Example Metadata Schema

## Purpose
This document defines the expected schema for example metadata files in the Physical AI & Humanoid Robotics Textbook. Each example in the `code/` directory should have a corresponding metadata file that follows this schema.

## Schema Definition

### Required Fields
- `id` (string): Unique identifier for the example
- `title` (string): Display title of the example
- `description` (string): Brief description of what the example demonstrates
- `module` (string): The module this example belongs to
- `path` (string): Relative path to the example code
- `type_hints` (boolean): Whether the code includes type hints (required: true)

### Environment and Requirements
- `os_compatibility` (array of strings): List of compatible operating systems
- `python_version` (string): Required Python version (e.g., ">=3.8")
- `gpu_required` (boolean): Whether the example requires GPU resources
- `gpu_memory` (string): Required GPU memory if applicable (e.g., "8GB")
- `dependencies` (array of strings): List of required dependencies
- `environment_file` (string): Path to environment configuration file

### Content and Accessibility
- `comments_language` (string): Language of code comments (required: "English")
- `accessibility_notes` (array of strings): Any accessibility considerations
- `estimated_completion_time` (number): Estimated time to run the example in minutes

### Validation and Testing
- `tested_on` (string): Environment where the example was tested
- `validation_status` (string): Current validation status ("pending", "passing", "failing")
- `last_tested` (string): ISO date of last test (YYYY-MM-DD)

## Example Implementation

```yaml
id: "module-1-example-1"
title: "ROS 2 Node Creation"
description: "Basic example showing how to create a simple ROS 2 node for humanoid robot control"
module: "module-1-ros2"
path: "./code/module-1/ros2-node-basic"
type_hints: true
os_compatibility: ["Ubuntu 22.04"]
python_version: ">=3.8"
gpu_required: false
dependencies: ["rclpy", "std_msgs"]
environment_file: "./code/module-1/ros2-node-basic/requirements.txt"
comments_language: "English"
accessibility_notes: []
estimated_completion_time: 15
tested_on: "Ubuntu 22.04"
validation_status: "passing"
last_tested: "2025-12-08"
```

## Validation Rules
- `id` must be unique across all examples
- `type_hints` must be true (constitution requirement)
- `comments_language` must be "English" (constitution requirement)
- `os_compatibility` must include "Ubuntu 22.04" as minimum requirement
- `last_tested` must be in ISO format
- `validation_status` must be one of the allowed values