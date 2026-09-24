## Passo 1: Revisar e adicionar dependências usando o dependency graph

**Qual a importância de proteger a cadeia de suprimentos do seu repositório?**: Com o uso acelerado de open source, a maioria dos projetos depende de centenas de dependências de código aberto. Isso cria um problema de segurança: e se as dependências que você usa forem vulneráveis? Você poderia estar colocando seus usuários em risco de um ataque à cadeia de suprimentos. Uma das coisas mais importantes que você pode fazer para proteger sua cadeia de suprimentos é corrigir dependências vulneráveis e substituir qualquer malware.

O GitHub oferece uma série de recursos para ajudar você a entender as dependências do seu ambiente, conhecer as vulnerabilidades delas e corrigi-las. Os recursos de cadeia de suprimentos no GitHub são:

- Dependency graph
- Dependency review
- Dependabot alerts
- Dependabot updates
  - Dependabot security updates
  - Dependabot version updates

**O que é um dependency graph**: O dependency graph é um resumo dos arquivos de manifesto e de lock armazenados em um repositório, além de quaisquer dependências enviadas para o repositório pela dependency submission API (beta). Para cada repositório, ele mostra:

- Dependencies: os ecossistemas e pacotes dos quais ele depende
- Dependents: os repositórios e pacotes que dependem dele

### :keyboard: Atividade 1.1: Verificar se o dependency graph está habilitado

**Recomendamos abrir outra aba do navegador para realizar as atividades a seguir, assim você mantém estas instruções abertas para consulta.**

>[!NOTE]
> O dependency graph vem habilitado por padrão em todos os novos repositórios públicos.

1. Navegue até a aba **Settings**.
1. Clique em **Advanced Security**.
1. Verifique se o **Dependency Graph** está **Enabled**

### :keyboard: Atividade 1.2: Adicionar uma nova dependência e visualizar seu dependency graph

1. Navegue até a aba **Code** e localize a pasta `code/src/AttendeeSite`.
1. Commit o conteúdo a seguir na branch `main`, no arquivo `package-lock.json`, como o último item do mapa `dependencies` _(depois da antepenúltima chave `}` e antes das duas últimas chaves)_

    > 🪧 **Nota:** Você pode editar e commitar o arquivo diretamente no github.com ou pressionar a tecla `.` para abrir o editor leve e fazer as alterações.

    ```json
    ,
    "follow-redirects": {
      "version": "1.14.1",
      "resolved": "https://registry.npmjs.org/follow-redirects/-/follow-redirects-1.14.1.tgz",
      "integrity": "sha512-HWqDgT7ZEkqRzBvc2s64vSZ/hfOceEol3ac/7tKwzuvEyWx3/4UegXh5oBOIotkGsObyk3xznnSRVADBgWSQVg=="
    }
    ```

1. Navegue até a aba **Insights**.
1. Selecione **Dependency graph** na barra de navegação lateral.
1. Revise todas as dependências na aba **Dependencies**.
1. Procure por `follow-redirects` e revise a nova dependência que você acabou de adicionar.
   ![Captura de tela mostrando a dependência "follow-redirects".](https://user-images.githubusercontent.com/6351798/196288729-734e3319-c5d7-4f35-a19c-676c12f0e27d.png)
1. Com a nova dependência adicionada, a Mona já deve estar verificando seu trabalho. Dê um momento a ela e fique de olho nos comentários. Você a verá responder com informações de progresso e a próxima lição.
