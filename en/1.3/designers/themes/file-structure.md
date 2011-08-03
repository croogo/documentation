# File structure

A theme is identified by it's unique alias. If you have your theme under the directory app/views/themed/my\_theme, then your theme’s alias is **my\_theme**.

A theme.yml file is also required. You can see the YAML file used for default theme here: [theme.yml](http://github.com/croogo/croogo/blob/master/webroot/theme.yml).

## Structure

For example, you have a theme with alias my_theme. All your files should be placed like this:

* app/views/themed/my_theme/
   * elements/
   * helpers/
      * custom.php
   * layouts/
      * default.ctp
   * nodes/
      * view.ctp
   * …
   * webroot/
      * css/
         * theme.css
      * js/
         * theme.js
      * img/
         * screenshot.png
      * theme.yml

Do not forget the theme.yml file. Your theme will not be available in the admin panel otherwise.