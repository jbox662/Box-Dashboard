# GitHub Repository Setup Guide

This guide will help you set up a GitHub repository for HACS distribution.

## Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `ha-auto-dashboard` (or your preferred name)
3. Description: "Auto-generated dashboard for Home Assistant with zero configuration"
4. Make it **Public** (required for HACS)
5. **Do NOT** initialize with README (we have our own)
6. Click "Create repository"

## Step 2: Upload Files

### Option A: Via GitHub Web Interface

1. On your new repository page, click "uploading an existing file"
2. Drag and drop these files:
   - `dist/ha-auto-dashboard.js`
   - `hacs.json`
   - `README.md`
   - `info.md`
   - `LICENSE`
   - `INSTALLATION.md`
3. Commit message: "Initial commit"
4. Click "Commit changes"

### Option B: Via Git Command Line

```bash
cd /path/to/ha-auto-dashboard-hacs

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit"

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/ha-auto-dashboard.git

# Push
git branch -M main
git push -u origin main
```

## Step 3: Create a Release (Recommended)

1. Go to your repository on GitHub
2. Click "Releases" (right sidebar)
3. Click "Create a new release"
4. Tag version: `v1.0.0`
5. Release title: `v1.0.0 - Initial Release`
6. Description:
   ```markdown
   ## Initial Release
   
   ### Features
   - Auto-discovery of all Home Assistant entities
   - Smart organization by areas and domains
   - Modern dark theme
   - Responsive design
   - Real-time updates
   - Support for lights, switches, sensors, climate, covers, and more
   
   ### Installation
   See [INSTALLATION.md](INSTALLATION.md) for detailed instructions.
   ```
7. Click "Publish release"

## Step 4: Verify Repository Structure

Your repository should look like this:

```
ha-auto-dashboard/
├── dist/
│   └── ha-auto-dashboard.js
├── hacs.json
├── README.md
├── info.md
├── LICENSE
├── INSTALLATION.md
└── GITHUB_SETUP.md (optional)
```

## Step 5: Test Installation

### Add as Custom Repository in HACS

1. Open HACS in Home Assistant
2. Click three dots (⋮) → "Custom repositories"
3. Add your repository URL: `https://github.com/YOUR_USERNAME/ha-auto-dashboard`
4. Category: "Dashboard" (or "Plugin")
5. Click "Add"
6. Find it in the list and click "Download"
7. Follow installation instructions

## Step 6: Submit to HACS Default Repository (Optional)

Once tested and working, you can submit to HACS for easier discovery:

1. Go to https://github.com/hacs/default
2. Fork the repository
3. Edit `plugin` file (or appropriate category)
4. Add your repository URL
5. Create pull request
6. Wait for review and approval

### Requirements for HACS Default

- Repository must be public
- Must follow HACS repository structure
- Must have proper documentation
- Must be tested and working
- Must have a license
- Must follow HACS guidelines

## Repository Maintenance

### Updating the Dashboard

1. Make changes to source code
2. Rebuild: `pnpm run build && node combine-bundle.js`
3. Copy new `ha-auto-dashboard-bundle.js` to `dist/ha-auto-dashboard.js`
4. Commit and push:
   ```bash
   git add dist/ha-auto-dashboard.js
   git commit -m "Update dashboard to v1.1.0"
   git push
   ```
5. Create new release with new version tag

### Version Numbering

Follow Semantic Versioning (semver):
- `v1.0.0` - Initial release
- `v1.0.1` - Bug fixes
- `v1.1.0` - New features (backward compatible)
- `v2.0.0` - Breaking changes

### Changelog

Keep a CHANGELOG.md file:

```markdown
# Changelog

## [1.1.0] - 2025-01-15
### Added
- Entity search functionality
- Favorite entities

### Fixed
- Climate control temperature display

## [1.0.0] - 2025-01-01
### Added
- Initial release
- Auto-discovery
- Area and domain filtering
```

## Tips

1. **Use releases** - HACS prefers repositories with releases
2. **Good documentation** - Clear README and installation guide
3. **License** - Always include a license file
4. **Issues enabled** - Allow users to report issues
5. **Responsive** - Respond to issues and pull requests
6. **Testing** - Test thoroughly before releasing
7. **Screenshots** - Add screenshots to README
8. **Badges** - Add HACS badge to README

## HACS Badge

Add this to your README.md:

```markdown
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)
```

Once in HACS default:

```markdown
[![hacs_badge](https://img.shields.io/badge/HACS-Default-blue.svg)](https://github.com/custom-components/hacs)
```

## Support

### GitHub Features to Enable

1. **Issues** - For bug reports and feature requests
2. **Discussions** - For Q&A and community
3. **Wiki** - For additional documentation (optional)
4. **Sponsorship** - If you want to accept donations (optional)

### Templates

Create issue templates in `.github/ISSUE_TEMPLATE/`:

**bug_report.md:**
```markdown
---
name: Bug report
about: Create a report to help us improve
---

**Describe the bug**
A clear description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior.

**Expected behavior**
What you expected to happen.

**Screenshots**
If applicable, add screenshots.

**Environment:**
- Home Assistant version:
- HACS version:
- Browser:

**Additional context**
Any other context about the problem.
```

## Resources

- HACS Documentation: https://www.hacs.xyz/docs/publish/plugin/
- GitHub Docs: https://docs.github.com/
- Semantic Versioning: https://semver.org/
- Markdown Guide: https://www.markdownguide.org/

---

**Your repository is ready for HACS distribution! 🚀**

