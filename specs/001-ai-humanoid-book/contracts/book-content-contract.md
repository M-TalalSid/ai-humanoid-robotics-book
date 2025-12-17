# Book Content Contract

## Purpose
This contract defines the structure and requirements for content that makes up the AI Robotics Humanoid Book. It ensures consistency across all chapters and adherence to the project's technical and quality standards.

## Content Structure Contract

### Chapter Format Requirements
```
- File naming: kebab-case format (e.g., "introduction-robotics-humanoids.md")
- Frontmatter must include:
  - title: string (chapter title)
  - sidebar_position: integer (position in sidebar navigation)
  - description: string (brief description of chapter content)
- Content must follow Docusaurus markdown format
```

### Cross-Chapter Reference Contract
```
- References to other chapters must use Docusaurus link syntax: `[text](./other-chapter)`
- All internal links must be relative
- Cross-references must be validated during build process
```

## Content Quality Contract

### Technical Accuracy Requirements
```
- All technical claims must be verifiable through credible sources
- No hallucinated components, frameworks, or technologies
- Content must be grounded in established robotics/AI research
```

### Citation Contract
```
- Minimum 2 credible sources per chapter
- Sources must be from institutions: IEEE, ACM, MIT, CMU, Nature, Arxiv, etc.
- Citations must follow IEEE or APA format consistently
- At least 40% of sources must be peer-reviewed
```

## Metadata Contract

### Chapter Metadata Requirements
```
Input:
  - title: string (5-100 characters)
  - content: string (500-1500 words per chapter)
  - wordCount: integer
  - references: array of Reference objects
  - difficultyLevel: enum (beginner, intermediate, advanced)
  - estimatedReadingTime: integer (in minutes)

Output:
  - Valid Docusaurus markdown file
  - Properly formatted sidebar entry
  - Compliant with Flesch-Kincaid grade 9-12 readability
```

## Validation Contract

### Content Validation Requirements
```
- Chapter word count between 500-1500 words
- Total book word count between 8,000-12,000 words
- Minimum 25 credible sources across all chapters
- Zero plagiarism tolerance
- Technical accuracy verification for all claims
```

## Navigation Contract

### Sidebar Integration Requirements
```
- Each chapter must be registered in sidebars.js
- Hierarchical structure maintained (preface → intro → core topics → advanced topics → conclusion)
- Logical flow preserved across all chapters
- Cross-links between related topics where appropriate
```

## Deployment Contract

### Build Requirements
```
- Docusaurus build must complete without errors
- All internal links must resolve correctly
- All assets (if any) must be properly referenced
- Site must be responsive and accessible
- SEO metadata must be present for each page
```

## Quality Gates
Before any chapter is considered complete:
1. Technical accuracy verified against credible sources
2. Citation requirements met
3. Readability requirements satisfied
4. Cross-references validated
5. Docusaurus build passes
6. All links and navigation work correctly