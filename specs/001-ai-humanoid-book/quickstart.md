# Quickstart Guide: AI Robotics Humanoid Book Development

## Prerequisites
- Node.js 18+ installed
- npm or yarn package manager
- Git for version control
- A GitHub account for deployment

## Setup Instructions

1. **Clone or create the project directory:**
   ```bash
   mkdir ai-humanoid-robotics-book
   cd ai-humanoid-robotics-book
   ```

2. **Initialize Docusaurus:**
   ```bash
   npx create-docusaurus@latest website classic
   cd website
   ```

3. **Install additional dependencies:**
   ```bash
   npm install --save-dev remark-math rehype-katex
   ```

4. **Create the book structure:**
   ```bash
   mkdir -p docs/{preface,introduction,mechanical,electronic,actuators,control,vision,ai,software,ethics,casestudies,future,glossary,references}
   ```

## Content Creation Workflow

1. **Create a new chapter:**
   ```bash
   # Create chapter file in docs/ with kebab-case naming
   touch docs/preface-overview.md
   ```

2. **Add proper frontmatter to each chapter:**
   ```markdown
   ---
   title: Preface & Overview
   sidebar_position: 1
   description: Introduction to the AI Robotics Humanoid Book
   ---

   # Preface & Overview

   Content here...
   ```

3. **Update sidebar configuration in `sidebars.js`:**
   ```javascript
   module.exports = {
     docs: [
       'preface-overview',
       'introduction-robotics-humanoids',
       // ... other chapters
     ],
   };
   ```

## Content Guidelines

1. **Citations**: Use IEEE or APA format consistently
   - Example: [1] A. Author, "Title of paper," Journal Name, vol. X, no. Y, pp. XX-XX, Year.
   - Example: A. Author, "Title of webpage," Website Name. [Online]. Available: URL. [Accessed: Date]

2. **Diagrams**: Describe all diagrams in text format
   ```markdown
   <!-- Diagram: Block diagram showing the main components of a humanoid robot -->
   <!-- Description: The diagram illustrates the torso, head, arms, and legs with labeled joints -->
   ```

3. **Technical accuracy**: Cross-reference all claims with credible sources
   - Verify with IEEE, ACM, academic robotics research, or industry documentation
   - Include at least 25 credible sources across all chapters

## Validation Steps

1. **Check word count:**
   ```bash
   # Use a word count tool to ensure 8,000-12,000 total words
   find docs -name "*.md" -exec cat {} \; | wc -w
   ```

2. **Readability check:**
   - Use online tools to verify Flesch-Kincaid grade level is 9-12
   - Ensure content is accessible to CS/hardware background readers

3. **Build and test:**
   ```bash
   npm run build
   npm run serve
   ```

## GitHub Pages Deployment

1. **Configure deployment in `docusaurus.config.js`:**
   ```javascript
   const config = {
     // ...
     organizationName: 'your-github-username',
     projectName: 'ai-humanoid-robotics-book',
     deploymentBranch: 'gh-pages',
     // ...
   };
   ```

2. **Deploy:**
   ```bash
   GIT_USER=<Your GitHub username> npm run deploy
   ```

## Quality Assurance Checklist

- [ ] All content is original with proper citations
- [ ] No hallucinated components or technologies
- [ ] 8,000-12,000 words total
- [ ] 25+ credible sources included
- [ ] Flesch-Kincaid grade 9-12 readability achieved
- [ ] All diagrams described in text
- [ ] Docusaurus build completes without errors
- [ ] All links work correctly
- [ ] Mobile responsiveness verified