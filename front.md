---
title: "Front-end"
layout: default
---

# Front-end
## Sumário

1. [O que é Front-end?](#1-front-end)
2. [HTML](#2-html-hypertext-markup-language)
- [O que é?](#2-html-hypertext-markup-language)
- [Tags Estruturais](#21-tags-estruturais)
  - [Doctype](#211-doctype)
  - [Title](#212-title)
  - [Body](#213-body)
  - [Organizando](#214-organizando-o-código)
- [Tags de Texto](#22-tags-de-texto)
  - [Cabeçalho](#221-cabeçalho)
  - [Itálico](#222-itálico)
  - [Negrito](#223-negrito)
  - [Sublinhado](#224-sublinhado)
  - [Tachado](#225-tachado)

# 1. Front-end

O Front-end é a parte do desenvolvimento de software responsável pela interface com a qual o usuário interage diretamente em uma aplicação. Ele envolve a criação de elementos visuais, interativos e estruturais que são exibidos no navegador ou na interface de um sistema.

O objetivo do Front-end é garantir que o usuário consiga utilizar a aplicação de forma clara, eficiente e agradável.

## 1.1 Tecnologias principais

O desenvolvimento Front-end na web é baseado principalmente em três tecnologias:

| Tecnologia | Função |
|-----------|------|
| HTML | Estrutura o conteúdo da página |
| CSS | Define o estilo e aparência |
| JavaScript | Adiciona interatividade e comportamento |

# 2. HTML (HyperText Markup Language)
> O HyperText Markup Language é uma linguagem de marcação para estruturar um site utilizando as tags, que são lidas pelo navegador para visualizar o site. Essas tags marcam a função que o navegador precisa rodar para mostrar o site.

## 2.1 Tags Estruturais
### 2.1.1 Doctype
`<!DOCTYPE HTML>`: A tag doctype, direciona o código para o tipo de documento que queremos formar, justamente, o Document type. Quando declaramos que é um html estamos focando em websites como qualquer um que vemos na internet, independente de qual você escolha muito provavelmente ele está rodando com html, css e javascript.

Existem outros tipos de doctype, porém essa tag é a padrão para o html5 e sites atuais e será sempre utilizada. É obrigatório o uso dessa tag no início do um código html antes de qualquer outra coisa. Além disso, vale ressaltar que as tags em html são case-sensitive, então se você iniciar uma tag com letra maiúscula, sua tag de fechamento precisa
também ser maiúscula, é recomendado escolher entre maiúsculo ou minúsculo para utilizar no código inteiro.

### 2.1.2 Title
`<title></title>`: Essa tag é utilizada para dar um título ou nome à aba em que será aberto o site e não aparecerá no corpo da página. Por exemplo, o título de uma aba vazia do Google é “nova guia”.

### 2.1.3 Body
`[<body></body>]`: Body é exatamente o corpo do site, sua forma e o que será exposto para o usuário. Tudo dentro da tag body pode ser utilizado e visto por quem abrir o site; seja link, imagem, texto, caixas de texto e outros. Essa tag deve ser fechada quando toda a informação que você quer que seja vista for adicionada dentro de `<body>...</body>`.

### 2.1.4 Organizando o código 
Há uma sequência a ser seguida para fazer o html funcionar: “<!doctype html> -> <html> -> <body> (quaisquer tags que queira adicionar) -> </body> -> </html>” O doctype especifica o formato do texto, o primeiro html o que será utilizado para o site, body o corpo visível do texto, o fechamento do body e o fim do html.

## 2.2. TAGS DE TEXTO
Veremos agora um breve guia do uso dos modificadores de texto (itálico, negrito, sublinhado, tachado), relacionando suas tags com seu significado e uso na língua portuguesa para melhorar a absorção do seu significado e uso na produção de um código em html.

### 2.2.1 Cabeçalho

`[<h1-6></h1-6>]`: Cabeçalhos são textos modificáveis, geralmente servindo para criar títulos e subtítulos na página, variando de tamanho em ordem decrescente de 1, o maior à 6, o menor. Exemplos:

<div style="text-align: center;">
    <h1>H1</h1>
    <h2>H2</h2>
    <h3>H3</h3>
    <h4>H4</h4>
    <h5>H5</h5>
    <h6>H6</h6>
</div>

### 2.2.2 Itálico
`[<i>Texto...</i>]`: O texto em itálico deixa o texto inclinado. O i em `<i>` é exatamente para mencionar o início de um “Italic". Adicionalmente, no português o itálico deve ser usado para destacar palavras estrangeiras (ainda não aportuguesadas), títulos de obras (livros, filmes), nomes científicos (espécies), ênfase em palavras específicas, diálogos internos/pensamentos e termos técnicos.

### 2.2.3 Negrito
`[<b>Texto...</b>]`: O 'b' vem da palavra "bold", do inglês; no brasil sendo traduzida como "negrito". É usado para dar ênfase em palavras. A palavra será destacada entre as outras por sua linha mais larga. É usado para destacar palavras-chave, frases importantes, títulos, subtítulos ou dados numéricos segundo a norma culta brasileira.

### 2.2.4 Sublinhado
`[<u>Texto...</u>]`: O 'u' é referente a "underline" ou sublinhado no português, para efeito de visualização, a palavra em inglês pode ser destrinchada para a tradução literal como 'under' 'Line' ou 'sob a linha', ou seja, todo texto está sob a linha. É usado principalmente para destacar informações cruciais ou indicar hiperlinks clicáveis na
internet.

### 2.2.5 Tachado 
`<s>Texto...</s>`: O 's' vem do termo "strikethrough" sendo um texto riscado por uma linha no centro. Para fins visuals, destrinchamos também a palavra em inglês, na tradução 'ao pé da letra' poderia ser algo parecido com "atacar através" ou apenas "atacar", "perfurar", Utilizaremos o perfurar, imagine a letra sendo atravessada ao ser tachada (é um pouco cruel porém é uma letra e não sente dor.). Sua função é indicar que uma frase ou trecho foi excluído revisado, substituído ou que é menos importante, sem removê-lo completamente do documento.

----

🦉 *Este material faz parte do projeto Arthemis, com foco em aprendizado colaborativo para alunos do Senac.*