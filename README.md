# UMG-Tour-Dates
Tour Dates custom module for UMG.

# Installation

1. Install Drupal
2. Clone this repo in docroot/modules/custom
3. Per Drupal guidelines for [managing dependencies for custom projects](https://www.drupal.org/docs/develop/using-composer/managing-dependencies-for-a-custom-project) add the following lines in docroot composer.json
```"extra": {
  "merge-plugin": {
    "require": [
      "modules/custom/umg_tour_dates/composer.json"
    ]
  }
}
```
4. Run `composer update` at docroot
5. Install umg_tour_dates module

# How to use it

1. Create a Tour Date node (or a few)
  * Title - this is just for administrative purposes
  * Date - make sure to select a date in the future, otherwise the Tour Date will not show up in the view
  * Venue - since there are a finite number of venues I thought it made sense to make this an entityreference field so editors have the option to reuse existing venue information.  I used inline_entity_form to allow the editor to either create a new Venue without leaving the current form OR reference a Venue that has already been created.
    * Name - enter a Venue name (this is just a relabelled title field for Venue content type)
    * Location (city/state/country) - enter location information for this Venue (fields provided by Address module)
  * Ticket Link - enter a link to an external ticketing page
2. Check out the Tour Dates view at /tour-dates
  * It should sort by the date field in Tour Dates (newest descending) and does not show Tour Dates with dates in the past
  * The Tour Dates in this vew are displayed using the 'Tour Date' view mode 

# Some final thoughts

Since this task had no design requirements I did not create any tpls, make modifications to the default view mode or do any theming outside of Display Suite UI.  I sort of used [Lil Yachty's tour page](https://www.lilyachty.com/pages/tour) as a rough template for the layout.  If you would like to define acceptance criteria for how this view should look please let me know and I would be happy to update.  The umg_tour_dates module is dependant upon 3 contrib modules (address, ds, inline_entity_form) all of which are handled by the composer.json file in the module directory.  If you have any questions about my implementation feel free to reach out as I would be happy to provide clarification.  Finally - THANK YOU for this opportunity!!  I learned a lot about composer from this exercise and will most definitely be applying that to future projects!