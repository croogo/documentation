# Components

Original source: [http://book.cakephp.org/view/993/Components](http://book.cakephp.org/view/993/Components).

## What is a Component?

Components are packages of logic that are shared between controllers. If you find yourself wanting to copy and paste things between controllers, you might consider wrapping some functionality in a component.

## Code

Assuming you want to create an Example component, it would be found at /app/controllers/components/example.php.

    <?php
    class ExampleComponent extends Object {
    
        public function myMethod() {
            // your code here
        }
    
    }
    ?>

#### Plugin components

If it Example plugin's component, it would be found at /app/plugins/example/controllers/components/example.php.

#### Using Components in Controllers

    <?php
    class RecipesController extends AppController {

        public $components = array(
            'Example', // 'Example.Example' if it is from Example plugin
        );
    
        function view($id)     {
            // call component method
            $this->Example->myMethod();
        }
    
    }
    ?>