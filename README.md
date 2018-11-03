# gurzr
single column theme for Bolt CMS

__this project is work-in-progress atm!__


### ToDo

- [x] archive template
- [x] latest posts template
- [x] login template + custom passwordform.twig
- [x] maintenance template
- [ ] default favicon?
- [ ] is custom.css working?
- [x] check `pre` content and highlight.js
- [ ] update this readme
- [ ] provide example contenttype-definition
- [ ] cleanup thumbnails in theme.yml (check `_gallery.twig` !)
- [ ] support fa-icons in menu
- [ ] check scss-includes, minify generated css



## Features

### Favicon

Just add a `favicon.png` with at least size of 180px*180px at the top level of
your files-folder and it will be used as _favicon_ as well as _apple-touch-icon_,
otherwise the themes [default favicon](images/favicon.png) will be used.

### Custom CSS

You can upload your own CSS-file to change some small things.
The file has to be named `custom.css` and be placed in the top level of your files-directory.

A typical `custom.css` (to change the color for links) can be:
```css
a{
    color: red;
}
```

### Galleries

gurzr supports galleries - to use them just add a field `gallery` with
`type: imagelist` to your ContentType.  
[PhotoSwipe](http://photoswipe.com/) is used as lightbox for the gallery images.

Captions can be shown optionally, to manage this behavior add a field
`show_gallery_captions` with `type: checkbox` to your ContentType.

### GPX tracks

If you regularly publish gpx tracks with your posts, you can add a field `gpx`
with `type: file` to your ContentType.
You also have to extend `accept_file_types` in `config.yml` to accept
`gpx`-files in order to be able to upload your tracks. If a nonempty field `gpx`
is found in your record a map is drawn right below the content (and above a gallery, if there is one).

The map is created using [leaflet](http://leafletjs.com/) and
[leaflet-gpx](https://github.com/mpetazzoni/leaflet-gpx) and uses maptiles from
the [Open Street Map Project](https://www.openstreetmap.org), some symbols from
[Font Awesome](http://fontawesome.io/) are used in the footer to indicate
distance, duration and elevations of your track.

### Code highlighting

Code blocks are highlighted using [highlight.js](https://highlightjs.org/), the
theme used for highlighting can be defined in your `config.yml` via the parameter
`highlight_theme` (use only lowercase, eg: `highlight_theme: dracula`), see the
[highlight.js demo page](https://highlightjs.org/static/demo/) for previews of
the different themes.


### Optional publishing of date and taxonomies

You can define for which ContentTypes the publishing date will be displayed
by adding `show_publishdate: true` to your ContentTypes values in
`config://contenttypes.yml`.
Typically you don't want to show the publishdate for pages.

Display of taxonomies can also be controlled via ContentType definition.
If you dont want taxonomy `tags` to be shown, just add
`hidden_taxonomies: [ tags ]` to your ContentType definition.
Hereby it is possible to use some taxonomies internally but not showing them to
your visitors.

Tags will be prefixed with a hash #, categories will be prefixed with an @.

The `publish_date` rule applies for listings and the records-page,
`hidden_taxonomies` is applied only to the record page, as we do not show
taxonomies in listings.
