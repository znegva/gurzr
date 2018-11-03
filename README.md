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
