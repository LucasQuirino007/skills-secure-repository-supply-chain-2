## Passo 2: Habilitar e visualizar alertas do Dependabot

_Bom trabalho! :tada: Você adicionou e visualizou uma dependência usando o Dependency graph!_

Considerando a quantidade de dependências que nosso repositório usa, a manutenção delas precisa se tornar uma tarefa automatizada. Manter nosso código seguro é prioridade, então a primeira coisa a fazer é configurar uma forma de sermos notificados quando uma dependência que usamos for vulnerável ou for malware. Podemos fazer isso habilitando os alertas do Dependabot.

**O que são alertas do Dependabot?**

Os alertas do Dependabot informam que seu código depende de um pacote inseguro. Esses alertas referenciam o [GitHub Advisory Database](https://github.com/advisories), que contém uma lista de vulnerabilidades de segurança e malwares conhecidos, agrupados em duas categorias: **GitHub reviewed advisories** e **unreviewed advisories**.

Se o seu código depende de um pacote com uma vulnerabilidade de segurança, isso pode causar uma série de problemas para o seu projeto ou para quem o utiliza. Você deve atualizar para uma versão segura do pacote o quanto antes. Se o seu código usa malware, é preciso substituir o pacote por uma alternativa segura.

Vamos testar isso com a nossa recém-adicionada dependência `follow-redirects`!

### :keyboard: Atividade 2.1: Visualizar advisories de segurança no GitHub Advisory Database

1. Navegue até o [GitHub Advisory Database](https://github.com/advisories).
1. Digite ou cole `follow-redirects` na caixa de busca de advisories.
1. Clique em qualquer um dos advisories encontrados para ver mais informações.
1. Você verá os pacotes, o impacto, os patches, os workarounds e as referências do advisory.

Repare na longa lista de advisories da nossa dependência! Isso pode parecer assustador, mas na verdade é algo bom. Significa que a dependência está sendo mantida ativamente e que patches estão sendo publicados para remover as vulnerabilidades. Se tivéssemos os alertas do Dependabot habilitados, receberíamos avisos quando fosse necessário atualizar uma dependência e poderíamos agir rapidamente para protegê-la.

Vamos habilitar os alertas do Dependabot no nosso repositório!

### :keyboard: Atividade 2.2: Habilitar alertas do Dependabot

1. Navegue até a aba **Settings**.
1. Exiba as configurações de **Advanced Security**.
1. **Habilite** os alertas do Dependabot.
1. **Aguarde cerca de 60 segundos para o Dependabot verificar os alertas.**
1. Navegue até a aba **Security**.
1. Em "Vulnerability alerts", na barra lateral, selecione **Dependabot** para ver a lista de alertas do Dependabot da branch padrão.

O Dependabot nos alertou sobre vulnerabilidades nas dependências que usamos. Também podemos usar o Dependabot para nos ajudar a tratar essas vulnerabilidades, criando pull requests para atualizar a dependência para uma versão segura.

Vamos ver como isso funciona usando o Dependabot para criar um pull request a partir de um dos alertas!

### :keyboard: Atividade 2.3: Criar um pull request a partir de um alerta do Dependabot

1. Na lista de alertas do Dependabot, clique em "Prototype Pollution in minimist" para exibir mais informações.
1. Clique no botão **Create Dependabot security update** para criar um pull request que atualiza a dependência. Isso pode levar até 2 minutos.
1. Quando o pull request estiver aberto, a página do alerta é atualizada e passa a exibir o botão **Review security update**.
1. Clique no botão **Review security update** para exibir o pull request.
   - Você pode visualizar o pull request e a aba **Files changed** para revisar a atualização.
1. Volte para a aba **Conversation** e faça o merge do pull request.
1. Com o pull request mesclado, a Mona já deve estar verificando seu trabalho. Dê um momento a ela e fique de olho nos comentários. Você a verá responder com informações de progresso e a próxima lição.