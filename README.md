BanklessDAO DevOps Documentation Demo
=====================================
This is the repository containing a demo of a deployment mechanism for a BanklessDAO documentation site for DevOps.

The Hosting Environment
------------
The static site is stored in an S3 bucket on AWS. It is then served via CloudFront over a domain using Route 53 and ACM for SSL.

The Deployment Process
----------------------
The process works like this:

2. Create a feature branch
2. Make changes, create posts, etc...
  1. Test the changes locally with "bundle exec jekyll serve" and http://localhost:4000
3. Open a PR to merge your changes to the `develop` branch
4. When the changes are merged GitHub Actions performs the workflow below on `https://draft-devops.bankless.community`
5. Open a PR to merge your changes to the `main` branch once the changes are ready to go live
6. When the changes are merged GitHub Actions performs the workflow below on `https://devops.bankless.community`

GitHub Actions Workflow:

1. AUTOMATED: GitHub Actions gets notified and clones the repo.
    1. AUTOMATED: GitHub Actions injects the draft/production _config.xml from BuildAdditions into SourceCode
    2. AUTOMATED: GitHub Actions then builds the site with "bundle exec jekyll build"
    3. AUTOMATED: GitHub Actions injects the robots.txt file from BuildAdditions into _site
    4. AUTOMATED: GitHub Actions uses its S3 credentials to sync the changes to the appropriate S3 bucket.
    5. AUTOMATED: GitHub Actions will invalidate the appropriate CloudFront cache using the CloudFront-Invalidate.json file found in BuildAdditions
2. The changes are now live and the containers in GitHub Actions are deleted.

Changing The _config.xml files
------------------------------
If you make any changes to `SourceCode/_config.xml` then the same changes need to be made to `BuildAdditions/prod_config.xml` and `BuildAdditions/draft_config.xml`
since those deploy to live sites for testing and production.

Known Issues
------------
1. Hot linking of images could cost money so if that becomes a problem then AWS WAF should be considered.
2. [This template](https://jekyllthemes.io/theme/desk-responsive-knowledge-base-and-faq-jekyll-theme) looks nicer IMHO
