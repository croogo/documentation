# File structure

A plugin is identified by it’s unique alias. If you have your plugin under the directory app/Plugin/Example, then your plugin’s alias is **Example**.

## Structure

* app/Plugin/Example/
   * Config/
      * bootstrap.php
      * plugin.json
      * routes.php
      * ExampleActivation.php
   * Controller/
      * Component/
         * ExampleComponent.php
      * ExampleController.php
      * ExampleAppController.php
   * Model/
      * Behavior/
      * ExampleAppModel.php
   * View/
      * Elements/
      * Example/
      * Helper/
         * ExampleHelper.php
    * webroot/
      * css/
      * img/
      * js/

Do not forget the [plugin.json](json-file) file. This is required, otherwise the plugin will not be available in admin panel for activation.

A full working plugin is available in the [repository](http://github.com/croogo/croogo/tree/1.4/Plugin/Example).