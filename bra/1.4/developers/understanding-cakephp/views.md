# Views

Read the CakePHP docs on Views:
[http://book.cakephp.org/2.0/en/views.html](http://book.cakephp.org/2.0/en/views.html).

## What is a View?

Views are the V in MVC. Views are responsible for generating the specific output
required for the request. Often this is in the form of HTML, XML, or JSON, but
streaming files and creating PDF's that users can download are also
responsibilities of the View Layer.

## Code

From previous example of Recipes, we will be placing out view file at
`/app/View/Recipes/view.ctp`.

    <div class="recipes view">
        <h2><?php echo $recipe['Recipe']['title']; ?></h2>

        <p><?php echo $recipe['Recipe']['body']; ?></p>
    </div>

#### Plugin Views

If it is Recipes plugin's view, it would be found at
`/app/Plugin/Recipes/View/view.ctp`.