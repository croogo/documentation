# Components

Read the CakePHP docs on Components:
[http://book.cakephp.org/2.0/en/controllers/components.html](http://book.cakephp.org/2.0/en/controllers/components.html).

## What is a Component?

Components are packages of logic that are shared between controllers. If you
find yourself wanting to copy and paste things between controllers, you might
consider wrapping some functionality in a component.

## Code

Assuming you want to create an Example component, it would be found at
`/app/Controller/Component/ExampleComponent.php`.

    <?php
    class ExampleComponent extends Component {

        public function myMethod() {
            // your code here
        }

    }

#### Plugin components

If it Example plugin's component, it would be found at
`/app/Plugin/Example/Controller/Component/ExampleComponent.php`.

#### Using Components in Controllers

    <?php
    class RecipesController extends AppController {

        public $components = array(
            'Example', // 'Example.Example' if it is from Example plugin
        );

        public function view($id)     {
            // call component method
            $this->Example->myMethod();
        }

    }