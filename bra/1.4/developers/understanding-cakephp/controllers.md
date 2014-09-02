# Controllers

Read the CakePHP docs on Controllers:
[http://book.cakephp.org/2.0/en/controllers.html](http://book.cakephp.org/2.0/en/controllers.html).

## What is a Controller?

A controller is used to manage the logic for a part of your application. Most
commonly, controllers are used to manage the logic for a single model. For
example, if you were building a site for an online bakery, you might have a
RecipesController and a IngredientsController managing your recipes and their
ingredients. In CakePHP, controllers are named after the model they handle, in
plural form.

The Recipe model is handled by the RecipesController, the Product model is
handled by the ProductsController, and so on.

Your application's controllers are classes that extend the CakePHP AppController
class, which in turn extends a core Controller class, which are part of the
CakePHP library. The AppController class can be defined in
`/app/Controller/AppController.php` and it should contain methods that are
shared between all of your application’s controllers.

Controllers can include any number of methods which are usually referred to as
actions. Actions are controller methods used to display views. An action is a
single method of a controller.

CakePHP's dispatcher calls actions when an incoming request matches a URL to a
controller’s action (refer to "Routes Configuration" for an explanation on how
controller actions and parameters are mapped from the URL).

## Code

Returning to our online bakery example, our RecipesController might contain the
view(), share(), and search() actions. The controller would be found in
`/app/Controller/RecipesController.php`.

    <?php
    class RecipesController extends AppController {

        public function view($id)     {
            //action logic goes here..
        }

        public function share($customer_id, $recipe_id) {
            //action logic goes here..
        }

        public function search($query) {
            //action logic goes here..
        }

    }

#### Plugin Controllers

If it is Recipes plugin's controller, it would be found at
`/app/Plugin/Recipe/Controller/RecipesController.php`.

## How to see it in action?

Controllers can be accessed from your browser from the address
**yoursite.com/controller\_name/action\_name**. But it will show errors now,
and we will require to create models and views for it too.