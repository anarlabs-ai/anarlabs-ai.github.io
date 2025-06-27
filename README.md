# Abdullah's Blog

Personal blog built with Hugo and deployed on GitHub Pages.

🌐 **Live Site**: [https://abdullamd.com](https://abdullamd.com)

## 🚀 Quick Start

### Prerequisites

- [Hugo Extended v0.147.9+](https://gohugo.io/installation/)
- Git

### Local Development

1. Clone the repository:
```bash
git clone https://github.com/Abdullamhd/Abdullamhd.github.io.git
cd Abdullamhd.github.io
```

2. Run the development server:
```bash
hugo server -D
```

3. Open your browser and visit: `http://localhost:1313`

## 📝 Writing a New Blog Post

### Method 1: Using Hugo Command (Recommended)

```bash
# For a post in a specific category
hugo new content/ai/my-new-post/index.md
hugo new content/automation/my-new-post/index.md
hugo new content/data/my-new-post/index.md
hugo new content/general/my-new-post/index.md
```

### Method 2: Manual Creation

1. Create a new directory in the appropriate category folder:
```bash
mkdir content/ai/my-new-post
```

2. Create an `index.md` file with the following frontmatter:
```markdown
---
title: "Your Post Title"
date: 2025-06-27T10:00:00+04:00
draft: false
description: "Brief description of your post"
tags: ["tag1", "tag2"]
categories: ["AI"]
---

Your content goes here...
```

### Adding Images to Posts

Place images in the same directory as your post:
```
content/ai/my-new-post/
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
   - [Actions Tab](https://github.com/Abdullamhd/Abdullamhd.github.io/actions)

## 📁 Project Structure

```
.
├── archetypes/          # Content templates
├── content/            # Blog posts and pages
│   ├── about/         # About page
│   ├── ai/            # AI category posts
│   ├── automation/    # Automation category posts
│   ├── data/          # Data category posts
│   ├── general/       # General category posts
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
title: Abdullah
description: "Abdullah Mohammed Personal blog"
author: 
  name: "Abdullah Mohammed"
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
hugo new content/category/post-name/index.md

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

Content is copyright Abdullah Mohammed. Theme is MIT licensed.

## 🤝 Contributing

Feel free to submit issues or pull requests if you find any problems.

---

**Note**: When writing new posts, remember to set `draft: false` in the frontmatter when you're ready to publish!