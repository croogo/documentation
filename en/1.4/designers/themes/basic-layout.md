# Basic Layout

Lets call our theme **MyTheme**, so we need to place our default layout at
`/app/View/Themed/MyTheme/Layouts/default.ctp`.

At the beginning, we have something like this:

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
        <head>
        </head>
        
        <body>
        </body>
    </html>

## The HEAD

This is where your page title, meta information, css, javascript info are shown.
Croogo has a
[LayoutHelper](http://github.com/croogo/croogo/blob/1.4/View/Helper/LayoutHelper.php)
to make things easier for you. You also get to use CakePHP's core helpers for
more general tasks.

#### Page title

`$title_for_layout` variable is set from your controller (can be done from
views too). And `Configure::read('Site.title')` is your website's title that
you can set from admin panel under **Settings &gt; Site**.

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
    </head>

#### Meta tags

This is as simple as calling a method from LayoutHelper.
`$this->Layout->meta()` outputs all meta tags for your content.

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php echo $this->Layout->meta(); ?>
    </head>

#### Feeds

`$this->Layout->feed()` will output your RSS feed link for your promoted
content.

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $this->Layout->meta();
            echo $this->Layout->feed();
        ?>
    </head>

#### CSS

If you have your css file placed under
`/app/View/Themed/MyTheme/webroot/css/theme.css`:

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $this->Layout->meta();
            echo $this->Layout->feed();
            echo $this->Html->css(array('theme'));
        ?>
    </head>

#### Javascript

Croogo has a **Croogo** object in javascript that stores information like the
application's base path, etc. This is useful for other javascript related tasks.
It can done by calling a single method `$layout->js()`:

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $this->Layout->meta();
            echo $this->Layout->feed();
            echo $this->Html->css(array('theme'));
            echo $this->Layout->js();
        ?>
    </head>

CakePHP allows you to load javascript from your views so they go directly inside
HEAD. For this, you need to echo out the variable `$scripts_for_layout`.

    <head>
        <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
        <?php 
            echo $this->Layout->meta();
            echo $this->Layout->feed();
            echo $this->Html->css(array('theme'));
            echo $this->Layout->js();
            echo $scripts_for_layout;
        ?>
    </head>

## The BODY

This is where you output the actual content that is visible in the browser.

#### Content

The output generated from your view is available in the variable
`$content_for_layout`:

    <body>
        <div id="content">
            <?php echo $content_for_layout; ?>
        </div>
    </body>

#### Menu

If you want to show a menu with alias **main**, it is as simple as
`$layout->menu('main')`. This will generate a nested unordered list of your
main menu:

    <body>
        <div id="nav">
            <?php echo $this->Layout->menu('main'); ?>
        </div>

        <div id="content">
            <?php echo $content_for_layout; ?>
        </div>
    </body>

#### Blocks

If you want to show the blocks that belong to **right** region, just add
`$layouts->blocks('right')`:

    <body>
        <div id="nav">
            <?php echo $this->Layout->menu('main'); ?>
        </div>
        
        <div id="content">
            <?php echo $content_for_layout; ?>
        </div>
        
        <div id="sidebar">
            <?php echo $this->Layout->blocks('right'); ?>
        </div>
    </body>

## Final code of default.ctp

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
        <head>
            <title><?php echo $title_for_layout . ' | ' . Configure::read('Site.title'); ?></title>
            <?php 
                echo $this->Layout->meta();
                echo $this->Layout->feed();
                echo $this->Html->css(array('theme'));
                echo $this->Layout->js();
                echo $scripts_for_layout;
            ?>
        </head>
        
        <body>
            <div id="nav">
                <?php echo $this->Layout->menu('main'); ?>
            </div>
        
            <div id="content">
                <?php echo $content_for_layout; ?>
            </div>
        
            <div id="sidebar">
                <?php echo $this->Layout->blocks('right'); ?>
            </div>
        </body>
    </html>