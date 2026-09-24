## Passo 4: Habilitar e disparar os version updates do Dependabot

_Muito bem!_ :partying_face:

Agora você automatizou o processo para que o Dependabot te alerte sobre vulnerabilidades nas suas dependências e crie pull requests para atualizá-las para versões seguras! Neste ponto, basta revisar o pull request e fazer o merge para se manter em dia com problemas de segurança nas dependências.

> [!NOTE]  
> Você percebeu que havia vários pull requests sugeridos pelo Dependabot? Você fez o merge apenas daquele relacionado à dependência **axios**, mas os outros desapareceram do painel **Pull requests**. Isso acontece porque o upgrade da dependência axios disparou mudanças em outras dependências transitivas, que podem ter sido removidas ou atualizadas para outras versões. Sempre que houver uma mudança no seu dependency graph, o Dependabot revisa automaticamente os pull requests existentes e fecha aqueles que deixaram de ser relevantes. Então não faça merge de tudo de uma vez, deixe o Dependabot trabalhar por você! 
<img width="955" alt="Captura de tela mostrando que o PR do axios foi mesclado e que os outros 2 foram fechados" src="../images/axios-pr-merged-others-closed.png" />


O recurso de security updates ajuda a automatizar o processo de resolver alertas, mas e quanto a simplesmente manter as versões atualizadas? Também podemos automatizar a geração de pull requests para versões atualizadas de dependências usando o recurso de version updates do Dependabot.

**O que são os version updates do Dependabot?**: Além dos alertas de segurança, o Dependabot também pode tirar o trabalho manual da manutenção das suas dependências. Você pode usá-lo para garantir que seu repositório acompanhe automaticamente os lançamentos mais recentes dos pacotes e aplicações dos quais depende. Assim como nos alertas de segurança, o Dependabot identifica uma dependência desatualizada e cria um pull request para atualizar o manifesto para a versão mais recente.

Vamos ver como isso funciona!

### :keyboard: Atividade 4.1: Habilitar e disparar os version updates do Dependabot

1. Navegue até a aba **Settings** e selecione **Advanced Security**.
1. Localize **Dependabot version updates** e clique em **Configure** para abrir um novo editor de arquivo com o conteúdo pré-preenchido. O arquivo se chama `dependabot.yml`.
1. Note que o arquivo já vem preenchido para atualizar as GitHub Actions do repositório, o ecossistema de pacotes `github-actions`.
1. Edite o arquivo de configuração `dependabot.yml` para incluir outra entrada. Ele deve ficar assim:

   ```yaml
   version: 2
   updates:
     - package-ecosystem: "github-actions"
       directory: "/"
       schedule:
         interval: "monthly"
     - package-ecosystem: "nuget"
       directory: "/code/"
       schedule:
         interval: "weekly"
   ```
  
   > 💡 **Dica:** Embora você possa editar e commitar um arquivo diretamente no github.com, também é possível pressionar a tecla ponto `.` para abrir um editor leve do VS Code diretamente no navegador.

1. Commit suas alterações diretamente na branch `main`.
1. Com o arquivo de configuração atualizado, a Mona já deve estar verificando seu trabalho. Dê um momento a ela e fique de olho nos comentários. Você a verá responder com informações de progresso e a próxima lição.

Você acabou de configurar os version updates do Dependabot para executar e verificar atualizações da seguinte forma:

- Verificar uma vez por mês se há atualizações para GitHub Actions e criar pull requests para atualizar as que estiverem desatualizadas.
- Verificar uma vez por semana se há atualizações para pacotes .NET e criar pull requests para atualizar os que estiverem desatualizados. Por padrão, essa verificação roda na segunda-feira; para executá-la em outro dia, veja [schedule.day](https://docs.github.com/en/code-security/dependabot/dependabot-version-updates/configuration-options-for-the-dependabot.yml-file#scheduleday).
