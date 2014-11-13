# Layout básico

Vamos chamar nosso tema **my\_theme**, então nós precisamos colocar o nosso layout padrão em /app/views/themed/my\_theme/layouts/default.ctp.

No início, nós temos algo como isto:

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
        <head>
        </head>
        
        <body>
        </body>
    </html>

## O HEAD

Aqui é onde informações como título da página, meta informações, css, javascript são mostradas. O Croogo tem um [LayoutHelper](http://github.com/croogo/croogo/blob/master/views/helpers/layout.php) para facilitar as coisas para você. Você também pode usar os Helpers do CakePHP para tarefas mais genéricas. 

#### Título da página

**$title\_for\_layout** esta variável é setada pelo seu Controller (pode ser feito pela View também). E o **Configure::read('Site.title')** é o título do seu website que você pode setar pelo painel administrativo, em **Settings &gt; Site**.

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
    </head>

#### Meta tags

Isto é tão simples que chamando um método de LayoutHelper **$layout->meta()** mostra todas as meta tags para o seu conteúdo.

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php echo $layout->meta(); ?>
    </head>

#### Feeds

**$layout->feed()** irá mostrar o link do RSS feeds para o conteúdo marcado com status promovido.

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
        ?>
    </head>

#### CSS

O arquivo css deve ficar localizado em /app/views/themed/my\_theme/webroot/css/theme.css:

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
            echo $html->css(array('theme'));
        ?>
    </head>

#### Javascript

O Croogo tem um objeto **Croogo** em javascript que armazena informações como o caminho base da aplicação, etc. Isto é útil para outras tarefas em javascript relacionadas. Pode ser feito chamando um método simples **$layout-&gt;js()**:

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
            echo $html->css(array('theme'));
            echo $layout->js();
        ?>
    </head>

O CakePHP permite você carregar javascript da view, e ele joga diretamente para dentro do HEAD. Para isso, você precisa dar echo na variável **$scripts\_for\_layout**.

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
            echo $html->css(array('theme'));
            echo $layout->js();
            echo $scripts_for_layout;
        ?>
    </head>

## O BODY

Este é onde você vai imprimir o conteúdo atual que estará visível no navegador.

#### Conteúdo

O conteúdo gerado pela view está disponível na variável **$content\_for\_layout**:

    <body>
        <div id="content">
        <?php echo $content_for_layout; ?>
        </div>
    </body>

#### Menu

Se você quiser exibir um menu com alias **main**, é tão simples como **$layout->menu('main')**. Será gerada uma lista não ordenada aninhada do seu menu main:

    <body>
        <div id="nav">
        <?php echo $layout->menu('main'); ?>
        </div>

        <div id="content">
        <?php echo $content_for_layout; ?>
        </div>
    </body>

#### Blocos

Se você quer mostrar o bloco que pertence a uma região **right**, apenas adicione **$layouts->blocks('right')**:

    <body>
        <div id="nav">
        <?php echo $layout->menu('main'); ?>
        </div>
        
        <div id="content">
        <?php echo $content_for_layout; ?>
        </div>
        
        <div id="sidebar">
        <?php echo $layout->blocks('right'); ?>
        </div>
    </body>

## Código final de default.ctp

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
        <head>
            <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
            <?php 
                echo $layout->meta();
                echo $layout->feed();
                echo $html->css(array('theme'));
                echo $layout->js();
                echo $scripts_for_layout;
            ?>
        </head>
        
        <body>
            <div id="nav">
            <?php echo $layout->menu('main'); ?>
            </div>
        
            <div id="content">
            <?php echo $content_for_layout; ?>
            </div>
        
            <div id="sidebar">
            <?php echo $layout->blocks('right'); ?>
            </div>
        </body>
    </html>