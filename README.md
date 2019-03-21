# Amsterdam Datablog

See https://amsterdam.github.io/datablog.

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
- Add [contact form](https://medium.com/datafire-io/simple-backends-four-ways-to-implement-a-contact-us-form-on-a-static-website-10fc430984a4)
- Include modified [Tachyons](https://github.com/tachyons-css/tachyons/)
- Test [Open Graph tags](http://ogp.me/)
- Improve [`fonts.scss`](assets/css/fonts.scss)
- Improve code syntax highlighting
- Leaflet iframe should ignore mouse wheel events!
- [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images#How_do_you_create_responsive_images)


## Ideas

- Lightbox for images
- Scripts to generate different image sizes (or use our IIIF server?)
- Anchor links for headings
- Button to copy code examples to clipboard
- Button to open data in geojson.io
- `%include` for Leaflet maps
