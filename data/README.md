# Blog CMS Sample Data

This folder contains realistic sample data for the Blog CMS template:

## Content Management Structure

```
data/
├── post/              # 30 blog posts with content
│   ├── [uuid].json    # Individual post files
│   └── relation.json  # Post relationships
├── category/          # 10 categories for organization
│   ├── [uuid].json    # Individual category files
│   └── relation.json  # Category relationships
└── comment/           # 50 reader comments
    ├── [uuid].json    # Individual comment files
    └── relation.json  # Comment relationships
```

## Sample Data Features

### Posts (30 records)
- Complete blog articles with titles, content, and metadata
- Published and draft status tracking
- SEO-friendly slugs and meta descriptions
- Featured images and media galleries
- Author information and publication dates
- Tag-based categorization
- View counts and engagement metrics
- Category associations for content organization

### Categories (10 records)
- Content categorization system
- Category hierarchy with parent/child relationships
- Featured images for category pages
- SEO descriptions and meta information
- Post count tracking
- Category-specific templates and styling

### Comments (50 records)
- Reader engagement and community interaction
- Comment moderation status (approved, pending, spam)
- Author information and contact details
- Comment threading and reply support
- Timestamp tracking for chronological ordering
- Post association for content context
- IP address logging for moderation

## Relationship Format

### Post Relations
```json
{
  "post-uuid": {
    "category": {
      "relation_type": "has_one",
      "id": "category-uuid"
    },
    "comment": {
      "relation_type": "has_many",
      "ids": ["comment-uuid-1", "comment-uuid-2"]
    }
  }
}
```

### Category Relations
```json
{
  "category-uuid": {
    "post": {
      "relation_type": "has_many",
      "ids": ["post-uuid-1", "post-uuid-2"]
    }
  }
}
```

### Comment Relations
```json
{
  "comment-uuid": {
    "post": {
      "relation_type": "has_one",
      "id": "post-uuid"
    }
  }
}
```

## Content Management Patterns

### Publishing Workflow
- **Draft**: Initial content creation and editing
- **Review**: Editorial review and fact-checking
- **Published**: Live content available to readers
- **Archived**: Older content maintained for reference

### Content Organization
- **Category System**: Hierarchical content classification
- **Tag System**: Cross-category content labeling
- **Featured Content**: Highlighted posts for homepage
- **SEO Optimization**: Search engine friendly URLs and metadata

### Reader Engagement
- **Comment System**: Reader feedback and discussion
- **Social Sharing**: Integration with social media platforms
- **Newsletter Integration**: Email subscription management
- **Analytics Tracking**: Page views and user engagement

## Blog Content Examples

### Technology Posts
- **"Getting Started with GraphQL"** - Technical tutorial content
- **"API Design Best Practices"** - Development methodology
- **"Database Performance Optimization"** - Technical deep-dive

### Business Posts  
- **"Content Marketing Strategies"** - Marketing insights
- **"Building Remote Teams"** - Business management
- **"Customer Success Stories"** - Case studies and testimonials

### Lifestyle Posts
- **"Work-Life Balance Tips"** - Personal development
- **"Productivity Tools Review"** - Product comparisons
- **"Industry Event Coverage"** - Conference reports and insights

## Comment Interaction Examples

### Technical Discussions
- Code examples and implementation questions
- Best practice debates and alternative approaches
- Bug reports and solution sharing

### Community Engagement
- Reader appreciation and feedback
- Question and answer interactions
- Experience sharing and testimonials

### Content Requests
- Topic suggestions for future posts
- Follow-up questions on published content
- Collaboration opportunities and partnerships

## Data Generation

This blog data was generated using the Apito Data Generator:

```bash
# Regenerate blog content data
./apito-gen

# Verify content relationships
grep -r "category_id\|post_id" *.json
```

## Statistics

- **Total Files**: 93
- **Blog Posts**: 30 with complete content and metadata
- **Categories**: 10 for content organization and navigation
- **Comments**: 50 reader interactions and community engagement
- **Relationships**: 100% coverage with proper content associations
- **UUID Format**: All files use UUID v4 naming
- **Content Features**: Rich text content, media galleries, and SEO optimization

## Import Instructions

### Via Apito Dashboard
1. Create new general project in Apito Dashboard
2. Import schema.json for blog CMS structure
3. Upload data folder maintaining content relationships
4. Configure publishing workflows and content management

### Via Apito CLI
```bash
apito import schema.json
apito import data/ --preserve-structure
```

## Use Cases Demonstrated

- **Corporate Blogging**: Company news, updates, and thought leadership
- **Technical Documentation**: API guides, tutorials, and how-to articles
- **Content Marketing**: SEO-optimized content for lead generation
- **Community Building**: Reader engagement through comments and discussions
- **Publishing Workflow**: Editorial processes and content lifecycle management
- **Multi-Author Platforms**: Collaborative content creation and management

## SEO and Content Features

### Search Engine Optimization
- **Meta Descriptions**: Custom descriptions for search results
- **Friendly URLs**: SEO-optimized slugs and permalinks
- **Category Structure**: Organized content hierarchy for navigation
- **Tag System**: Content discoverability and cross-referencing

### Content Management
- **Draft System**: Work-in-progress content management
- **Publishing Schedule**: Automated content release timing
- **Media Management**: Image galleries and file attachments
- **Comment Moderation**: Community interaction oversight

### Analytics and Performance
- **View Tracking**: Popular content identification
- **Engagement Metrics**: Comment and sharing statistics
- **Category Performance**: Content area analysis
- **User Behavior**: Reading patterns and content preferences

---

**Note**: This demonstrates comprehensive blog CMS patterns with content management, reader engagement, and publishing workflows suitable for corporate blogs, technical documentation, content marketing platforms, and community-driven publishing sites. All content includes realistic data for immediate testing and development.
