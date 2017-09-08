# File structure

A plugin is identified by it’s unique alias. If you have your plugin under the directory app/plugins/example, then your plugin’s alias is **example**.

## Structure

* app/plugins/example/
   * config/
      * example\_activation.php
      * example\_bootstrap.php
      * example\_routes.php
      * plugin.yml
   * controllers/
      * components/
         * example.php
      * example\_controller.php
   * models/
      * behaviors/
   * views/
      * elements/
      * example/
      * helpers/
         * example.php
    * webroot/
      * css/
      * img/
      * js/
   * example\_app\_controller.php
   * example\_app\_model.php

Do not forget the plugin.yml file. This is required, otherwise the plugin will not be available in admin panel for activation.

A full working plugin is available in the [repository](http://github.com/croogo/croogo/tree/master/plugins/example).