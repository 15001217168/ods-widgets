# Change Log
All notable changes to this project will be documented in this file.
This log tries to follow the good principles of [Keep a CHANGELOG](http://keepachangelog.com/).

## 0.1.4 - 2015-01-28
### Added
- New `odsPaginationBlock` widget, especially used in `odsResultEnumerator` where you can use a new `showPagination` attribute
to display a pagination control below your results.
- `odsFacets` now support the configuration of a specific order for facet values. It can be used for example to ensure
 "Monday", "Tuesday", "Wednesday", "Thursday"... are displayed in the right order. 
 See documentation of the `sort` parameter for more information.
- In `odsMap` default tooltips, if a field contains a link to a YouTube video, a mini video player is displayed.
- Clicking on a reuse's source will now open in a new tab by default.
- When `odsTextSearch` initialized, it now takes the `q=` parameter of its context as a default value.

### Fixed
- The `imagify` filter no longer cuts URL parameters from detected image links; this means you'll no longer see this problem
in `odsMap` tooltips for example.
- Linebreaks between start and end of the `odsTable` tag no longer triggers an empty custom template for cells.
- Clicking on a reuse (from `odsReuses` or `odsLastReusesFeed`) will bring you to the dataset's information tab where all
the reuses are listed, instead of a default visualization.
- `odsSearchBox` now works in every case; previously, depending on how it was initialized, it may have been not working when submitting a search.

## 0.1.3 - 2014-12-04
### Added
- New widget: `odsToggleModel`. It can be used on a checkbox, to add/remove a parameter depending on the state of the checkbox.
- It is now possible to customize the template of reuses in the `odsLastReusesFeed` widget. See the widget's documentation for more information.
- `odsLastReusesFeed` now has a `max` parameter to set a maximum number of reuses to display.
- `odsMap` custom tooltips have been simplified and do not require including some code for scrolling between multiple records anymore. Documentation is coming soon!
- `odsResults` widget, when used with an `odsCatalogContext`, now retrieves every metadata, including DCAT and others, so that you can use them in results display.
- Facet values are now also displayed as a tooltip on mouse hover (title), making it possible to read long values that have been truncated.

### Fixed
- The sort icons on the `odsTable` widget now show the proper direction, and sorting on an alphanumeric field now sorts
in the right direction the first time.
- `odsMap` now handles massive amounts of data much faster than before.

## 0.1.2 - 2014-10-15
### Added
- New widget: `odsFacets`. This widget allows you to insert and finely configure filters for your data, including customizing the way each available
value is displayed. You can find more information in the documentation.
- New widget: `odsReuses`. This widget displays an infinite list of reuses for a domain, displayed in large boxes.
- The user's timezones is now taken into account in filters and facets.

### Fixed
- Internet Explorer 8 and 9 can now interact with non-local APIs: the widgets now use JSONP to circumvent these browsers'
limitations with cross-domain requests.

## 0.1.1 - 2014-09-17
### Added
- We now have a changelog!
- New widget: `odsTimerange`. This widget displays a calendar to select a range
of date or datetime to refine on.
- New widget: `odsResults`. This widget exposes the result of a search query as a variable in your scope. It can be
easily combined with AngularJS's ngRepeat to display a custom list of results.
- `odsGeotooltip` can now be directly passed a record to display its geographical
information, instead of having to explicitely pass the field name.
- `odsMap` now supports a new mechanism to refine another context when the user
clicks on a marker or shape. See the `itemClickContext` in the documentation.
- `odsResultEnumerator` now support a `showHitsCounter` parameter to display
a simple counter of the number of hits.
- If there is no data to display, the `odsHighcharts` widget now displays an
explicit message instead of an empty space.
- The HTTP requests sent to APIs now include an `ODS-Widgets-Version` header to indicate
the version of the ODS-Widgets library.
- To improve support for Internet Explorer 8, you can now load a `ieshiv.js` file (or its minified version also included)
before AngularJS is loaded in your page.

### Removed
- `odsTable` no longer has a `tableContext` parameter; instead, the active sort is
now directly shared in the context itself, like the other parameters.

### Fixed
- On Internet Explorer 8, Vector markers (typically containing a pictogram) were sometimes subject to
bad positioning and appeared far from their original location.


## 0.1.0 - 2014-08-22
*Initial release of the project*