# Research Summary — Physical AI & Humanoid Robotics Textbook

## Decision: Docusaurus Implementation
**Rationale**: Docusaurus v3 was selected as the static site generator based on the constitution requirements and plan specifications. It's well-suited for documentation-heavy projects like textbooks and provides built-in features for search, navigation, and accessibility compliance.

**Alternatives considered**:
- Next.js with custom MDX: More complex setup, requires more custom code
- VuePress: Less ecosystem support for accessibility features
- GitBook: Limited customization options
- Custom React app: Higher maintenance overhead

## Decision: Project Structure
**Rationale**: The project structure was determined based on the constitution and plan requirements, focusing on a documentation-first approach without backend or hardware integration.

**Structure**:
- `docs/` - All textbook content in Markdown/MDX format
- `diagrams/` - 12 SVG/PNG diagrams with accessibility compliance
- `code/` - 20 runnable examples organized by modules
- `examples/` - Metadata files (meta.yaml) for examples
- `scripts/` - Validation and build scripts
- `static/` - Static assets for Docusaurus
- `specs/` - Specification files
- `.specify/` - SpecKit internal files
- `.claude/` - Claude Code automation files
- `templates/` - Content templates with frontmatter

## Decision: Technology Stack
**Rationale**: The technology stack was predetermined in the constitution and plan:
- Node.js 18+ for Docusaurus compatibility
- Markdown/MDX for content authoring
- Ubuntu 22.04 as the target development environment
- Vercel for deployment (mandated by constitution)

**Alternatives considered**:
- Python-based solutions: Not aligned with front-end documentation requirements
- Static HTML generation: Lacks Docusaurus features like versioning, search
- Traditional CMS: Overkill for textbook content

## Decision: Content Organization
**Rationale**: Content will be organized into 4 modules following the 13-week curriculum structure from the constitution, with appropriate word counts and examples per module.

**Module Breakdown**:
- Module 1: ROS 2 Nervous System (Weeks 1-5) - 4000-5000 words
- Module 2: Digital Twin (Weeks 6-7) - 3500-4500 words
- Module 3: NVIDIA Isaac AI Brain (Weeks 8-10) - 4000-5000 words
- Module 4: Vision-Language-Action (Weeks 11-13) - 3500-4500 words

## Decision: Accessibility Compliance
**Rationale**: WCAG 2.1 AA compliance is mandated by the constitution and essential for educational content.

**Implementation**:
- Proper alt text for all diagrams
- Semantic HTML structure through Docusaurus
- Keyboard navigation support
- Color contrast compliance
- Screen reader compatibility

## Decision: Deployment Strategy
**Rationale**: Vercel deployment is explicitly mandated in the constitution, providing reliable hosting with good performance for documentation sites.

**Implementation**:
- GitHub integration for automatic builds
- Custom domain support if needed
- CDN distribution for global access
- Preview deployments for PRs

## Decision: Code Examples Architecture
**Rationale**: Examples must be runnable and accessible to students on Ubuntu 22.04, with proper type hints and English comments as required by the constitution.

**Approach**:
- Each example will have its own directory with requirements.txt/environment.yaml
- GPU-dependent examples will be tagged with metadata
- Examples will be organized by module
- All code will include error handling and English comments