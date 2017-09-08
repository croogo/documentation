# Models

Read the CakePHP docs on Models:
[http://book.cakephp.org/2.0/en/models.html](http://book.cakephp.org/2.0/en/models.html).

## What is a Model?

Models represent data and are used in CakePHP applications for data access. A
model usually represents a database table but can be used to access anything
that stores data such as files, LDAP records, iCal events, or rows in a CSV
file.

A model can be associated with other models. For example, a Recipe may be
associated with the Author of the recipe as well as the Ingredient in the
recipe.

## Code

If you have a table named 'recipes' (with columns id, title, body), the model
name would be **Recipe** and found at `/app/Model/Recipe.php`.

    <?php
    class Recipe extends AppModel {

    }

#### Plugin Models

If it is Recipes plugin's model, it would be found at
`/app/Plugin/Recipes/Model/Recipe.php`.

#### Using Models in Controllers

    <?php
    class RecipesController extends AppController {

        public $uses = array(
            'Recipe', // 'Recipes.Recipe' if it is from Recipes plugin
        );

        public function view($id) {
            // retrieve record with ID 123 from recipes table
            $recipe = $this->Recipe->findById(123);

            // set the $recipe variable so it can be used by views later
            $this->set('recipe', $recipe); // or $this->set(compact('recipe'));
        }

    }
