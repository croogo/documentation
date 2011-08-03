# Fallback system

It is absolutely fine if you do not want to create each and every view files for your theme. For example, if app/views/themed/my\_theme/users/add.ctp is not found, CakePHP will try to locate app/views/users/add.ctp.

## Extra fallbacks for Nodes

For theming, Croogo supports a few extra fallbacks for nodes, and whichever view file found first is rendered. Below are the lists of four actions of NodesController supporting extra view fallbacks:

#### index
  
   * app/views/themed/my\_theme/nodes/index\_{type}.ctp: where {type} is the alias of your content type, for e.g. 'blog'
   * app/views/themed/my\_theme/nodes/index.ctp
   * app/views/nodes/index.ctp

#### search

   * app/views/themed/my\_theme/nodes/search\_{type}.ctp
   * app/views/themed/my\_theme/nodes/search.ctp
   * app/views/nodes/search.ctp

#### term

   * app/views/themed/my\_theme/nodes/term\_{id}.ctp: where {id} is Term ID
   * app/views/themed/my\_theme/nodes/term\_{type}.ctp
   * app/views/themed/my\_theme/nodes/term.ctp
   * app/views/nodes/term.ctp

#### view

   * app/views/themed/my\_theme/nodes/view\_{id}.ctp: where {id} is Node ID
   * app/views/themed/my\_theme/nodes/view\_{type}.ctp
   * app/views/themed/my\_theme/nodes/view.ctp
   * app/views/nodes/view.ctp