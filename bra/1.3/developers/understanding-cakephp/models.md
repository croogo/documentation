# Models

Fonte original: [http://book.cakephp.org/view/1000/Models](http://book.cakephp.org/view/1000/Models).

## O que é um Model?

Models representam dados e são usados em aplicações CakePHP para acessar dados. Um model geralmente representa uma tabela do bando de dados, mas pode ser usado para acessar qualquer coisa que armazene dados como arquivos, registros LDPA, eventos iCal, ou linhas de arquivos CSVs.

Um model pode ser associado com outros models. Por exemplo, um model Recipe pode ser associado com o Autor de receitas tanto quanto o Igredient da receita.

## Código

Se você tem uma tabela chamada 'recipes' (com colunas id, title, body), o nome do model seria **Recipe** e encontrado em /app/Model/Recipe.php

    <?php
    class Recipe extends AppModel {
    
        public $name = 'Recipe';

    }
    ?>

#### Models de Plugin

Se fosse model do plugin Recipes, seria encontrado em /app/Plugin/Recipes/Model/Recipe.php

#### Usando Models em Controllers

    <?php
    class RecipesController extends AppController {
    
        public $uses = array(
            'Recipe', // 'Recipes.Recipe' se for de um plugin Recipes
        );
    
        public function view($id)     {
            // recuperar registro com ID 123 da tabela recipes
            $recipe = $this->Recipe->findById(123);
    
            // seta a variável $recipe então pode ser usada pela view depois
            $this->set('recipe', $recipe); // ou $this->set(compact('recipe'));
        }

    }
    ?>