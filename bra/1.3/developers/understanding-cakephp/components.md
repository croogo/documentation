# Componentes

Fonte original: [http://book.cakephp.org/view/993/Components](http://book.cakephp.org/view/993/Components).

## O que é um Component?

Components são pacotes de lógicas que são compartilhadas entre controllers. Se você se pega copiando e colando coisas entre controllers, você pode considerar envolver algumas funcionalidades em um componente.

## Código

Assumindo que você quer criar um componente Example, ele seria encontrado em /app/Controller/Component/ExampleComponent.php

    <?php
    class ExampleComponent extends Component {
    
        public function myMethod() {
            // seu código aqui
        }
    
    }
    ?>

#### Components de Plugin

Se fosse um component do plugin Example, ele seria encontrado em /app/Plugin/Example/Controller/Component/ExampleComponent.php

#### Usando Components nos Controllers.

    <?php
    class RecipesController extends AppController {

        public $components = array(
            'Example', // 'Example.Example' se for de um plugin Example
        );
    
        function view($id)     {
            // chama o método do Component
            $this->Example->myMethod();
        }
    
    }
    ?>