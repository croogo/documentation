# Behaviors

Fonte original: [http://book.cakephp.org/view/1071/Behaviors](http://book.cakephp.org/view/1071/Behaviors).

Os behaviors do model são formas de organizar algumas das funcionalidades definidas nos models do CakePHP. Eles nos permitem separar  lógica que podem não estar diretamente relacionadas ao model, mas é preciso estar lá. Para prover uma simples, mas ainda poderosa forma de extender models, os behaviors nos permitem anexar funcionalidades aos models definindo uma simples classe variável. Isso é como os behaviors permitem models para se livrar de todo o peso extra que pode não ser parte do contrato de negócio que estão modelando ou que também é necessária em diferentes modelos e podem ser extrapolados.

Por exemplo, considere um model que nos dá acesso a uma tabela de banco de dados que armazena informações na estrutura de árvores. Removendo, adicionando, e migrando nós em uma árvore não é tão fácil como excluir, inserir, e editar registros na tabela. Muitos registros podem precisar ser atualizado conforme as coisas movem-se ao redor. Em vez de criar aqueles métodos de manipulação em árvores por modelo base (para cada model que precisar desta funcionalidade), nós poderiamos simplificar dizendo ao nosso model para usar o TreeBehavior, ou em termos formais, nós dizemos ao nosso model se comporte como uma árvore. Isto é conhecido como anexar um comportamento para um modelo. Com apenas uma linha de código, o nosso modelo CakePHP assume um novo conjunto de métodos que permitem interagir com a estrutura subjacente.

## Código

Se o nome do seu behavior é **Example**, ele seria localizado em /app/Model/Behavior/ExampleBehavior.php

    <?php
    class ExampleBehavior extends ModelBehavior {
    
        public function setup(&$model, $config = array()) {
            $this->settings[$model->alias] = $config;
        }
    
        public function beforeFind(&$model, $query) {
            return $query;
        }
    
        public function afterFind(&$model, $results, $primary) {
    
        }

        public function beforeDelete(&$model, $cascade = true) {
            return true;
        }
    
        public function afterDelete(&$model) {
    
        }
    
        public function beforeValidate(&$model) {
            return true;
        }
    
    ?>

#### Behaviors de Plugin

Se fosse um behavior do plugin Example, seria localizado em /app/Plugin/Example/Model/Behavior/ExampleBehavior.php

#### Usando Behaviors nos Models

    <?php
    class Recipe extends AppModel {
    
        public $name = 'Recipe';

        public $actsAs = array(
            'Example' => array( // 'Example.Example' se for de um plugin Example
                'config1' => 'value here',
                'config2' => 'value here',
            ),
        );
    
    }
    ?>