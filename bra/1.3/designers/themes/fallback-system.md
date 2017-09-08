# Sistema fallback

Isto é absolutamente excelente se você não quer criar cada e todos os arquivos de view para o seu tema. Por exemplo, se app/views/themed/my\_theme/users/add.ctp não for encontrado, o CakePHP irá tentar localizar em app/views/users/add.ctp.

## Fallbacks extras para Nodes
Para temas, Croogo suporta uns poucos fallbacks extras para nodes, e seja qual for o arquivo da view o primeiro encontrado será renderizado. Abaixo está a lista de quatro métodos de NodesController que tem suporte a fallbacks extras de views:

#### index
  
   * app/views/themed/my\_theme/nodes/index\_{type}.ctp: onde {type} é o alias do seu tipo de conteúdo, por exemplo 'blog'
   * app/views/themed/my\_theme/nodes/index.ctp
   * app/views/nodes/index.ctp

#### search

   * app/views/themed/my\_theme/nodes/search\_{type}.ctp
   * app/views/themed/my\_theme/nodes/search.ctp
   * app/views/nodes/search.ctp

#### term

   * app/views/themed/my\_theme/nodes/term\_{id}.ctp: onde {id} é o ID do termo
   * app/views/themed/my\_theme/nodes/term\_{type}.ctp
   * app/views/themed/my\_theme/nodes/term.ctp
   * app/views/nodes/term.ctp

#### view

   * app/views/themed/my\_theme/nodes/view\_{id}.ctp: onde {id} é o ID do Node
   * app/views/themed/my\_theme/nodes/view\_{type}.ctp
   * app/views/themed/my\_theme/nodes/view.ctp
   * app/views/nodes/view.ctp