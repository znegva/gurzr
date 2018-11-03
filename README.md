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

__Note:__ this is only working if the `css` is provided with the correct Content-Type,
a [Pull Request to the Bolt CMS repo](https://github.com/bolt/bolt/pull/6964) was created, please check if it was accepted
or add the necessary change to your installation of Bolt if you want to use this feature.

A typical `custom.css` (to change the color for links) can be:
```css
a{
    color: red;
}
```

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
