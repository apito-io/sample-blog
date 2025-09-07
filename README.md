# Blog CMS - Apito Engine Template

📝 **A complete blog content management system with posts, categories, tags, and user management**

[![Apito Engine](https://img.shields.io/badge/Apito-Engine-blue?style=flat&logo=graphql)](https://apito.io)
[![Project Type](https://img.shields.io/badge/Project%20Type-General-green?style=flat)](#project-type)
[![Models](https://img.shields.io/badge/Models-6-orange?style=flat)](#data-models)
[![Sample Data](https://img.shields.io/badge/Sample%20Data-93%20Files-purple?style=flat)](#sample-data)

## 🚀 Quick Start

1. **Import Schema**: Use `schema.json` to set up your Apito Engine project
2. **Configure Project**: Reference `config.yml` for project metadata
3. **Load Sample Data**: Import the `data/` folder for realistic examples
4. **Customize**: Modify fields and relationships as needed

## 📋 Project Overview

### **Project Type**

- **General Project** (Single-tenant)
- **Difficulty Level**: Beginner
- **Category**: Content Management

### **Key Features**

- ✅ Multi-author support
- ✅ Category organization
- ✅ Tag system
- ✅ Media management
- ✅ Comment system
- ✅ User roles
- ✅ Complete sample data with relationships
- ✅ UUID-based data files

## 🏗️ Data Models

This template includes **6 models** with **8 relationships**:

### **📄 Post Model**

Primary content model for blog articles.

**Fields:**

- `title` (text) - Article title
- `slug` (text) - URL-friendly identifier
- `content` (multiline) - Article content (HTML, Markdown, Plain text)
- `excerpt` (text) - Brief article summary
- `featured_image` (media) - Cover image
- `publish_date` (date) - Publication date
- `status` (list) - Published, Draft, Private
- `author_name` (text) - Author display name
- `author_email` (text) - Author email
- `category_id` (relation) - Associated category
- `meta_title` (text) - SEO title
- `meta_description` (text) - SEO description

**Relations:**

- `belongs_to` Category (has_one)
- `has_many` Comments

### **📂 Category Model**

Content categorization system.

**Fields:**

- `name` (text) - Category name
- `slug` (text) - URL-friendly identifier
- `description` (multiline) - Category description
- `featured_image` (media) - Category image
- `color` (text) - Theme color

**Relations:**

- `has_many` Posts

### **💬 Comment Model**

User feedback and discussion system.

**Fields:**

- `author_name` (text) - Commenter name
- `author_email` (text) - Commenter email
- `content` (multiline) - Comment content
- `status` (list) - Approved, Pending, Spam
- `created_at` (date) - Comment date
- `post_id` (relation) - Associated post

**Relations:**

- `belongs_to` Post (has_one)

### **🏷️ Tag Model**

Content tagging system.

**Fields:**

- `name` (text) - Tag name
- `slug` (text) - URL-friendly identifier
- `description` (text) - Tag description

### **👤 User Model**

Author and user management.

**Fields:**

- `username` (text) - Unique username
- `email` (text) - User email
- `display_name` (text) - Public display name
- `bio` (multiline) - Author biography
- `avatar` (media) - Profile picture
- `role` (list) - Admin, Editor, Author, Subscriber
- `status` (list) - Active, Inactive, Suspended

### **⚙️ Setting Model**

Site configuration and preferences.

**Fields:**

- `key` (text) - Setting identifier
- `value` (text) - Setting value
- `description` (text) - Setting description
- `type` (list) - Text, Number, Boolean, JSON

## 📊 Sample Data

The template includes **93 sample data files** with realistic content:

### **Data Structure**

```
data/
├── post/           # 30 blog posts
│   ├── [uuid].json # Individual post files
│   └── relation.json
├── category/       # 10 categories
│   ├── [uuid].json # Individual category files
│   └── relation.json
└── comment/        # 50 comments
    ├── [uuid].json # Individual comment files
    └── relation.json
```

### **Sample Data Features**

- **30 Blog Posts** - Complete articles with HTML/Markdown content
- **10 Categories** - Tech, Business, Lifestyle, etc.
- **50 Comments** - Realistic user feedback
- **UUID-based Filenames** - Proper unique identifiers
- **Complete Relationships** - All foreign keys properly linked
- **Realistic Content** - Professional sample text and descriptions

### **Relationship Format**

```json
{
  "post-uuid": {
    "category": {
      "relation_type": "has_one",
      "id": "category-uuid" // Single string for has_one
    },
    "comment": {
      "relation_type": "has_many",
      "ids": ["comment-uuid-1"] // Array for has_many
    }
  }
}
```

## 🎯 Use Cases

Perfect for building:

- **Personal Blogs** - Individual content creators
- **Company Blogs** - Corporate content marketing
- **News Websites** - Multi-author news platforms
- **Documentation Sites** - Technical documentation
- **Multi-author Platforms** - Community-driven content

## 🔧 Technical Details

### **Field Types Used**

- `text` - Short text inputs
- `multiline` - Rich content with HTML/Markdown support
- `media` - Image and file uploads
- `date` - Publication dates
- `list` - Fixed option selections

### **Validation Rules**

- Required fields for essential data
- Unique constraints for slugs and identifiers
- Relationship integrity maintained

### **GraphQL Schema**

Automatically generates a complete GraphQL API with:

- Queries for all models
- Mutations for CRUD operations
- Relationship resolution
- Filtering and pagination

## 📦 Installation

### **Option 1: Apito Engine Dashboard**

1. Create new project in Apito Dashboard
2. Import `schema.json`
3. Load sample data from `data/` folder

### **Option 2: Apito CLI**

```bash
# Clone this repository
git clone https://github.com/apito-io/sample-blog

# Import schema
apito import schema.json

# Load sample data
apito import data/
```

### **Option 3: Manual Setup**

1. Copy `schema.json` content
2. Create models in Apito Dashboard
3. Import data files individually

## 🔄 Data Generation

To regenerate or customize sample data:

```bash
# Using the Apito Data Generator (Go version)
./apito-gen

# Using Node.js version
node apito-data-generator.js
```

Both tools will generate fresh sample data based on the schema definition.

## 📚 Documentation

- **Schema Guide**: Complete field and relationship documentation
- **API Reference**: GraphQL query and mutation examples
- **Customization**: How to modify models and add fields
- **Deployment**: Production setup and configuration

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Support

- **Documentation**: [Apito Engine Docs](https://docs.apito.io)
- **Community**: [Apito Discord](https://discord.gg/apito)
- **Issues**: [GitHub Issues](https://github.com/apito-io/sample-blog/issues)
- **Email**: support@apito.io

---

**Built with ❤️ using [Apito Engine](https://apito.io) - The GraphQL Backend-as-a-Service Platform**
