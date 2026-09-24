## Passo 3: Habilitar e disparar os security updates do Dependabot

_Bom trabalho habilitando, visualizando e criando alertas do Dependabot :sparkles:_

Habilitar os alertas do Dependabot no nosso repositório foi um ótimo passo para melhorar a segurança do código, mas ainda precisávamos selecionar manualmente um alerta e depois escolher manualmente a opção de criar o pull request. Seria ótimo ampliar ainda mais a automação e a manutenção das nossas dependências! Pois bem, com os security updates do Dependabot, podemos fazer exatamente isso.

**O que são os security updates do Dependabot?**

Quando esse recurso está habilitado, o Dependabot detecta *e* corrige dependências vulneráveis para você, abrindo pull requests automaticamente para resolver os alertas do Dependabot.

Nós criamos manualmente um pull request para corrigir o alerta "Prototype Pollution in minimist", mas vamos habilitar os security updates do Dependabot para automatizar esse processo em alertas futuros!

### :keyboard: Atividade 3.1: Habilitar e disparar os security updates do Dependabot

1. Navegue até a aba **Settings** e selecione **Advanced Security**.
1. Habilite os **Dependabot security updates**. Pode ser necessário aguardar de 30 a 60 segundos antes de ver novos pull requests.
1. Navegue até a aba **Pull requests** do repositório para ver o que o Dependabot encontrou.
1. Encontre o novo pull request que solicita a correção da dependência **axios**.
1. Revise e faça o merge do pull request.
1. Com o pull request mesclado, a Mona já deve estar verificando seu trabalho. Dê um momento a ela e fique de olho nos comentários. Você a verá responder com informações de progresso e a próxima lição.