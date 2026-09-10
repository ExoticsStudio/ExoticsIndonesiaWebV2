# Exotics SEO System v1

## Goals

Every public page should be:
- crawlable
- indexable when published
- uniquely titled
- uniquely described
- canonicalized
- shareable
- connected to its language alternate
- represented with appropriate structured data

## Bilingual SEO

English and Indonesian pages are distinct URLs:

- `/en/`
- `/id/`
- `/en/news/{slug}`
- `/id/news/{slug}`

Each language pair should expose reciprocal `hreflang` links.

## Content fields

Recommended Google Sheets fields:

```text
seo_title_en
seo_title_id
seo_description_en
seo_description_id
og_image
canonical_path_en
canonical_path_id
noindex
```

If SEO fields are empty, the sync/build layer can generate safe defaults from title/excerpt. Editorially supplied SEO metadata takes precedence.

## Indexing rules

- Only `status=published` content is indexable.
- Draft, candidate, rejected and unpublished content should be `noindex`.
- Every indexable URL gets one canonical URL.
- Avoid indexing duplicate query-string URLs.
- Paginated/archive pages should have deliberate canonical/indexing policy.

## Structured data

Use JSON-LD where applicable:

- `WebSite` for site
- `Organization` for publisher
- `Article` for news/article pages
- `BreadcrumbList` for hierarchy
- `VideoObject` for featured video pages
- `Review` for review pages

Do not emit structured data for content that is not actually visible on the page.

## Sitemap

The sync worker should generate `sitemap.xml` from published records, including both language versions where available.

## RSS

`feed.xml` should contain published news only.

## Performance SEO

- AVIF/WebP where supported
- responsive image sizes
- lazy-load below-the-fold imagery
- reserve image dimensions to reduce layout shift
- minimize render-blocking assets
- self-host fonts in production
- avoid unnecessary third-party scripts

## Important

The current package provides the SEO foundation and dynamic metadata engine. The final dynamic metadata/sitemap generation belongs in the Google Sheets sync/build worker once production content exists.
