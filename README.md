# Amsterdam Datablog

Work in progress. First blog post will be published in a few weeks.

## Images

| Description                        | Dimensions  | Filename                        |
|------------------------------------|------------:|---------------------------------|
| Default image in post              | 800 × | _n.a._       |
| Wide banner image                  | 2800 × 595  | `{{ post.ref }}-wide.jpg`       |
| Thumbnail for post list            |  600 × 336  | `{{ post.ref }}-thumbnail.jpg`  |
| [Open Graph image](http://ogp.me/) | 1200 × 630  | `{{ post.ref }}-open-graph.jpg` |

## Style

- https://patternlab-amsterdam.infoprojects.nl/
- https://www.amsterdam.nl/stijlweb/ruimtelijke-middelen/wagenpark/
- https://dokuwiki.datapunt.amsterdam.nl/doku.php?id=start:datapunt:huisstijl

## Internationalization

Based on https://www.sylvaindurand.org/making-jekyll-multilingual/.

# TODO

- Improve [footer links](_includes/footer.liquid)
- Include modified [Tachyons](https://github.com/tachyons-css/tachyons/)
- Test [Open Graph tags](http://ogp.me/)
- Improve [`fonts.scss`](assets/css/fonts.scss)
- Improve code syntax highlighting
- Leaflet iframe should ignore mouse wheel events!

## Ideas

- Lightbox for images
- More/better/responsive image sizes
- Button to copy code examples to clipboard
- Button to open data in geojson.io
- `%include` for Leaflet maps
