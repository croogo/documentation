# Controllers

Fonte original: [http://book.cakephp.org/view/955/Controllers](http://book.cakephp.org/view/955/Controllers).

## O que é um Controller?

Um controller é usado para gerenciar a lógica para uma parte da sua aplicação. Mais comumente, controllers são usados para gerenciar a lógica de um único model. Por exemplo, se você estiver construindo um site para uma padaria, você pode ter um RecipesController e um IngredientsController para gerenciar suas receitas e seus ingredientes. No CakePHP, controllers são nomeados após o manuseio do model deles, na forma de plural.

O model Recipe é manuseado pelo RecipesController, o model Product é manuseado pelo ProductsController, e assim por diante.

Na sua aplicação os controllers são classes que extendem a classe AppController do CakePHP, que por sua vez entende a classe Controller do core, que é parte da biblioteca do CakePHP. A classe AppController pode ser definida em /app/AppController.php e ela deve conter métodos que serão compartilhados entre todos os controllers da sua aplicação.

Os Controllers podem incluir qualquer número de métodos que geralmente se refere às actions. Actions são métodos do controller, usados para exibir as views. Uma action é um simples método do controller.


CakePHP’s dispatcher calls actions when an incoming request matches a URL to a controller’s action (refer to "Routes Configuration" for an explanation on how controller actions and parameters are mapped from the URL).

## Code

Returning to our online bakery example, our RecipesController might contain the view(), share(), and search() actions. The controller would be found in /app/controllers/recipes\_controller.php.

    <?php
    class RecipesController extends AppController {
        
        function view($id)     {
            //action logic goes here..
        }
        
        function share($customer_id, $recipe_id) {
            //action logic goes here..
        }
        
        function search($query) {
            //action logic goes here..
        }
    
    }
    ?>

#### Plugin controllers

If it is Recipes plugin's controller, it would be found at /app/plugins/recipes/controllers/recipes\_controller.php.

## How to see it in action?

Controllers can be accessed from your browser from the address **yoursite.com/controller\_name/action\_name**. But it will show errors now, and we will require to create models and views for it too.