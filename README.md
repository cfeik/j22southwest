# J/22 Southwest District Website

Official website for the J/22 Southwest District sailboat racing community.

🌐 **Live Site:** [https://j22southwest.org](https://j22southwest.org)

## About

This is a static website hosting regatta results, media, and information for the J/22 Southwest District.

## Structure

```
website/
├── index.html       # Home page
├── results.html     # Regatta results
├── media.html       # Media and links
├── css/
│   └── style.css    # Site styles
└── images/          # Site images
```

## Deployment

The site is automatically deployed to AWS S3 + CloudFront when changes are merged to the `main` branch.

### Infrastructure
- **Hosting:** AWS S3 (`j22southwest.org` bucket)
- **CDN:** CloudFront (distribution `E9651Z369JQUC`)
- **Domain:** j22southwest.org / www.j22southwest.org
- **SSL:** AWS Certificate Manager
- **CI/CD:** GitHub Actions

### Automatic Deployment

Every push to `main` triggers a GitHub Action that:
1. Syncs website files to S3 with proper content types
2. Sets appropriate cache headers
3. Invalidates CloudFront cache for immediate updates

### Manual Deployment

If needed, you can manually deploy using the AWS CLI:

```bash
# Deploy HTML files
aws s3 cp website/ s3://j22southwest.org/ \
  --recursive \
  --exclude "*" \
  --include "*.html" \
  --content-type "text/html" \
  --cache-control "max-age=300"

# Deploy CSS files
aws s3 sync website/css/ s3://j22southwest.org/css/ \
  --content-type "text/css" \
  --cache-control "max-age=86400"

# Deploy images
aws s3 sync website/images/ s3://j22southwest.org/images/ \
  --cache-control "max-age=86400"

# Invalidate CloudFront cache
aws cloudfront create-invalidation \
  --distribution-id E9651Z369JQUC \
  --paths "/*"
```

## Making Changes

1. Edit files in the `website/` directory
2. Test locally by opening HTML files in a browser
3. Commit and push to `main`
4. GitHub Actions will automatically deploy
5. Changes appear on the live site within 1-2 minutes

## Local Testing

```bash
cd website
python3 -m http.server 8000
# Open http://localhost:8000 in browser
```

## GitHub Secrets

The following secrets must be configured in the repository settings for automatic deployment:

- `AWS_ACCESS_KEY_ID` - AWS access key with S3 and CloudFront permissions
- `AWS_SECRET_ACCESS_KEY` - AWS secret access key

## Contact Information

- **District Governor:** Colin Feik (colin.feik@gmail.com)
- **District Treasurer:** Kevin Orff (Kevin.Orff@gmail.com)

## License

© J/22 Southwest District
