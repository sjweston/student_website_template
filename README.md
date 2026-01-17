# Academic Website Template

A clean, professional academic website template for graduate students built with [Hugo](https://gohugo.io/) and [Hugo Blox Builder](https://hugoblox.com/). This template is designed to be easy to customize, even for users with minimal coding experience.

## Features

- Clean, modern design with customizable color themes
- Sections for publications, projects, teaching, blog posts, and CV
- Automatic publication management from BibTeX files
- Responsive design (works on desktop and mobile)
- Fast loading times
- Easy deployment to GitHub Pages
- Optional custom domain support

## Live Demo

See an example of this template in action [here](https://sarajweston.com/student_website_template/)

## Quick Start

### 1. Clone or Download This Repository

**Option A: Clone with Git**
```bash
git clone https://github.com/yourusername/academic-website-template.git
cd academic-website-template
```

**Option B: Download as ZIP**
1. Click the green "Code" button above
2. Select "Download ZIP"
3. Extract the ZIP file and navigate to the folder

### 2. Install Prerequisites

This template requires two tools: Hugo (the website generator) and Go (needed for theme modules).

#### Install Hugo

Hugo is the static site generator that powers your website.

**macOS:**
```bash
brew install hugo
```

**Windows:**
Download from [Hugo Releases](https://github.com/gohugoio/hugo/releases) or use:
```bash
choco install hugo-extended
```

**Linux:**
```bash
sudo apt-get install hugo
```

**Verify installation:**
```bash
hugo version
```

You should see version 0.136.5 or higher.

#### Install Go

Go is required for Hugo to download and manage the theme modules.

**macOS:**
```bash
brew install go
```

**Windows:**
Download from [Go Downloads](https://go.dev/dl/) or use:
```bash
choco install golang
```

**Linux:**
```bash
sudo apt-get install golang
```

**Verify installation:**
```bash
go version
```

You should see Go version 1.19 or higher.

### 3. Download Theme Modules

Before running the site for the first time, download the required theme modules:

```bash
hugo mod get -u
```

This downloads the Hugo Blox theme components (only needed once).

### 4. Preview Your Site Locally

```bash
hugo server
```

Open your browser and go to `http://localhost:1313` to see your site!

Press `Ctrl+C` to stop the server.

## Personalizing Your Website

### Step 1: Update Basic Information

#### Edit `config/_default/hugo.yaml`

Change these lines:
```yaml
title: Your Name  # Change to your name
baseURL: 'https://yourusername.github.io/'  # Change to your GitHub username
```

#### Edit `config/_default/params.yaml`

Update the following:
```yaml
appearance:
  color: ocean  # Choose a color theme (see below for options)

marketing:
  seo:
    org_name: 'Your Name'  # Your name
    twitter: ''  # Your Twitter handle (optional)

header:
  navbar:
    logo:
      text: "Your Name"  # Your name

footer:
  copyright:
    notice: '© {year} Your Name. This work is licensed under {license}'
```

**Available color themes:** ocean, emerald, forest, dark, minimal, mr robot, strawberry, coffee, rose, earth, and more. See the [full list here](https://docs.hugoblox.com/getting-started/customization/#appearance).

### Step 2: Update Your Profile

Edit `content/authors/admin/_index.md` with your information:

1. **Basic info:** Change `title`, `first_name`, `last_name`, `role`, and organization
2. **Social links:** Update email, GitHub, LinkedIn, Google Scholar, and ORCID URLs
3. **Research interests:** List your areas of interest
4. **Education:** Add your degrees (PhD, MS, BS, etc.)
5. **Work experience:** List your current and past positions
6. **Skills:** Update technical skills and percentages
7. **About Me:** Write a brief bio in the section at the bottom

### Step 3: Add Your Photo

Replace `content/authors/admin/avatar.jpg` with your own photo:
- Recommended size: 512x512 pixels (square)
- Supported formats: JPG, PNG
- Filename must be `avatar.jpg` or `avatar.png`

### Step 4: Customize the Homepage

Edit `content/_index.md` to modify what appears on your homepage:

- **Research Overview:** Update the text in the `markdown` block
- **Sections:** You can comment out (add `#` before each line) or remove sections you don't want
- **Add sections:** Copy existing block structure to add new sections

Example - to hide the Featured Publications section:
```yaml
# - block: collection
#   id: featured
#   content:
#     title: Featured Publications
```

## Adding Content

### Adding Publications

You have two options for adding publications:

#### Option 1: Using BibTeX (Recommended for Multiple Publications)

1. **Add entries to `publications.bib`:**

   Your file should look like this:
   ```bibtex
   @article{yourname_title_2024,
       title = {Your Paper Title},
       author = {Your Name and Coauthor Name},
       journal = {Journal Name},
       year = {2024},
       doi = {10.1000/example.doi},
       abstract = {Your abstract here...},
   }
   ```

2. **Run the Python script to generate publication folders:**
   ```bash
   python create_pubs.py
   ```

   This will automatically create folders under `content/publication/` with properly formatted files.

3. **Optional:** To make a publication "featured" (highlighted on your homepage):
   - Open the publication's `index.md` file
   - Change `featured: false` to `featured: true`

#### Option 2: Manual Creation

1. Create a new folder in `content/publication/` (e.g., `my-paper-2024`)
2. Inside that folder, create an `index.md` file:

```yaml
---
title: 'Your Paper Title'
authors:
- Your Name
- Coauthor Name
date: '2024-01-01'
publishDate: '2024-01-01T00:00:00Z'
publication_types:
- article-journal  # or paper-conference, chapter, book, etc.
publication: '*Journal Name*'
doi: 10.1000/example.doi
abstract: |
  Your abstract here.
tags:
- Machine Learning
- NLP
featured: false  # Set to true to feature on homepage
url_pdf: ''  # Link to PDF
url_code: ''  # Link to code repository
---

Additional details about your paper can go here.
```

### Adding Projects

1. Create a new folder in `content/project/` (e.g., `my-cool-project`)
2. Create an `index.md` file inside:

```yaml
---
title: Project Title
summary: A brief one-sentence description.
tags:
- Machine Learning
- Python
date: '2024-01-01'
external_link: ''  # Leave empty for internal page, or add GitHub URL
url_code: 'https://github.com/yourusername/project'
url_pdf: ''
url_slides: ''
url_video: ''
---

## Project Description

Detailed description of your project goes here. You can use:

- Markdown formatting
- **Bold** and *italic* text
- Code blocks
- Images
- Links

## Technologies Used

List the technologies, frameworks, and tools you used.
```

### Adding Blog Posts

1. Create a new folder in `content/post/` (e.g., `my-first-post`)
2. Create an `index.md` file:

```yaml
---
title: Your Blog Post Title
subtitle: Optional subtitle
summary: A brief summary that appears in the blog list.
date: '2024-01-15'
authors:
- admin
tags:
- Research
- Tutorial
categories:
- General
---

Your blog post content goes here. Write in Markdown!

## Section Headers

You can organize your post with headers.

### Subsections

And subsections too.

- Bullet points
- Are supported
- As well

1. Numbered lists
2. Also work
3. Great!

You can include **bold**, *italic*, and `code` formatting.

\```python
# And code blocks
def hello_world():
    print("Hello, world!")
\```
```

### Adding Teaching

1. Create a new folder in `content/teaching/` (e.g., `course-name`)
2. Create an `index.md` file:

```yaml
---
title: Course Name (CS 101)
summary: Teaching Assistant, Fall 2024
date: '2024-09-01'
type: teaching
tags:
- Teaching
- Course Topic
---

## Course Description

Describe what the course covers.

## My Role

What you did as a TA or instructor.

## Topics Covered

- Topic 1
- Topic 2
- Topic 3
```

## Using GitHub Desktop (Recommended for Beginners)

If you're not comfortable with Git commands in the terminal, [GitHub Desktop](https://desktop.github.com/) provides an easy-to-use graphical interface for managing your repository.

### Setup with GitHub Desktop

1. **Download and install GitHub Desktop** from [desktop.github.com](https://desktop.github.com/)

2. **Sign in to GitHub** in the app (File → Options → Accounts on Windows, or GitHub Desktop → Preferences → Accounts on Mac)

3. **Clone your repository:**
   - In GitHub Desktop: File → Clone Repository
   - Select your `yourusername.github.io` repository
   - Choose where to save it on your computer
   - Click "Clone"

4. **Make changes to your files** using any text editor (VS Code, Sublime Text, or even TextEdit/Notepad)

5. **Commit and push changes:**
   - Open GitHub Desktop
   - You'll see all your changed files on the left
   - Write a summary of your changes (e.g., "Updated my profile information")
   - Click "Commit to main"
   - Click "Push origin" to upload your changes to GitHub

6. **GitHub Actions will automatically deploy** your changes in a few minutes

### Alternative: Using Git in Terminal

If you prefer using the terminal:

```bash
# First, make sure you're in the correct directory
cd path/to/your/website/folder

# Verify you're in the right place (should show your website directory)
pwd

# Should show files like config/, content/, etc.
ls

# Make your changes to files, then commit and push:
git add .
git commit -m "Description of your changes"
git push
```

**⚠️ Common mistake:** Running git commands in the wrong directory. Always use `pwd` to verify you're in your website folder before running git commands.

## Deployment

### Deploying to GitHub Pages

1. **Create a GitHub repository:**
   - Go to [GitHub](https://github.com) and create a new repository
   - Name it `yourusername.github.io` (replace `yourusername` with your actual GitHub username)
   - Make it public

2. **Update your baseURL in `config/_default/hugo.yaml`:**
   ```yaml
   baseURL: 'https://yourusername.github.io/'
   ```

3. **Push your code to GitHub:**

   **Using GitHub Desktop:** Follow the steps in the "Using GitHub Desktop" section above.

   **Using Terminal:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/yourusername.github.io.git
   git push -u origin main
   ```

4. **Set up GitHub Actions for automatic deployment:**

   Create a file `.github/workflows/hugo.yaml` with this content:

   ```yaml
   name: Deploy Hugo site to Pages

   on:
     push:
       branches:
         - main
     workflow_dispatch:

   permissions:
   contents: read
     pages: write
     id-token: write

   concurrency:
     group: "pages"
     cancel-in-progress: false

   defaults:
     run:
       shell: bash

   jobs:
     build:
       runs-on: ubuntu-latest
       env:
         HUGO_VERSION: 0.136.5
       steps:
         - name: Install Hugo CLI
           run: |
             wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
             && sudo dpkg -i ${{ runner.temp }}/hugo.deb
         - name: Checkout
           uses: actions/checkout@v4
           with:
             submodules: recursive
             fetch-depth: 0
         - name: Setup Pages
           id: pages
           uses: actions/configure-pages@v4
         - name: Install Node.js dependencies
           run: "[[ -f package-lock.json || -f npm-shrinkwrap.json ]] && npm ci || true"
         - name: Build with Hugo
           env:
             HUGO_ENVIRONMENT: production
             HUGO_ENV: production
           run: |
             hugo \
               --gc \
               --minify \
               --baseURL "${{ steps.pages.outputs.base_url }}/"
         - name: Upload artifact
           uses: actions/upload-pages-artifact@v3
           with:
             path: ./public

     deploy:
       environment:
         name: github-pages
         url: ${{ steps.deployment.outputs.page_url }}
       runs-on: ubuntu-latest
       needs: build
       steps:
         - name: Deploy to GitHub Pages
           id: deployment
           uses: actions/deploy-pages@v4
   ```

5. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Click "Settings" → "Pages"
   - Under "Source", select "GitHub Actions"

6. **Wait for deployment:**
   - Go to the "Actions" tab to see the deployment progress
   - Once complete, visit `https://yourusername.github.io`

### Using a Custom Domain (Optional)

1. **Buy a domain** from a registrar (Porkbun, Namecheap, Google Domains, etc.)

2. **Add your custom domain to GitHub:**
   - In your repository, go to Settings → Pages
   - Under "Custom domain", enter your domain (e.g., `www.yourname.com`)
   - Click "Save"

3. **Configure DNS with your registrar:**
   - Add a `CNAME` record pointing `www` to `yourusername.github.io`
   - Or add `A` records pointing to GitHub's IP addresses:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153

4. **Update baseURL in `config/_default/hugo.yaml`:**
   ```yaml
   baseURL: 'https://www.yourname.com/'
   ```

5. **Wait for DNS propagation** (can take up to 24 hours)

## Customization Tips

### Changing Colors and Themes

Edit `config/_default/params.yaml`:
```yaml
appearance:
  mode: system  # Options: system, light, dark
  color: ocean  # Choose from available themes
```

### Hiding/Showing Sections

In `content/_index.md` and other pages, comment out sections you don't want:
```yaml
# - block: collection
#   id: projects
#   content:
#     title: Projects
```

### Adding Menu Items

Edit `config/_default/menus.yaml` to add, remove, or reorder menu items:
```yaml
main:
  - name: New Page
    url: /newpage/
    weight: 70  # Higher numbers appear later in the menu
```

### Adding a CV/Resume PDF

1. Add your PDF to `static/uploads/resume.pdf`
2. It will be accessible at the "Download CV" button on your homepage

## Troubleshooting

### Common Issues

#### Working in the wrong directory
**Problem:** Running `hugo server` or git commands in the wrong folder.

**Solution:**
1. Open Terminal/Command Prompt
2. Use `cd` to navigate to your website folder:
   ```bash
   cd path/to/your/website/folder
   ```
3. Verify you're in the right place:
   ```bash
   pwd    # Shows current directory
   ls     # Should list: config/, content/, static/, etc.
   ```

#### Forgot to change the title in hugo.yaml
**Problem:** Site breaks because the title field in `config/_default/hugo.yaml` wasn't updated properly.

**Solution:**
1. Open `config/_default/hugo.yaml`
2. Make sure line 7 has a valid title (no special characters like `_` at the start):
   ```yaml
   title: Your Name  # ✓ Good
   title: _Your Name  # ✗ Bad - remove the underscore
   ```
3. Save the file and run `hugo server` again

#### File naming issues causing caching problems
**Problem:** Created files with wrong names (e.g., `_index.md` instead of `index.md` in blog post folders).

**Solution:**
- Blog posts should be in folders like `content/post/my-post/index.md`
- NOT `content/post/my-post/_index.md`
- If you renamed files, clear Hugo's cache:
  ```bash
  hugo mod clean
  rm -rf public/
  hugo server
  ```

#### SSH key setup for GitHub
**Problem:** GitHub asks for password repeatedly or authentication fails.

**Solution:** Set up an SSH key:
1. Generate a new SSH key:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```
   Press Enter to accept the default location, and optionally add a passphrase.

2. Copy your public key:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

3. Add to GitHub:
   - Go to GitHub.com → Click your profile picture → Settings
   - Click "SSH and GPG keys" (left sidebar)
   - Click "New SSH key"
   - Give it a title (like "My MacBook")
   - Paste your key
   - Click "Add SSH key"

4. When cloning repositories, use the SSH URL instead of HTTPS:
   ```bash
   git clone git@github.com:yourusername/yourusername.github.io.git
   ```

### Installation Issues

#### "binary with name 'go' not found in PATH"
**Problem:** Go is not installed. The Hugo Blox theme requires Go to download theme modules.

**Solution:** Install Go:
- macOS: `brew install go`
- Windows: Download from [go.dev/dl](https://go.dev/dl/) or `choco install golang`
- Linux: `sudo apt-get install golang`

After installing Go, run `hugo mod get` then `hugo server` again.

#### "Hugo command not found"
**Problem:** Hugo is not installed or not in your system PATH.

**Solution:**
1. Install Hugo (see Prerequisites section)
2. Verify installation: `hugo version`
3. If installed but not found, check your PATH environment variable

### Site Building Issues

#### Site looks broken locally
**Solutions:**
1. Make sure you're running `hugo server` from the root directory (where `config/` folder is)
2. Check that all required files are present
3. Try stopping the server (Ctrl+C) and restarting it
4. Make sure both Hugo and Go are installed
5. Clear the cache:
   ```bash
   hugo mod clean
   rm -rf public/ resources/
   hugo server
   ```

### Changes not appearing on GitHub Pages
1. Check the Actions tab for build errors
2. Make sure your baseURL is correct
3. Wait a few minutes for the build to complete
4. Clear your browser cache

### Publications not showing up
1. Make sure publication folders have an `index.md` file
2. Check that the `date` field is set correctly
3. Run the Python script again if using BibTeX: `python create_pubs.py`

## Support and Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [Hugo Blox Documentation](https://docs.hugoblox.com/)
- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

## License

This template is based on the Hugo Academic CV theme, which is licensed under the MIT License. You are free to use, modify, and distribute this template for your own academic website.

## Credits

- Built with [Hugo](https://gohugo.io/)
- Theme: [Hugo Blox Builder](https://hugoblox.com/)
- Template created for graduate students and early-career researchers

---

**Good luck with your website!** If you have questions or run into issues, check the troubleshooting section above or consult the Hugo and Hugo Blox documentation.
