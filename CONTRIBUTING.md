# Contributing to Profile Explorer

Thank you for contributing to the ProfileScraper community!

## How to Contribute

### Option 1: Via ProfileScraper App (Recommended)

The easiest way to contribute is through the ProfileScraper desktop app:

1. Create and thoroughly test your profile
2. Click the **"Publish to Profile Explorer"** button
3. Login with your GitHub account
4. Fill in the description and tags
5. Click **"Create Pull Request"**

The app will automatically:
- Fork this repository
- Create a branch with your changes
- Open a pull request
- Auto-populate author and timestamp fields

### Option 2: Manual Submission

If you prefer to submit manually:

1. Fork this repository
2. Create a new branch: `git checkout -b add-profile-your-site-name`
3. Edit `public-profiles.json` and add your profile to the `profiles` array
4. Update the `updated_at` timestamp to current Unix time (milliseconds)
5. Commit your changes
6. Push to your fork
7. Open a pull request

## Profile Structure

```json
{
  "id": "unique-uuid-here",
  "name": "Site Name - Category",
  "description": "What this profile scrapes",
  "author": "Your GitHub username",
  "tags": ["e-commerce", "electronics"],
  "categoryUrl": "https://example.com/category",
  "productLinkSelector": "a.product-link",
  "fieldSelectors": {
    "title": "h1.title",
    "price": ".price",
    "image": {
      "selector": "img.main",
      "attribute": "src"
    }
  },
  "pagination": {
    "type": "button",
    "selector": ".next-page",
    "maxPages": 10
  },
  "preActions": [],
  "productPageActions": [],
  "concurrency": 3,
  "delayRange": [2000, 4000],
  "retries": 3,
  "checkpointInterval": 10,
  "headless": true,
  "overwriteExisting": false,
  "isPublic": true,
  "isReadonly": true,
  "version": "1.0.0",
  "created_at": 1699564800000,
  "updated_at": 1699564800000
}
```

## Submission Guidelines

### Required Fields
- ✅ `id` - UUID v4 format
- ✅ `name` - Clear, descriptive name
- ✅ `description` - What the profile scrapes
- ✅ `author` - Your GitHub username
- ✅ `tags` - At least one tag
- ✅ `isPublic: true` - Mark as public
- ✅ `isReadonly: true` - Prevent editing in app

### Best Practices
- ✅ Test thoroughly before submitting
- ✅ Use respectful scraping settings (delays, low concurrency)
- ✅ Include clear field selectors
- ✅ Add helpful description
- ✅ Use appropriate tags
- ✅ No hardcoded credentials or tokens
- ✅ Respect website ToS

### Tags
Use consistent tags:
- `e-commerce` - Online stores
- `real-estate` - Property listings
- `electronics` - Tech products
- `fashion` - Clothing/accessories
- `books` - Book listings
- `marketplace` - Multi-vendor platforms
- `auction` - Auction sites
- `job-board` - Job listings

## Review Process

Submitted profiles are reviewed for:

1. **Correctness** - Does the profile work?
2. **Safety** - No malicious code or credentials
3. **Quality** - Clear selectors and configuration
4. **Compliance** - Respectful scraping practices
5. **Completeness** - All required fields present

Reviews typically take 1-3 days.

## Questions?

- [Open an issue](https://github.com/ProfileScraper/profile-explorer/issues)
- [Join discussions](https://github.com/ProfileScraper/configurable-scraper/discussions)

Thank you for making ProfileScraper better! 🎉
