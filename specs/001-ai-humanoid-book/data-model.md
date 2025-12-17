# Data Model: AI Robotics Humanoid Book

## Book Chapter
- **Fields**:
  - id: string (kebab-case identifier)
  - title: string (chapter title)
  - content: string (markdown content)
  - wordCount: integer (number of words in chapter)
  - references: array of Reference objects
  - diagrams: array of Diagram objects
  - learningGoals: array of strings
  - difficultyLevel: enum (beginner, intermediate, advanced)
  - estimatedReadingTime: integer (minutes)

- **Validation rules**:
  - Title must be 5-100 characters
  - Content must be between 500-1500 words for optimal chapter length
  - Must include at least 2 references
  - Difficulty level must be specified

- **Relationships**:
  - Belongs to one Book
  - May reference other Chapters for cross-references

## Reference
- **Fields**:
  - id: string (unique identifier)
  - title: string (title of the source)
  - authors: array of strings (author names)
  - publication: string (journal, conference, or book title)
  - year: integer (publication year)
  - type: enum (journal, conference, book, thesis, report, web)
  - url: string (URL if available)
  - citation: string (formatted citation in IEEE or APA style)
  - credibilityRating: enum (high, medium, low) based on source institution

- **Validation rules**:
  - Must be from credible institution (IEEE, ACM, academic research, etc.)
  - Citation must follow IEEE or APA format
  - Type must be specified

- **Relationships**:
  - Belongs to one or more Chapters

## Diagram
- **Fields**:
  - id: string (unique identifier)
  - title: string (diagram title)
  - description: string (text description of the diagram)
  - purpose: string (educational purpose of the diagram)
  - chapterId: string (which chapter this diagram belongs to)

- **Validation rules**:
  - Description must be detailed enough to understand the diagram conceptually
  - Purpose must align with learning goals of the chapter

- **Relationships**:
  - Belongs to one Chapter

## Humanoid System
- **Fields**:
  - id: string (unique identifier)
  - name: string (system name: sensing, actuation, locomotion, perception, reasoning)
  - description: string (detailed description of the system)
  - components: array of strings (key components of the system)
  - technicalSpecifications: object (detailed technical specs)
  - applications: array of strings (use cases)

- **Validation rules**:
  - Must be one of the 5+ key humanoid systems
  - Description must be technically accurate

- **Relationships**:
  - Referenced in one or more Chapters

## Book
- **Fields**:
  - id: string (unique identifier)
  - title: string (book title)
  - author: string (author name)
  - totalWordCount: integer (sum of all chapters)
  - chapters: array of Chapter objects
  - totalReferences: integer (count of all references)
  - readingTime: integer (estimated total reading time in minutes)
  - targetAudience: string (description of target audience)
  - publicationDate: string (ISO date format)

- **Validation rules**:
  - Total word count must be between 8,000-12,000 words
  - Must have at least 25 references
  - Target audience must be specified
  - Must include all required chapters as per spec

- **State transitions**:
  - draft → in-progress → review → complete