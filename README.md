# J/22 Southwest District Website

Official website for the J/22 Southwest District sailboat racing community.

🌐 **Live Site:** [https://j22southwest.org](https://j22southwest.org)

## Contributing

We welcome contributions from the J/22 Southwest community! Whether you want to update regatta information, add links, or fix typos, we appreciate your help.

### How to Make Changes

#### Option 1: Edit Directly on GitHub (Easiest)

1. Navigate to the file you want to edit (usually in `website/` folder)
2. Click the pencil icon (✏️) to edit
3. Make your changes
4. Scroll down and click "Propose changes"
5. Click "Create pull request"
6. Wait for a maintainer to review and merge

#### Option 2: Using Git (Recommended for Multiple Changes)

1. **Fork or clone this repository**
   ```bash
   git clone https://github.com/cfullerton/j22southwest.git
   cd j22southwest
   ```

2. **Create a new branch**
   ```bash
   git checkout -b my-changes
   ```

3. **Make your edits** to files in the `website/` folder

4. **Commit and push**
   ```bash
   git add .
   git commit -m "Brief description of your changes"
   git push -u origin my-changes
   ```

5. **Create a Pull Request**
   - Go to https://github.com/cfullerton/j22southwest
   - Click "Pull requests" → "New pull request"
   - Select your branch and click "Create pull request"

6. **Wait for review** - A maintainer will review and merge your changes

### What You Can Edit

#### **Upcoming Events** (`website/index.html`)
Add or update regatta dates, locations, and registration links.

#### **Results** (`website/results.html`)
Add past regatta results and links.

#### **Media & Links** (`website/media.html`)
Update yacht club links, add photos, or include useful sailing resources.

#### **Styling** (`website/css/style.css`)
Adjust colors, fonts, or layout.

### Testing Your Changes Locally

Before submitting a PR, you can preview your changes:

```bash
cd website
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

### After You Submit

Once your pull request is merged to `main`:
- ✅ GitHub Actions automatically deploys to the live site
- ✅ Changes appear at https://j22southwest.org within 1-2 minutes
- ✅ No manual deployment needed!

## Website Structure

```
website/
├── index.html       # Home page with upcoming regattas
├── results.html     # Past regatta results
├── media.html       # Media, photos, and useful links
├── css/
│   └── style.css    # Site styling
└── images/          # Images and photos
```

## Contact Information

- **District Governor:** Colin Feik (colin.feik@gmail.com)
- **District Treasurer:** Kevin Orff (Kevin.Orff@gmail.com)
- **Website Issues:** Create an issue on this repository

## Technical Details

- **Hosting:** AWS S3 + CloudFront CDN
- **Deployment:** Automatic via GitHub Actions on merge to `main`
- **SSL/HTTPS:** AWS Certificate Manager

---

© J/22 Southwest District
