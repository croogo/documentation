# Blocks

Blocks are what you see in the sidebar (‘right’ region in default theme) as boxes. They belong to a particular region.

## Elements

All blocks are rendered via **block.ctp** element (found in app/views/elements/block.ctp). You can use your own element too for your blocks by editing 'element' field when adding a block.

**Tip**: If it is a plugin element, enter 'plugin\_name.element\_name'.

## How to display a THIS and THAT in a block?

You are able to show an element, menu, vocabulary (nested list of terms), or a list of nodes by entering specially formatted text in your block’s body.

### Element

For an element with file name **my_element.ctp**:

    [element:my_element] OR [e:my_element]

Passing variables to your element:

    [element:my_element myVar="value here" anotherVar="value here"]

For plugin elements:

    [element:my_element plugin="my_plugin"]

### Menu

For a Menu with alias **main**:

    [menu:main] OR [m:main]

### Vocabulary

For a Vocabulary with alias **categories**:

    [vocabulary:categories] OR [v:categories]

### Nodes

For example, you want to show a list of 5 most recent blog posts as a block:

    [node:recent_posts conditions="Node.type:blog;Node.status:1" order="Node.id DESC" limit="5"]