# TD SYNNEX Knowledge Bridge - Developer Guide

A dynamic knowledge base system for TD SYNNEX integration documentation across multiple PSA platforms.

## How It Works

This knowledge base uses **static HTML pages** that **dynamically load markdown content**. Each platform has its own HTML page that fetches and renders `.md` files on demand.

```
HTML Page (UI Shell) + Markdown Files (Content) = Dynamic Knowledge Base
```

## System Architecture

### 1. Platform Structure
Each platform follows the same pattern:

```
   Platform Folder/                     Platform HTML Page
├── article1.md       ←──── loads ←──── platform-kb.html
├── article2.md                         (navigation + rendering)
├── article3.md
└── images referenced ←──── points to ←─── 📁 public/assets/images/
```

### 2. Current Platforms
- **ConnectWise PSA** → `connectwise-psa-kb.html` loads from `connectwise/` folder
- **Autotask PSA** → `autotask-psa-kb.html` loads from `autotask/` folder  
- **ServiceNow** → `servicenow-kb.html` loads from `servicenow/` folder
- **Microsoft Apps** → `microsoft-apps-kb.html` loads from `msapps/` folder

## Markdown Files (.md) - How They Work

### Simple Rule: Write Markdown, It Shows Up Instantly

1. **Create a markdown file** in the platform folder (e.g., `connectwise/my-article.md`)
2. **Add it to the navigation** in the HTML page
3. **That's it!** The content appears when users click the nav link

### 📷 Images in Markdown

All images must be in `public/assets/images/` and referenced like this:

```markdown
![Description](/public/assets/images/filename.png)
```

**Examples:**
```markdown
![ConnectWise Login](/public/assets/images/cw-login-screen.png)
![Setup Step 1](/public/assets/images/setup-step1.jpeg)
```

## Adding New Content

### Add a New Article to Existing Platform

1. **Create the markdown file:**
   ```bash
   # Example: Add new ConnectWise article
   touch connectwise/kb_new_feature.md
   ```

2. **Write your content:**
   ```markdown
   # My New Feature Guide
   
   This explains how to use the new feature...
   
   ![Screenshot](/public/assets/images/new-feature-screen.png)
   ```

3. **Add to navigation** in `connectwise-psa-kb.html`:
   ```html
   <ul class="kb-nav">
       <!-- existing articles -->
       <li><a href="#" data-article="kb_new_feature.md" class="kb-article-link">New Feature Guide</a></li>
   </ul>
   ```

4. **Add to main index** in `index.html`:
   ```javascript
   // ConnectWise articles
   { category: 'ConnectWise PSA', title: 'New Feature Guide', file: 'kb_new_feature.md', url: 'connectwise-psa-kb.html' },
   ```

### Add a New Platform

1. **Create the folder and HTML page:**
   ```bash
   mkdir newplatform/
   cp servicenow-kb.html newplatform-kb.html
   ```

2. **Update the HTML page:**
   - Change the page title and breadcrumb
   - Update the `fetch()` path: `fetch('newplatform/${articlePath}')`
   - Update navigation links to point to your new markdown files

3. **Add to main navigation** in `index.html`:
   ```html
   <a href="newplatform-kb.html" class="tile">
       <h3>New Platform</h3>
       <p>Integration guides for New Platform</p>
   </a>
   ```

## Technical Details

### How Markdown Rendering Works

Each platform HTML page includes:

```html
<!-- Markdown parser -->
<script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>

<script>
// Loads and renders markdown
async function loadArticle(articlePath) {
    const response = await fetch(`platform-folder/${articlePath}`);
    const markdown = await response.text();
    const html = marked.parse(markdown);  // ← Converts MD to HTML
    document.getElementById('article-content').innerHTML = html;
}
</script>
```

### Image Styling

Images are automatically styled with:
- Max width: 800px
- Centered display
- Rounded corners with shadows
- Crisp rendering (no blur)

### Navigation System

Each sidebar link has a `data-article` attribute:

```html
<li><a href="#" data-article="filename.md" class="kb-article-link">Display Name</a></li>
```

When clicked, JavaScript loads that specific markdown file and renders it.

## File Naming Convention

Use descriptive, prefixed filenames:

```
Good:
kb_prerequisites_api.md
kb_connect_activation.md  
kb_template_products.md

Bad:
article1.md
setup.md
guide.md
```

## Development Workflow

### Start the Server
```bash
npm start
# Opens http://localhost:8081
```

###  Edit Content
1. Edit any `.md` file
2. Refresh browser to see changes
3. No build step needed!

###  Add Images
1. Put image in `public/assets/images/filename.png`
2. Reference in markdown: `![Alt text](/public/assets/images/filename.png)`
3. Refresh page to see image

## Common Tasks

### Update Article Order
Reorder the `<li>` elements in the platform HTML file's navigation.

### Change Article Titles
Update both:
1. The link text in the HTML navigation
2. The title in `index.html` articles array

### Fix Broken Images
1. Check the file exists in `public/assets/images/`
2. Verify the path in markdown starts with `/public/assets/images/`
3. Check the file extension matches (`.png`, `.jpeg`, `.jpg`)

## Architecture Benefits

**Simple**: Edit markdown, see changes instantly  
**Fast**: No build process, pure client-side rendering  
**Maintainable**: Content separated from presentation  
**Scalable**: Easy to add new platforms and articles  
**Modern**: Uses standard web technologies

## Support

For technical questions about this knowledge base system:
- Review this README
- Check existing platform implementations as examples
- Test changes locally with `npm start`

---

**Remember: This system is designed to be simple. Write markdown, add navigation links, and it works!**