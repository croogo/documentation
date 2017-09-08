# Blocos

Blocos é o que você vê no barra lateral (região `direita' no tema padrão) as caixas. Eles pertencem a uma região em particular.

## Elementos

Todos os blocos são renderezidos via elemento **bloco.ctp** (encontrado em app/views/elements/bloco.ctp). Você pode usar seu próprio elemento também, para seus blocos editando o campo 'element' quando adiciona um block.

**Dica**: Se é um elemento de plugin, entre com 'plugin\_name.element\_name'.

## Como exibir Isto ou Aquilo em um bloco?

Você é capaz de mostrar um elemento, menu, vocabulário (lista de links aninhadas), ou a entrada de texto de uma lista de nodes especialmente formatada em blocos em seu corpo. 

### Elemento

Para um elemento com nome do arquivo **my_element.php**:

    [element:my_element] OR [e:my_element]

Passando varaiáveis para seu elemento:

    [element:my_element myVar="value here" anotherVar="value here"]

Para elementos de plugin:

    [element:my_element plugin="my_plugin"]

### Menu

Para um Menu com alias **main**:

    [menu:main] OR [m:main]

### Vocabulário

Para um Vocabulário com alias **categories**:

    [vocabulary:categories] OR [v:categories]

### Nodes

Por exemplo, você pode querer exibir uma lista dos 5 mais recentes posts do blog como um bloco:

    [node:recent_posts conditions="Node.type:blog;Node.status:1" order="Node.id DESC" limit="5"]