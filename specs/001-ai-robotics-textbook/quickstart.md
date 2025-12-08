# Quickstart Guide — Physical AI & Humanoid Robotics Textbook

## Overview
This guide provides a quick setup process for the Physical AI & Humanoid Robotics Textbook project. The project is built with Docusaurus and follows the specifications in the constitution and feature requirements.

## Prerequisites
- Node.js 18+ installed on your system
- Git for version control
- Ubuntu 22.04 (recommended environment for examples)
- Text editor of your choice

## Installation Steps

### 1. Clone and Setup the Repository
```bash
# Clone your repository (after creating it manually)
git clone <your-repo-url>
cd <repo-name>

# Install dependencies
npm install
```

### 2. Verify Docusaurus Installation
```bash
# Check if Docusaurus is properly installed
npx docusaurus --version

# Start development server
npm start
```

### 3. Project Structure Overview
```
├── docs/                 # Textbook content (Markdown/MDX files)
├── diagrams/             # SVG/PNG diagrams (12 total)
├── code/                 # Runnable examples (20 total)
├── examples/             # Example metadata files
├── scripts/              # Validation and build scripts
├── static/               # Static assets
├── specs/                # Specification files
├── .specify/             # SpecKit internal files
├── .claude/              # Claude Code automation
└── templates/            # Content templates
```

### 4. Creating Your First Module Content
1. Create a new markdown file in `docs/`:
```bash
touch docs/module-1-introduction.md
```

2. Add proper frontmatter to your content file:
```md
---
title: "Introduction to Module 1"
description: "Introduction to ROS 2 concepts for humanoid robotics"
sidebar_label: "Introduction"
sidebar_position: 1
module: "module-1-ros2"
week: 1
word_count: 1200
estimated_time: 20
authors: ["Your Name"]
tags: ["ros2", "introduction", "concepts"]
draft: false
date_updated: "2025-12-08"
examples: ["module-1-example-1"]
diagrams: ["module-1-diagram-1"]
prerequisites: ["Basic Python knowledge"]
---

# Introduction to Module 1: ROS 2 Nervous System

[Your content here...]
```

### 5. Adding Examples
1. Create an example directory in `code/`:
```bash
mkdir -p code/module-1/example-1
```

2. Add your code files and a metadata file:
```bash
# Create your example code
touch code/module-1/example-1/main.py

# Create metadata file
touch examples/module-1-example-1.meta.yaml
```

3. Example metadata file (`examples/module-1-example-1.meta.yaml`):
```yaml
id: "module-1-example-1"
title: "Basic ROS 2 Node"
description: "A simple ROS 2 node example"
module: "module-1-ros2"
path: "./code/module-1/example-1"
type_hints: true
os_compatibility: ["Ubuntu 22.04"]
python_version: ">=3.8"
gpu_required: false
dependencies: ["rclpy", "std_msgs"]
environment_file: "./code/module-1/example-1/requirements.txt"
comments_language: "English"
accessibility_notes: []
estimated_completion_time: 10
tested_on: "Ubuntu 22.04"
validation_status: "pending"
last_tested: "2025-12-08"
```

### 6. Adding Diagrams
1. Place your diagram in the appropriate module directory:
```bash
cp your-diagram.svg diagrams/module-1/
```

2. Reference it in your content with proper alt text and accessibility considerations.

### 7. Running Validation Scripts
```bash
# Check word count
python scripts/check-wordcount.py

# Check for broken links
bash scripts/link-check.sh

# Run full verification
bash scripts/verify.sh
```

### 8. Building and Deploying
```bash
# Build the static site
npm run build

# Deploy to Vercel (requires Vercel CLI setup)
vercel --prod
```

## Content Creation Guidelines

### Word Count Requirements
- Module 1: 4,000-5,000 words
- Module 2: 3,500-4,500 words
- Module 3: 4,000-5,000 words
- Module 4: 3,500-4,500 words

### Accessibility Requirements
- All diagrams must have proper alt text
- All content must meet WCAG 2.1 AA standards
- Use semantic HTML elements through Docusaurus

### Code Example Requirements
- Include type hints in all Python code
- Use English comments exclusively
- Tag GPU-dependent examples with `gpu: true` in metadata
- Ensure Ubuntu 22.04 compatibility

## Module Structure (13-Week Curriculum)

### Module 1 — ROS 2 Nervous System (Weeks 1-5)
- ROS 2 nodes, topics, services
- URDF humanoid models
- rclpy
- Sensor pipelines

### Module 2 — Digital Twin (Weeks 6-7)
- Gazebo physics
- Unity viz
- Multi-sensor simulation

### Module 3 — NVIDIA Isaac AI Brain (Weeks 8-10)
- Isaac Sim
- Nav2
- VSLAM
- Isaac ROS

### Module 4 — Vision-Language-Action (Weeks 11-13)
- Whisper → intent
- LLM planning
- VLA pipeline
- Capstone humanoid

## Troubleshooting

### Common Issues
1. **Docusaurus not starting**: Ensure Node.js 18+ is installed
2. **Missing dependencies**: Run `npm install` in the project root
3. **Build errors**: Check that all frontmatter is properly formatted

### Validation Failures
- If word count is outside limits, adjust content accordingly
- If accessibility checks fail, ensure all diagrams have alt text
- If example validation fails, check that type hints are present

## Next Steps
1. Begin creating content for Module 1 following the curriculum structure
2. Add at least 5 examples per module
3. Include 3 diagrams per module with proper accessibility
4. Run validation scripts regularly to ensure compliance
5. Deploy to Vercel when ready for review