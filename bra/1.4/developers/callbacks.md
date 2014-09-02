# Callbacks

## Components

The following callbacks are
[supported for components](http://book.cakephp.org/2.0/en/controllers/components.html#callbacks)
by CakePHP.

* **initialize**: Called before Controller::beforeFilter()
* **startup**: Called after the Controller::beforeFilter() and before the 
  controller action
* **beforeRender**: Called after the Controller::beforeRender(), after the view
  class is loaded, and before the Controller::render()
* **shutdown**: Called after Controller::render() and before the output is
  printed to the browser.

#### Code

    <?php
    class ExampleComponent extends Component {

        //called before Controller::beforeFilter()
        public function initialize(&$Controller, $settings = array()) {
            // saving the controller reference for later use
            $this->Controller =& $Controller;
        }

        //called after Controller::beforeFilter()
        public function startup(&$Controller) {
        }

        //called after Controller::beforeRender()
        public function beforeRender(&$Controller) {
        }

        //called after Controller::render()
        public function shutdown(&$Controller) {
        }

        //called before Controller::redirect()
        public function beforeRedirect(&$Controller, $url, $status = null, $exit = true) {
        }

        public function redirectSomewhere($value) {
            // utilizing a controller method
            $this->controller->redirect($value);
        }

    }

Learn more about components from
[http://book.cakephp.org/2.0/en/controllers/components.html](http://book.cakephp.org/2.0/en/controllers/components.html).

## Helpers

The following callbacks are
[supported for helpers](http://book.cakephp.org/2.0/en/views/helpers.html#callbacks)
by CakePHP:

* **beforeRender**: Called before the view file is rendered.
* **afterRender**: Called after the view file is rendered but before the layout
  has been rendered.
* **beforeLayout**: Called before the layout is rendered.
* **afterLayout**: Called after the layout has rendered.

#### Extra callbacks by Croogo for better integration

* **afterSetNode**: Called after LayoutHelper::setNode(). A good place to
  modify node content.
* **beforeNodeInfo**: Called before LayoutHelper::nodeInfo().
* **afterNodeInfo**: Called after LayoutHelper::nodeInfo().
* **beforeNodeBody**: Called before LayoutHelper::nodeBody().
* **afterNodeBody**: Called after LayoutHelper::nodeBody().
* **beforeNodeMoreInfo**: Called before LayoutHelper::nodeMoreInfo().
* **afterNodeMoreInfo**: Called after LayoutHelper::nodeMoreInfo()

#### Code

    <?php
    class ExampleHelper extends AppHelper {

        public $helpers = array(
            'Html',
            'Layout',
        );

        public function beforeRender() {
        }

        public function afterRender() {
        }

        public function beforeLayout() {
        }

        public function afterLayout() {
        }

        public function afterSetNode() {
            // field values can be changed from hooks
            $currentTitle = $this->Layout->node('title');
            $modifiedTitle = $currentTitle . ' [Modified by ExampleHelper]';
            $this->Layout->setNodeField('title', $modifiedTitle);
        }

        public function beforeNodeInfo() {
            return '<p>beforeNodeInfo</p>';
        }

        public function afterNodeInfo() {
            return '<p>afterNodeInfo</p>';
        }

        public function beforeNodeBody() {
            return '<p>beforeNodeBody</p>';
        }

        public function afterNodeBody() {
            return '<p>afterNodeBody</p>';
        }

        public function beforeNodeMoreInfo() {
            return '<p>beforeNodeMoreInfo</p>';
        }

        public function afterNodeMoreInfo() {
            return '<p>afterNodeMoreInfo</p>';
        }

    }

Learn more about helpers from
[http://book.cakephp.org/2.0/en/views/helpers.html](http://book.cakephp.org/2.0/en/views/helpers.html).