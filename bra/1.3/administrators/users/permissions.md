# Permissões

Croogo usa o ACL do CakePHP para gerenciar as permissões do usuário. Para ser honesto, o ACL pode ser muito complicado de entender para iniciantes. Mas o Croogo leva esta dor embora, provendo uma simples e utilizável interface para gerenciar as permissões.

Uma vez que a aplicação foi construída com um framework MVC, qualquer url (diferente do normal como arquivos CSS e imagens) você acessa a saída através de um método do Controller. Por exemplo, quando você visita o post 'Hello World' do blog, ele exibirá o método **view** do Controller **Nodes**.

Para gerenciar as permissões:

* Logar no seu painel administrativo
* Vá para **Users &gt; Permissions**
* Clique em **Nodes**, isto então exibirá a lista de todos os métodos
* Então clique na ícone cruz/riscado da linha da **view** para ativar ou desativar acesso do papel ao método.