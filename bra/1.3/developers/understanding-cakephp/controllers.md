# Controllers

Fonte original: [http://book.cakephp.org/view/955/Controllers](http://book.cakephp.org/view/955/Controllers).

## O que é um Controller?

Um controller é usado para gerenciar a lógica para uma parte da sua aplicação. Mais comumente, controllers são usados para gerenciar a lógica de um único model. Por exemplo, se você estiver construindo um site para uma padaria, você pode ter um RecipesController e um IngredientsController para gerenciar suas receitas e seus ingredientes. No CakePHP, controllers são nomeados após o manuseio do model deles, na forma de plural.

O model Recipe é manuseado pelo RecipesController, o model Product é manuseado pelo ProductsController, e assim por diante.

Na sua aplicação os controllers são classes que extendem a classe AppController do CakePHP, que por sua vez entende a classe Controller do core, que é parte da biblioteca do CakePHP. A classe AppController pode ser definida em /app/AppController.php e ela deve conter métodos que serão compartilhados entre todos os controllers da sua aplicação.

Os Controllers podem incluir qualquer número de métodos que geralmente se refere às actions. Actions são métodos do controller, usados para exibir as views. Uma action é um simples método do controller.

O dispatcher do CakePHP chama uma action quando a entrada de uma requisição de URL corresponder com uma action do controller (veja em "Configuração de Rotas" para uma explicação em como a action do controller e parâmetros são mapeados da URL).

## Código

Retornando ao nosso exemplo de padaria online, nosso RecipesController pode conter as actions view(), share(), e search(). O controller seria encontrado em /app/Controller/RecipesController.php

    <?php
    class RecipesController extends AppController {
        
        function view($id)     {
            //a lógica da action vem aqui..
        }
        
        function share($customer_id, $recipe_id) {
            //a lógica da action vem aqui..
        }
        
        function search($query) {
            //a lógica da action vem aqui..
        }
    
    }
    ?>

#### Plugin controllers

Se fosse o controller do plugin Recipes, seria encontrado em /app/Plugin/Recipes/Controller/RecipesController.php

## Como ver isso em ação?

Os controllers podem ser acessados pelo seu browser do endereço **youriste.com/controller\_name/action\_name**. Mas isso exibirá erros, e nos vai ser requerido a criar model e view para  isso também.