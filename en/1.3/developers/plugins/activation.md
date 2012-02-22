# Activation

Plugins may require to perform some tasks when they are activated or deactivated. This can be done using their own activation class. For example, you have a plugin named **example**, then you will have a file at app/plugins/example/config/example_activation.php:

    class ExampleActivation {
    /**
     * Plugin will be activated and continue with onActivation()
     * if this returns true
     *
     * @param  object $controller Controller
     * @return boolean
     */
        public function beforeActivation(&$controller) {
            return true;
        }
    /**
     * Called right after activating the plugin 
     *
     * @param object $controller Controller
     * @return void
     */
        public function onActivation(&$controller) {
            // your code here
        }
    /**
     * Plugin will be deacvitated and continue with onDeactivation()
     * if this returns true
     *
     * @param  object $controller Controller
     * @return boolean
     */
        public function beforeDeactivation(&$controller) {
            return true;
        }
    /**
     * Called right after deactivating the plugin 
     *
     * @param object $controller Controller
     * @return void
     */
        public function onDeactivation(&$controller) {
            // your code here
        }
    }

For a more detailed explanation, you can see [ExampleActivation](http://github.com/croogo/croogo/blob/master/plugins/example/config/example_activation.php) class from the repository.

**Note**: Activation class for plugins is optional and is required only when you need to perform tasks when the plugin is activated or deactivated.