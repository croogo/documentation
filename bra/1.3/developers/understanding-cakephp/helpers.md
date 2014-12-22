# Helpers

Fonte original: [http://book.cakephp.org/view/1095/Helpers](http://book.cakephp.org/view/1095/Helpers).

## O que é um Helper?

Helpers são classes tipo component para a camada de apresentação da sua aplicação. Eles contém lógica de apresentação que é compartilhada entre várias views, elements, ou layouts. Este capítulo lhe mostrará como criar seus próprios helpers, e esboço dos helpers do core do CakePHP que podem ajudar você realizar as tarefas básicas.

## Código

Vamos dizer que nomeamos nosso Example helper, e ele seria encontrado em /app/View/Helper/ExampleHelper.php

    <?php
    class ExampleHelper extends AppHelper {
    
        public function lowercase($text) {
            return strtolower($text);
        }
    
    }
    ?>

#### Helper do Plugin

Se fosse helper do plugin Example, seria encontrado em /app/Plugin/Example/View/Helper/ExampleHelper.php.

#### Usando Helpers na Views

Antes de usar o helper na view, nós precisamos deixar nosso Controller saber que irá carregá-lo.

    <?php
    class RecipesController extends AppController {
    
        public $uses = array(
            'Recipe',
        );

        public $helpers = array(
            'Example', // 'Example.Example' se for do plugin Example
        );
    
        public function view($id)     {
            $recipe = $this->Recipe->findById($id);
            $this->set('recipe', $recipe);
        }
    
    }
    ?>

Agora nós podemos usar o helper da nossa view em /app/View/Recipes/view.ctp:

    <div class="recipes view">
        <h2><?php echo $recipe['Recipe']['title']; ?></h2>
        
        <p><?php echo $recipe['Recipe']['body']; ?></p>

        <p><?php echo $this->Example->lowercase('TEXT WILL BE CONVERTED TO LOWERCASE'); ?></p>
    </div>
