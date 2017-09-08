# Bootstrap

Plugins can have their own bootstrap. If you have a plugin named **example**, you will have a file at app/plugins/example/config/example_bootstrap.php This file is required for all plugins and will be loaded (when active) every time the application bootstraps.

This is useful for storing basic configuration info like:

    Configure::write('PluginName.my_setting_key', 'value here');

Then it can be accessed anywhere in the application by:

    $myVar = Configure::read('PluginName.my_setting_key');