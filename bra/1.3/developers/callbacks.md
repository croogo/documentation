# Callbacks

## Components

Os callbacks seguintes são [suportados por components](http://book.cakephp.org/view/996/Creating-Components#MVC-Class-Access-Within-Components-998) pelo CakePHP.

* **initialize**: Chamado antes do Controller::beforeFilter()
* **startup**: Chamado depois do Controller::beforeFilter() e antes da action do controller
* **beforeRender**: Chamado depois do Controller::beforeRender(), depois da classe view ser carregada, e antes do Controller::render()
* **shutdown**: Chamada depois de Controller::render() e antes da saída ser exibida no browser.

#### Código

    <?php
    class ExampleComponent extends Component {
    
        //chamada antes de Controller::beforeFilter()
        public function initialize(&$controller, $settings = array()) {
            // salvando a referência do controller para ser usado depois
            $this->controller =& $controller;
        }
    
        //chamado depois de Controller::beforeFilter()
        public function startup(&$controller) {
        }
    
        //chamado depois de Controller::beforeRender()
        public function beforeRender(&$controller) {
        }
        
        //chamado depois de Controller::render()
        public function shutdown(&$controller) {
        }
    
        //chamado antes de Controller::redirect()
        public function beforeRedirect(&$controller, $url, $status=null, $exit=true) {
        }
    
        public function redirectSomewhere($value) {
            // utilizando um método no controller
            $this->controller->redirect($value);
        }
    
    }
    ?>

Leia mais sobre components em [http://book.cakephp.org/view/993/Components](http://book.cakephp.org/view/993/Components).

## Helpers

Os callbacks seguintes são [suportados por helpers](http://book.cakephp.org/view/1097/Creating-Helpers#Callback-method-1099) pelo CakePHP:

* **beforeRender**: Chamado antes da view ser renderizada.
* **afterRender**: Chamado depois da view ser renderizada mas antes do layout ser renderizado.
* **beforeLayout**: Chamado antes do layout ser renderizado.
* **afterLayout**: Chamado depois do layout ser renderizado.

#### Callbacks extras do Croogo para melhor integração

* **afterSetNode**: Chamado depois de LayoutHelper::setNode(). Um bom lugar para mudar o conteúdo.
* **beforeNodeInfo**: Chamado antes de LayoutHelper::nodeInfo().
* **afterNodeInfo**: Chamado depois de LayoutHelper::nodeInfo().
* **beforeNodeBody**: Chamado antes de LayoutHelper::nodeBody().
* **afterNodeBody**: Chamado depois de LayoutHelper::nodeBody().
* **beforeNodeMoreInfo**: Chamado antes de LayoutHelper::nodeMoreInfo().
* **afterNodeMoreInfo**: Chamado depois de LayoutHelper::nodeMoreInfo()

#### Code

    <?php
    class ExampleHelper extends AppHelper {
    
        public $helpers = array(
            'Html',
            'Layout',
        );
    
        public function beforeRender() {
        }
    
        public function afterRender() {
        }
    
        public function beforeLayout() {
        }
    
        public function afterLayout() {
        }
    
        public function afterSetNode() {
            // valor dos campos podem ser alterados aqui
            $currentTitle = $this->Layout->node('title');
            $modifiedTitle = $currentTitle . ' [Modificado por ExampleHelper]';
            $this->Layout->setNodeField('title', $modifiedTitle);
        }
    
        public function beforeNodeInfo() {
            return '<p>beforeNodeInfo</p>';
        }
    
        public function afterNodeInfo() {
            return '<p>afterNodeInfo</p>';
        }
    
        public function beforeNodeBody() {
            return '<p>beforeNodeBody</p>';
        }
    
        public function afterNodeBody() {
            return '<p>afterNodeBody</p>';
        }
    
        public function beforeNodeMoreInfo() {
            return '<p>beforeNodeMoreInfo</p>';
        }
    
        public function afterNodeMoreInfo() {
            return '<p>afterNodeMoreInfo</p>';
        }
    }
    ?>

Aprenda mais sobre helpers em [http://book.cakephp.org/view/1095/Helpers](http://book.cakephp.org/view/1095/Helpers).