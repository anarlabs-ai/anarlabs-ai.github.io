# Anarlabs Blog

Official blog for Anarlabs - Leading AI Company in UAE, built with Hugo and deployed on GitHub Pages.

🌐 **Live Site**: [https://anarlabs.ai](https://anarlabs.ai)

## 🚀 Quick Start

### Prerequisites

- [Hugo Extended v0.147.9+](https://gohugo.io/installation/)
- Git

### Local Development

1. Clone the repository:
```bash
git clone https://github.com/anarlabs-ai/anarlabs-ai.github.io.git
cd anarlabs-ai.github.io
```

2. Run the development server:
```bash
hugo server -D
```

3. Open your browser and visit: `http://localhost:1313`

## 📝 Creating Content

### Creating a New Blog Post

```bash
# Create a new blog post
hugo new posts/my-new-post/index.md
```

Or manually create a directory and file:
```bash
mkdir -p content/posts/my-new-post
```

Create `content/posts/my-new-post/index.md` with:
```markdown
---
title: "Your Post Title"
date: 2025-01-10T10:00:00+04:00
draft: false
author: "Author Name"  # Use one of: Abdullah Abdulwahab, Mohammed Khan, Salman, Mohammed Raz, Saad
description: "Brief description of your post"
tags: ["AI", "Machine Learning"]
categories: ["Technology"]
---

Your content goes here...
```

### Creating a New Page

```bash
# Create a new standalone page
hugo new page-name.md
```

Or manually create `content/page-name.md`:
```markdown
---
title: "Page Title"
date: 2025-01-10T10:00:00+04:00
draft: false
description: "Page description"
---

Page content goes here...
```

### Adding Images to Content

Place images in the same directory as your content:
```
content/posts/my-new-post/
├── index.md
├── image1.png
└── image2.jpg
```

Reference them in your markdown:
```markdown
![Alt text](image1.png)
```

## 🚢 Deployment

The site automatically deploys to GitHub Pages when you push to the `master` branch.

### Manual Deployment

1. Commit your changes:
```bash
git add .
git commit -m "Add new blog post"
```

2. Push to master:
```bash
git push origin master
```

3. GitHub Actions will automatically build and deploy your site. Check the deployment status at:
   - [Actions Tab](https://github.com/anarlabs-ai/anarlabs-ai.github.io/actions)

## 📁 Project Structure

```
.
├── archetypes/          # Content templates
├── content/            # Blog posts and pages
│   ├── about/         # About page
│   ├── authors/       # Author profiles
│   ├── posts/         # Blog posts
│   ├── contact.md     # Contact page
│   └── privacy.md     # Privacy page
├── config/            # Hugo configuration
│   ├── _default/      # Default config
│   ├── development/   # Dev environment config
│   └── production/    # Production config
├── public/            # Generated site (don't edit)
├── themes/            # Hugo themes
│   └── PaperMod/     # Current theme
└── .github/           # GitHub Actions workflows
    └── workflows/
        └── hugo.yaml  # Deployment workflow
```

## ⚙️ Configuration

Main configuration files are in `config/_default/`:
- `config.yaml` - Main Hugo configuration
- `params.yaml` - Site parameters and theme settings
- `menu.yaml` - Navigation menu configuration

### Changing Site Settings

Edit `config/_default/params.yaml`:
```yaml
title: Anarlabs
description: "Anarlabs - Leading AI Company in UAE"
author: 
  name: "Anarlabs Team"
```

### Updating Navigation Menu

Edit `config/_default/menu.yaml` to add/remove menu items.

## 🎨 Theme

This site uses the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

### Theme Documentation
- [PaperMod Wiki](https://github.com/adityatelange/hugo-PaperMod/wiki)
- [Features](https://github.com/adityatelange/hugo-PaperMod/wiki/Features)
- [Variables](https://github.com/adityatelange/hugo-PaperMod/wiki/Variables)

## 🛠️ Common Commands

```bash
# Start development server
hugo server -D

# Build the site
hugo

# Build with drafts
hugo -D

# Create new post
hugo new posts/post-name/index.md

# Create new page
hugo new page-name.md

# Update theme
git submodule update --remote --merge
```

## 🐛 Troubleshooting

### Build Errors
1. Make sure you have Hugo Extended version installed:
   ```bash
   hugo version
   ```
   Should show: `hugo v0.147.9-... +extended`

2. Clear Hugo cache:
   ```bash
   hugo --gc
   ```

### Theme Issues
1. Update submodules:
   ```bash
   git submodule update --init --recursive
   ```

### Local Development Issues
1. Kill existing Hugo server:
   ```bash
   pkill hugo
   ```

2. Try a different port:
   ```bash
   hugo server -D -p 1314
   ```

## 📄 License

Content is copyright Anarlabs. Theme is MIT licensed.

## 🤝 Contributing

Feel free to submit issues or pull requests if you find any problems.

---

## 📚 Available Authors

When creating posts, use one of these author names in the frontmatter:
- Abdullah Abdulwahab
- Mohammed Khan
- Salman
- Mohammed Raz
- Saad

**Note**: When writing new posts, remember to:
1. Set `draft: false` when ready to publish
2. Include an author from the list above
3. Add relevant tags and categories