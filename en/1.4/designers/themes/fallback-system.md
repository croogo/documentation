# Fallback system

It is absolutely fine if you do not want to create each and every view file for
your theme. For example, if `app/View/Themed/MyTheme/Users/add.ctp` is not
found, CakePHP will try to locate `app/View/Users/add.ctp`.

## Extra fallbacks for Nodes

For theming, Croogo supports a few extra fallbacks for nodes, and whichever view
file found first is rendered. Below are the lists of four actions of
NodesController supporting extra view fallbacks:

#### index
  
   * app/View/Themed/MyTheme/Nodes/index\_{type}.ctp: where {type} is the alias
     of your content type, for e.g. 'blog'
   * app/View/Themed/MyTheme/Nodes/index.ctp
   * app/View/Nodes/index.ctp

#### search

   * app/View/Themed/MyTheme/Nodes/search\_{type}.ctp
   * app/View/Themed/MyTheme/Nodes/search.ctp
   * app/View/Nodes/search.ctp

#### term

   * app/View/Themed/MyTheme/Nodes/term\_{id}.ctp: where {id} is Term ID
   * app/View/Themed/MyTheme/Nodes/term\_{type}.ctp
   * app/View/Themed/MyTheme/Nodes/term.ctp
   * app/View/Nodes/term.ctp

#### view

   * app/View/Themed/MyTheme/Nodes/view\_{id}.ctp: where {id} is Node ID
   * app/View/Themed/MyTheme/Nodes/view\_{type}.ctp
   * app/View/Themed/MyTheme/Nodes/view.ctp
   * app/View/Nodes/view.ctp