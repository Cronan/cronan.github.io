# LinkedIn carousel PDF spec

## Dimensions

1080 x 1080px (square). Set via CSS `@page { size: 1080px 1080px; }`.

Square gets more feed real estate than landscape. LinkedIn also accepts 1080x1350 (portrait, 4:5) which is taller and can fit more text per slide.

## Page count

Each `<div class="slide">` with `page-break-after: always` becomes one PDF page. LinkedIn supports up to 300 pages; 8-12 is the practical sweet spot.

## Generation

HTML source in `drafts/linkedin-carousel.html`, converted to PDF with weasyprint:

```bash
pip install weasyprint
python3 -c "from weasyprint import HTML; HTML('drafts/linkedin-carousel.html').write_pdf('drafts/linkedin-carousel.pdf')"
```

## Fonts available on this system

- Headings: `Bitstream Charter` (matches site's Charter/Georgia stack)
- Body: `DejaVu Sans Mono` (matches site's SF Mono/Consolas stack)
- Also available: Liberation Serif, Liberation Mono, DejaVu Serif

## Colour palette (matches site dark mode)

| Token                       | Value     |
|-----------------------------|-----------|
| Background                  | `#111`    |
| Primary text                | `#e0e0e0` |
| Secondary/dim text          | `#999`    |
| Muted text (slide numbers)  | `#555`    |
| Accent (bar, stats, URLs)   | `#c44`    |
| Strong/bold text            | `#fff`    |
| Dividers/borders            | `#333`    |

## Layout per slide

- 100px padding on all sides (80px bottom)
- 6px red accent bar across the top (`::before` pseudo-element)
- Slide number bottom-right in monospace at 20px
- Content vertically centred via flexbox
- Divider element: 60px wide, 2px tall, `#333`

## Typography sizes

| Element              | Size    |
|----------------------|---------|
| h1 (title)           | 52px    |
| h2 (section head)    | 36px    |
| Body text            | 32px    |
| Dim/attribution text | 24-28px |
| Stat (big number)    | 72px    |
| Byline / slide num   | 20-22px |
| Tags                 | 18px    |

## Upload

Download the PDF, create a new LinkedIn post, click the document icon (not image), upload the PDF. LinkedIn converts each page to a swipeable slide.
