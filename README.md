# Amsterdam Datablog

See https://amsterdam.github.io/datablog.

## Images

| Description                        | Dimensions  | Filename                        |
|------------------------------------|------------:|---------------------------------|
| Default image in post              | 800 × | _n.a._       |
| Wide banner image                  | 2800 × 595  | `{{ post.ref }}-wide.jpg`       |
| Thumbnail for post list            |  600 × 336  | `{{ post.ref }}-thumbnail.jpg`  |
| [Open Graph image](http://ogp.me/) | 1200 × 630  | `{{ post.ref }}-open-graph.jpg` |

## Running locally

The data blog is made using [Jekyll](https://jekyllrb.com/), a static site generator written in Ruby.  To install Jekyll, you can follow the [Jekyll Installation](https://jekyllrb.com/docs/installation/macos/)

To run, test and author this blog locally, first clone the source code from GitHub:

    git clone https://github.com/Amsterdam/datablog.git

Install the missing gems:

    cd datablog
    bundle install

Then, run Jekyll:

    bundle exec jekyll serve --baseurl "" --livereload --incremental

The blog should now be available on http://localhost:4000/.

## Adding posts

Jekyll supports working with post drafts, you can put them in the [`_drafts` directory](_drafts). For more information about posts and drafts, see [Jekyll's documentation](https://jekyllrb.com/docs/posts/#drafts).

Adding a new posts:

1. First, make sure your name is added to the authors file: [`_data/authors.yml`](_data/authors.yml);
2. Then, create a new Markdown file in [`_drafts`](_drafts);
3. Start typing! You can use the HTML components from the [`_includes`](_includes) directory to easily add, for example, images, figures and iframes. See the [existing posts](_posts) for examples.

Start Jekyll with the `--drafts` option to include the drafts:

    bundle exec jekyll serve --baseurl "" --livereload --incremental --drafts

By default, images are loaded from https://amsterdam.github.io/data-blog-assets/ (see [`_config.yml`](_config.yml)).

If you want to add and test images and other assets more easily while writing new posts, it is easier to host these assets locally:

1. First, clone the assets repository: `git clone https://amsterdam.github.io/data-blog-assets.git`;
2. Start a web server in this directory ([http-server](https://github.com/indexzero/http-server), for example);
3. Create a development configuration file `_config.dev.yml` and specify your local assets server:

```yml
baseurl:
assets: http://data-blog-assets.test
production: false
```

Start Jekyll and use the `--config` option to include the development configuration file as well as the default one:

    bundle exec jekyll serve -P $PORT --baseurl "" --config "_config.yml,_config.dev.yml" --livereload --livereload_port 52287 --incremental --drafts

_You can use [Hotel](https://github.com/typicode/hotel) to configure local `.localhost` or `.test` domains for easy testing of local web servers!_

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
- [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images#How_do_you_create_responsive_images)

## Ideas

- Lightbox for images
- Scripts to generate different image sizes (or use our IIIF server?)
- Anchor links for headings
- Button to copy code examples to clipboard
- Button to open data in geojson.io
- `%include` for Leaflet maps
