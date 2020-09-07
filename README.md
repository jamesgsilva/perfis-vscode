# Perfis para Visual Studio Code

Adotar o Visual Studio Code como editor de código/texto padrão para diversas tecnologias (Javascript, GO, Java) não é uma escolha fácil.

Muitas vezes fazer alterações nas configurações (tema, fonte, etc), e gerenciar extensões (ativar/desativar) para cada tipo de projeto é um trabalho tedioso.

## Opções avançadas de linha de comando

Felizmente o VSCode pode ser iniciado pela linha de comando com [opções avançadas](https://code.visualstudio.com/docs/editor/command-line#_advanced-cli-options) para carregar configurações e extensões de um diretório especifico.

A primeira coisa que precisamos fazer é criar diretórios para armazenar as configurações e extensões de cada "perfil" de desenvolvimento.

```bash
mkdir -p code_profiles/java/{exts,data}
mkdir -p code_profiles/go/{exts,data}
mkdir -p code_profiles/nodejs/{exts,data}
```

Agora podemos abrir o VS Code pelo terminal com as opções `--extensions-dir` e `--user-data-dir` apontando para as extensões e configurações dos "perfis" criados.

```bash
code --extensions-dir ~/code_profiles/java/exts --user-data-dir ~/code_profiles/java/data
```

Vamos iniciar o "perfil" java e instalar algumas extensões (maven, spring, etc) comuns em projetos java web.

![Perfil java VS Code!](https://i.imgur.com/KZubrvS.png "Perfil java VS Code")

Vemos 22 extensões instaladas no "perfil" java.

Agora para ter certeza de que fizemos tudo certo, vamos iniciar o VS Code com o "perfil" nodejs e instalar algumas extensões (eslint, etc) comuns no universo javascript.

`code --extensions-dir ~/code_profiles/nodejs/exts --user-data-dir ~/code_profiles/nodejs/data`

![Perfil nodejs VS Code!](https://i.imgur.com/Wnf3TGa.png "Perfil nodejs VS Code")

Agora temos apenas 8 extensões instaladas no "perfil" nodejs.

A configuração de cada perfil (`settings.json`) fica dentro do subdiretório `User` da opção `--user-data-dir`.

## Criando apelidos

Agora que podemos alternar entre "perfis", vamos criar apelidos, atalhos no bash para não ter que sempre lembrar de todos esses comandos por completo.

Adicione `alias` ao arquivo de perfil do seu usuário (`~/.bash_profile`, `~/.zshrc`, `~/.profile`, ou `~/.bashrc`) para cada "perfil" do VS Code.

```bash
`alias code-java="code --extensions-dir ~/code_profiles/java/exts --user-data-dir ~/code_profiles/java/data"`

`alias code-node="code --extensions-dir ~/code_profiles/nodejs/exts --user-data-dir ~/code_profiles/nodejs/data"`

`alias code-go="code --extensions-dir ~/code_profiles/go/exts --user-data-dir ~/code_profiles/go/data"`
```

Agora, quando quiser usar um "perfil", tudo que precisa fazer é usar os atalhos.

```bash
code-java ~/workspaces/spring-quickstart
```

## Extensão Profile Switcher

Se você não quiser ter todo esse trabalho, o Aaron Powell criou a extensão [Profile Switcher](https://marketplace.visualstudio.com/items?itemName=aaronpowell.vscode-profile-switcher) que permite salvar vários "perfis" e trocar entre eles de dentro do VSCode.

## Referencia

Andy Van Slaars, [Profile Codes](https://github.com/avanslaars/code-profiles).