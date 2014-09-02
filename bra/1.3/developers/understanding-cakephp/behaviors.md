# Behaviors

Original source: [http://book.cakephp.org/view/1071/Behaviors](http://book.cakephp.org/view/1071/Behaviors).

Model behaviors are a way to organize some of the functionality defined in CakePHP models. They allow us to separate logic that may not be directly related to a model, but needs to be there. By providing a simple yet powerful way to extend models, behaviors allow us to attach functionality to models by defining a simple class variable. That's how behaviors allow models to get rid of all the extra weight that might not be part of the business contract they are modeling, or that is also needed in different models and can then be extrapolated.

As an example, consider a model that gives us access to a database table which stores structural information about a tree. Removing, adding, and migrating nodes in the tree is not as simple as deleting, inserting, and editing rows in the table. Many records may need to be updated as things move around. Rather than creating those tree-manipulation methods on a per model basis (for every model that needs that functionality), we could simply tell our model to use the TreeBehavior, or in more formal terms, we tell our model to behave as a Tree. This is known as attaching a behavior to a model. With just one line of code, our CakePHP model takes on a whole new set of methods that allow it to interact with the underlying structure.

## Code

If your Behavior's name is **Example**, it would be found at /app/models/behaviors/example.php.

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

#### Plugin behaviors

If it is Example plugin's behavior, it would be found at /app/plugins/example/models/behaviors/example.php.

#### Using Behaviors in Models

    <?php
    class Recipe extends AppModel {
    
        public $name = 'Recipe';

        public $actsAs = array(
            'Example' => array( // 'Example.Example' if it is from Example plugin
                'config1' => 'value here',
                'config2' => 'value here',
            ),
        );
    
    }
    ?>