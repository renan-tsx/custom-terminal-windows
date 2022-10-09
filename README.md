# custom-terminal-windows
Personalize o novo Windows Terminal, integre o Git Bash ao Windows Terminal e Personalize o Git Bash.

<a name="ancora"></a>
# Sumário
- [Prévia](#previa)
- [Requisitos](#requisitos)
    - [Windows Terminal](#wterminal)
    - [Git](#git)
    - [Scoop](#scoop)
    - [Oh-my-posh](#ohmyposh)
- [Configurações](#configuracoes)
    - [Adicionar Git Bash no Terminal](#addgit)
    - [Temas para Windows Terminal](#temas)
    - [Oh-my-posh](#ohmyposhconfig)
- [Consideracoes](#consideracoes)
- [Tutorial Notion](#notion)

# custom-terminal-windows

<a id="previa"></a>
# Prévia


Cada tema tem sua características, o larserikfinholt por exemplo indica através de símbolos algumas informações sobre a branch como:

- Se a branch está somente local
- Existe arquivos modificados  ~1
- Existe arquivos excluídos  -1
- Existe novos arquivos   ?1

[Themes | Oh My Posh](https://ohmyposh.dev/docs/themes)

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/main/Untitled.png)

<a id="requisitos"></a>
# Requisitos

<a id="wterminal"></a>
## Windows Terminal

Certifique que o Windows Terminal esteja instalado. </br>
O App está disponível na Microsoft Store. </br>
Acesse o link para outras formas de instalação e saber mais sobre ao app. </br>

[Instalação do Terminal do Windows](https://learn.microsoft.com/pt-br/windows/terminal/install)

<a id="git"></a>
## Git

Certifique que o Git esteja instalado.

[Downloads](https://git-scm.com/downloads)

<a id="scoop"></a>
## Scoop

Scoop é um instalador de programas via terminal. </br>
Abra o Windows PowerShell como administrador. </br>
Se o comando `scoop -v` for aceito aparecerá a versão instalada. </br>

Para instalar acesse o link e siga os passos

[](https://scoop.sh/)

<a id="ohmyposh"></a>
## Ho-my-posh

Um mecanismo de temas para qualquer Shell. </br>
Abra o Windows PowerShell como administrador. </br>
Se o comando `oh-my-posh --version` for aceito aparecerá a versão instalada. </br>

Para instalar acesse o link e siga os passos

[Windows | Oh My Posh](https://ohmyposh.dev/docs/installation/windows)

Baixe a Font [Meslo LGM NF](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/Meslo.zip), extraia todas as fontes para dentro de `C:\Windows\Fonts`

[Fonts | Oh My Posh](https://ohmyposh.dev/docs/installation/fonts)

<a id="configuracoes"></a>
# Configurações

<a id="addgit"></a>
## Adicionar Git Bash no terminal

Abra as Configurações do Windows Terminal

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%201.png)

Crie um novo perfil

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%202.png)

1. De uma nome ao perfil
2. Encontre o local de instalação do Git Bash
3. (opcional) Inicia o terminal sempre no mesmo diretório
4. Encontre o ícone do Git Bash

Salve as novas configurações

[Como identificar local de intalação do Git Bash](https://www.notion.so/Como-identificar-local-de-intala-o-do-Git-Bash-50c9989317cf460aa363b63e05dd028c)

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%203.png)

Feche a abra novamente o Windows Terminal para ter acesso a nova opção

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%204.png)

Esse é o terminah Git Bash integrado ao Windows Terminal.

Os próximos será adicionar Temas.

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%205.png)

<a id="temas"></a>
## Temas para Windows Terminal

O tema de sua preferência pode ser escolhido no site abaixo, clique em Get theme para copiar.

[Windows Terminal Themes](https://windowsterminalthemes.dev/)

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%206.png)

Abra novamente as configurações do Windows Terminal e clique em Abrir o arquivo JSON 

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%207.png)

Adicione o novo tema junto com os temas existentes

```json
"schemes": 
    [
        {
            "name": "Dracula",
            "background": "#1E1F29",
            "black": "#000000",
            "blue": "#BD93F9",
            "brightBlack": "#555555",
            "brightBlue": "#BD93F9",
            "brightCyan": "#8BE9FD",
            "brightGreen": "#50FA7B",
            "brightPurple": "#FF79C6",
            "brightRed": "#FF5555",
            "brightWhite": "#FFFFFF",
            "brightYellow": "#F1FA8C",
            "cursorColor": "#BBBBBB",
            "cyan": "#8BE9FD",
            "foreground": "#F8F8F2",
            "green": "#50FA7B",
            "purple": "#FF79C6",
            "red": "#FF5555",
            "selectionBackground": "#44475A",
            "white": "#BBBBBB",
            "yellow": "#F1FA8C"
        }
    ]
}
```

Modifique a propriedade `profiles` para o formato abaixo. </br>
A propriedade `list` pode estar em outro local, migre ela para dentro de profiles.

```json
"profiles": 
    {
        "defaults": 
        {
            "colorScheme": "Dracula",
            "cursorColor": "#888888",
            "cursorShape": "filledBox",
            "font": 
            {
                "face": "MesloLGM NF",
                "size": 14
            },
            "opacity": 100,
            "padding": "16"
        },
        "list": 
        [
          //...
        ]
    },
```

Tema Dark aplicado

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%208.png)

<a id="ohmyposhconfig"></a>
## Oh-my-posh

Crie o arquivo .bashrc dentro de C:/Users/<seu usuário>

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%209.png)

Abra o arquivo com algum editor de texto e cole o tema desejado. </br>
Segue algumas sugestões de temas.

```powershell
eval "$(oh-my-posh --init --shell bash --config ~/scoop/apps/oh-my-posh/current/themes/larserikfinholt.omp.json)"
# eval "$(oh-my-posh --init --shell bash --config ~/scoop/apps/oh-my-posh/current/themes/dracula.omp.json)"
# eval "$(oh-my-posh --init --shell bash --config ~/scoop/apps/oh-my-posh/current/themes/night-owl.omp.json)"
# eval "$(oh-my-posh --init --shell bash --config ~/scoop/apps/oh-my-posh/current/themes/gruvbox.omp.json)"
```

Para visualizar o novo tema abra uma nova aba. </br>
Reinicie o terminal se necessário.

![Untitled](https://github.com/renan-tsx/custom-terminal-windows/blob/1d1f1a3ec9f9386887e00067f5c778db5eb770cc/Untitled%2010.png)

Acesse para outros temas

[Themes | Oh My Posh](https://ohmyposh.dev/docs/themes)

<a id="consideracoes"></a>
# Considerações

Ajude a compartilhar essa postagem.

Siga o repositório, compartilhe.

<a id="notion"></a>
# Tutorial Notion

Entre no link para ver o tutorial no formato Notion

[Notion](https://renanmms.notion.site/custom-terminal-windows-60ffe2852d474121b2a3ad90b00735f5)

