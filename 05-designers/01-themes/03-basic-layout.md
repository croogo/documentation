# Basic layout

Lets call our theme **my\_theme**, so we need to place our default layout at /app/views/themed/my\_theme/layouts/default.ctp.

At the beginning, we have something like this:

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
        <head>
        </head>
        
        <body>
        </body>
    </html>

## The HEAD

This is where your page title, meta information, css, javascript info are shown. Croogo has a [LayoutHelper](http://github.com/croogo/croogo/blob/master/views/helpers/layout.php) to make things easier for you. You also get to use CakePHP's core helpers for more general tasks.

#### Page title

**$title\_for\_layout** variable is set from your controller (can be done from views too). And **Configure::read('Site.title')** is your website's title that you can set from admin panel under **Settings &gt; Site**.

    <head>
        <title><?php echo $title_for_layout ' | ' . Configure::read('Site.title'); ?></title>
    </head>

#### Meta tags

This is as simple as calling a method from LayoutHelper. **$layout->meta()** outputs all meta tags for your content.

    <head>
        <title><?php echo $title_for_layout ' | ' . Configure::read('Site.title'); ?></title>
        <?php echo $layout->meta(); ?>
    </head>

#### Feeds

**$layout->feed()** will output your RSS feed link for your promoted content.

    <head>
        <title><?php echo $title_for_layout ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
        ?>
    </head>

#### CSS

If you have your css file placed under /app/views/themed/my\_theme/webroot/css/theme.css:

    <head>
        <title><?php echo $title_for_layout ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
            echo $html->css(array('theme'));
        ?>
    </head>

#### Javascript

Croogo uses jQuery for all it's javascript related tasks, so you need to load this library before any other javascript:

    <head>
        <title><?php echo $title_for_layout ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
            echo $html->css(array('theme'));
            echo $html->script(array('jquery/jquery.min'));
        ?>
    </head>

Croogo also has a **Croogo** object in javascript that stores information like the application's base path, etc. This is useful for other javascript related tasks. It can done by calling a single method **$layout-&gt;js()**:

    <head>
        <title><?php echo $title_for_layout ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
            echo $html->css(array('theme'));
            echo $html->script(array('jquery/jquery.min'));
            echo $layout->js();
        ?>
    </head>

CakePHP allows you to load javascript from your views so they go directly inside HEAD. For this, you need to echo out the variable **$scripts\_for\_layout**.

    <head>
        <title><?php echo $title_for_layout ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $layout->meta();
            echo $layout->feed();
            echo $html->css(array('theme'));
            echo $html->script(array('jquery/jquery.min'));
            echo $layout->js();
            echo $scripts_for_layout;
        ?>
    </head>

## The BODY

This is where you output the actual content that is visible in the browser.

#### Content

The output generated from your view is available in the variable **$content\_for\_layout**:

    <body>
        <div id="content">
        <?php echo $content_for_layout; ?>
        </div>
    </body>

#### Menu

If you want to show a menu with alias **main**, it is as simple as **$layout->menu('main')**. This will generate a nested unordered list of your main menu:

    <body>
        <div id="nav">
        <?php echo $layout->menu('main'); ?>
        </div>

        <div id="content">
        <?php echo $content_for_layout; ?>
        </div>
    </body>

#### Blocks

If you want to show the blocks that belong to **right** region, just add **$layouts->blocks('right')**:

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

## Final code of default.ctp

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
        <head>
            <title><?php echo $title_for_layout ' | ' . Configure::read('Site.title'); ?></title>
            <?php 
                echo $layout->meta();
                echo $layout->feed();
                echo $html->css(array('theme'));
                echo $html->script(array('jquery/jquery.min'));
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