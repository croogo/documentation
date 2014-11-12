# Tipos de Conteúdo

Por padrão, há três tipos de conteúdo:

* **Page**: para páginas
* **Blog**: para posts para blog
* **Node**: para quando não tiver certeza que tipo de conteúdo usar

Se você acha que precisa de um novo tipo de conteúdo, você é capaz de criar um pelo painel admin.

## Parâmetros

Quando você adiciona ou edita tipo de conteúdo, você vai notar um campo 'Params' onde você pode entrar com parâmetros. É esperado que um parâmetro seja introduzido por linha com um par chave/valor usando o sinal de igual como separador. Exemplo abaixo:

    my_param_key=value_here
    another_key=another_value

Chaves de parâmetros suportadas para tipos de conteúdo:

* **nodes\_per\_page**: Limite de paginação por nodes

Você é livre para usar mais chaves para os parâmetros e eles estarão disponíveis de uma forma agradável formatado por [ParamsBehavior](http://github.com/croogo/croogo/blob/master/models/behaviors/params.php).