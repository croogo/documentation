# Helpers

Read the CakePHP docs on Helpers:
[http://book.cakephp.org/2.0/en/views/helpers.html](http://book.cakephp.org/2.0/en/views/helpers.html).

## What is a Helper?

Helpers are the component-like classes for the presentation layer of your
application. They contain presentational logic that is shared between many
views, elements, or layouts. This chapter will show you how to create your own
helpers, and outline the basic tasks CakePHP's core helpers can help you
accomplish.

## Code

Let's say we named our helper Example, and it would be found at
`/app/View/Helper/ExampleHelper.php`.

    <?php
    class ExampleHelper extends AppHelper {

        public function lowercase($text) {
            return strtolower($text);
        }

    }

#### Plugin helpers

If it is Example plugin's helper, it would be found at
`/app/Plugin/Example/View/Helper/ExampleHelper.php`.

#### Using Helpers in Views

Before using helpers in views, we need to let our Controller know to get it
loaded.

    <?php
    class RecipesController extends AppController {

        public $uses = array(
            'Recipe',
        );

        public $helpers = array(
            'Example', // 'Example.Example' if it is from Example plugin
        );

        public function view($id) {
            $recipe = $this->Recipe->findById($id);
            $this->set('recipe', $recipe);
        }

    }

Now we can use the helper from our view at `/app/View/Recipes/view.ctp`:

    <div class="recipes view">
        <h2><?php echo $recipe['Recipe']['title']; ?></h2>

        <p><?php echo $recipe['Recipe']['body']; ?></p>

        <p><?php echo $this->Example->lowercase('TEXT WILL BE CONVERTED TO LOWERCASE'); ?></p>
    </div>
