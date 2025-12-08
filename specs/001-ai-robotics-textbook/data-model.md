# Data Model — Physical AI & Humanoid Robotics Textbook

## Textbook Module
Represents one of the 4 course modules (ROS 2, Digital Twin, NVIDIA Isaac AI, Vision-Language-Action), containing content, examples, and diagrams.

**Fields**:
- `id` (string): Unique identifier for the module (e.g., "module-1-ros2")
- `title` (string): Display title of the module
- `description` (string): Brief description of the module content
- `wordCount` (integer): Target word count for the module (3500-5000)
- `weeks` (integer[]): Week numbers covered by this module
- `contentFiles` (string[]): List of content file paths
- `examples` (string[]): List of example IDs associated with this module
- `diagrams` (string[]): List of diagram file paths
- `order` (integer): Module sequence number (1-4)

**Validation Rules**:
- `id` must be unique across all modules
- `wordCount` must be within constitution-specified ranges
- `weeks` must align with curriculum structure (1-13)
- `order` must be between 1-4 and unique

## Code Example
Represents runnable code with associated environment configuration and metadata.

**Fields**:
- `id` (string): Unique identifier for the example (e.g., "module-1-example-1")
- `moduleId` (string): Reference to parent module
- `title` (string): Display title of the example
- `description` (string): Brief description of what the example demonstrates
- `path` (string): File path to the example code
- `environment` (string): Path to environment configuration file (requirements.txt, environment.yaml)
- `gpuRequired` (boolean): Whether the example requires GPU resources
- `osCompatibility` (string[]): List of compatible operating systems (default: ["Ubuntu 22.04"])
- `dependencies` (string[]): List of required dependencies
- `instructions` (string): Setup and execution instructions
- `typeHints` (boolean): Whether the code includes type hints (required by constitution)

**Validation Rules**:
- `id` must be unique across all examples
- `moduleId` must reference an existing module
- `gpuRequired` must be explicitly set (true/false)
- `typeHints` must be true (constitution requirement)
- `osCompatibility` must include "Ubuntu 22.04" as minimum requirement

## Diagram
Represents visual content with alt text and accessibility compliance.

**Fields**:
- `id` (string): Unique identifier for the diagram
- `moduleId` (string): Reference to parent module
- `title` (string): Display title of the diagram
- `path` (string): File path to the diagram (SVG/PNG)
- `altText` (string): Alternative text for accessibility (WCAG 2.1 AA compliance)
- `caption` (string): Descriptive caption for the diagram
- `description` (string): Longer description for complex diagrams
- `format` (string): File format ("SVG" or "PNG")
- `accessibilityCompliant` (boolean): Whether the diagram meets WCAG 2.1 AA standards

**Validation Rules**:
- `id` must be unique across all diagrams
- `moduleId` must reference an existing module
- `altText` must not be empty (accessibility requirement)
- `format` must be either "SVG" or "PNG"
- `accessibilityCompliant` must be true

## Validation Script
Represents automated checks for content quality metrics.

**Fields**:
- `id` (string): Unique identifier for the validation script
- `name` (string): Name of the validation (e.g., "wordcount", "link-check", "verify")
- `description` (string): What the validation script checks
- `path` (string): File path to the script
- `frequency` (string): When the validation runs ("pre-commit", "build", "manual")
- `required` (boolean): Whether the validation is mandatory for deployment

**Validation Rules**:
- `id` must be unique across all validation scripts
- `frequency` must be one of the allowed values
- `required` must be true for constitution-mandated validations

## Relationships

### Module → Code Example
- One-to-Many: Each module can have multiple code examples
- Required: Each example must belong to exactly one module
- Cascade: If a module is removed, its examples become orphaned

### Module → Diagram
- One-to-Many: Each module can have multiple diagrams
- Required: Each diagram must belong to exactly one module
- Cascade: If a module is removed, its diagrams become orphaned

### Code Example → Environment Configuration
- One-to-One: Each code example has one environment configuration file
- Required: Each example must have environment configuration
- File-based: Configuration files are stored separately in the code directory

### Diagram → Accessibility Compliance
- One-to-One: Each diagram must meet accessibility compliance requirements
- Required: All diagrams must have alt text and proper descriptions
- Validation: Compliance is checked by validation scripts

## State Transitions (if applicable)

### Code Example States
- `draft`: Example is being developed
- `review`: Example is under review
- `approved`: Example is approved for inclusion
- `published`: Example is included in the textbook

### Validation Status
- `pending`: Validation has not yet been run
- `passing`: All validation checks have passed
- `failing`: One or more validation checks have failed
- `skipped`: Validation was intentionally skipped (with justification)