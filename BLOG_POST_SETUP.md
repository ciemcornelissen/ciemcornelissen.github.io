# Blog Post Integration Summary

## What Was Done

Your blog post "In-Field Grape Quality Mapping with Illumination-Invariant AI" has been successfully integrated into your website.

## Files Created and Modified

### 1. Blog Post

**Location:** `_posts/2025-10-20-hsi-grapes.md`

- Converted from MDX to Jekyll-compatible Markdown
- Properly formatted with YAML front matter
- Configured with tags, categories, and sidebar table of contents
- Enabled comments (Giscus) and related posts

### 2. Blog Images

**Location:** `assets/img/blog/2025-10-20-hsi-grapes/`
All images from your original blog folder have been copied here:

- `AE.png` - LISA architecture diagram
- `dataSetICCV.png` - Three lighting conditions comparison
- `spectralsignatures.png` - Spectral signature graph
- `IoTsystemArcitecture.png` - Robotic platform
- `exampleScan.png` - System output example
- `robot.png` - Additional robot image
- Plus all PDF versions

### 3. Configuration Update

**File:** `_config.yml`

- Added `relevantInformation/` to the `exclude` list
- This ensures Jekyll ignores the original MDX file and source folder

## Important Notes

### For GitHub Deployment

Since you won't be uploading the `relevantInformation` folder to GitHub:

✅ **Already Done:**

- All necessary images copied to `assets/img/blog/2025-10-20-hsi-grapes/`
- Blog post created in `_posts/2025-10-20-hsi-grapes.md`
- Configuration updated to exclude source folder

📝 **What to Commit to GitHub:**

```bash
git add _posts/2025-10-20-hsi-grapes.md
git add assets/img/blog/2025-10-20-hsi-grapes/
git add _config.yml
git commit -m "Add grape quality mapping blog post"
git push
```

⚠️ **Do NOT commit:**

- `relevantInformation/` folder (already excluded in .gitignore if needed)

## Viewing Your Blog Post

The blog post is now live at:

- Local: http://localhost:8080/al-folio_test/blog/2025/hsi-grapes/
- Blog listing: http://localhost:8080/al-folio_test/blog/

## Features Included

- ✅ Professional formatting with Jekyll Liquid tags
- ✅ Responsive image handling with zoom capability
- ✅ Proper captions for all figures
- ✅ Table of contents in sidebar
- ✅ Related posts suggestions
- ✅ Tags and categories for organization
- ✅ Comment section (Giscus)
- ✅ Links to paper and arXiv preprint

## Adding Future Blog Posts

To add more blog posts, simply:

1. Place your source content in `relevantInformation/[blog-name]/`
2. Copy images to `assets/img/blog/[blog-name]/`
3. Create a new markdown file in `_posts/YYYY-MM-DD-blog-name.md`
4. Follow the same format as `2025-10-20-hsi-grapes.md`

The `relevantInformation` folder will always be excluded from Jekyll processing and GitHub commits.
