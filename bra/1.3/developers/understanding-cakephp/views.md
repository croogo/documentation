# Views

Fonte original: [http://book.cakephp.org/view/1078/Views](http://book.cakephp.org/view/1078/Views).

## O que é uma View?

Views são o V no MVC. Views são responsáveis por gerar a saída específica necessária para a requisição. Muitas vezes isto é na forma de HTML, XML, ou JSON, mas streaming de arquivos e criação de PDF em que os usuários podem baixar são também responsabilidades da View.

## Código

Do exemplo anterior de Recipes, nós colocaremos o arquivo da view em /app/View/Recipes/view.ctp.

    <div class="recipes view">
        <h2><?php echo $recipe['Recipe']['title']; ?></h2>
        
        <p><?php echo $recipe['Recipe']['body']; ?></p>
    </div>

#### View do Plugin

Se fosse a view do plugin Recipes, seria encontrado em /app/Plugin/Recipes/View/view.ctp.