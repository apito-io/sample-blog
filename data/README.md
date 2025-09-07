# Sample Data Structure

This folder contains realistic sample data for the Blog CMS template:

## Structure

```
data/
├── post/           # 30 blog posts with content
│   ├── [uuid].json # Individual post files  
│   └── relation.json # Relationship mappings
├── category/       # 10 categories
│   ├── [uuid].json # Individual category files
│   └── relation.json # Relationship mappings  
└── comment/        # 50 comments
    ├── [uuid].json # Individual comment files
    └── relation.json # Relationship mappings
```

## File Format

### Individual Records
Each model record is stored as a UUID-named JSON file:

**Post Example:**
```json
{
  "_id": "550e8400-e29b-41d4-a716-446655440001",
  "title": "Sample Blog Post",
  "slug": "sample-blog-post",
  "content": {
    "html": "<h2>Introduction</h2><p>Content...</p>",
    "markdown": "## Introduction\n\nContent...",
    "text": "Introduction: Content..."
  },
  "featured_image": "https://images.unsplash.com/photo-xxx",
  "published_at": "2024-09-07",
  "status": "Published",
  "tags": "Technology"
}
```

### Relationship Files
Relationships are documented in `relation.json` files:

```json
{
  "post-uuid": {
    "category": {
      "relation_type": "has_one",
      "id": "category-uuid"     // Single string for has_one
    },
    "comment": {
      "relation_type": "has_many",
      "ids": ["comment-uuid-1", "comment-uuid-2"]  // Array for has_many
    }
  }
}
```

## Data Generation

This sample data was generated using the Apito Data Generator:

```bash
# Regenerate data
./apito-gen

# Or using Node.js
node apito-data-generator.js
```

## Statistics

- **Total Files**: 93
- **Posts**: 30 with rich HTML/Markdown content
- **Categories**: 10 with descriptions and themes
- **Comments**: 50 with realistic user feedback
- **Relationships**: 100% coverage with proper foreign keys
- **UUID Format**: All files use UUID v4 naming convention

---

**Note**: Due to GitHub file limits, this shows the data structure. The complete dataset can be generated using the data generator tools included in this repository.