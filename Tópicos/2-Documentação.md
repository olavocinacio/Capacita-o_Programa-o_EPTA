 cPor que documentação é importante?
=

O que é markdown e como utilizar?
=
markdownguide.org/getting-started/

https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown#open


Headers
=
```markdown
Título
=

Subtítulo
-

# Título 1 <h1> Subtítulo
## Título 2 <h2>
### Título 3 <h3>
#### Título 4 <h4>
##### Título 5 <h5>
###### Título 6 <h6>

# Alternative heading
```

Heading
=

Sub-título
-
# Título 1
## Título 2 <h2> 
### Título 3 <h3>
#### Título 4 <h4>
##### Título 5 <h5>
###### Título 6 <h6>

# Alternative heading

De onde surgem esses "h"? HTML e como podemos usar ele em documentação

Parágrafos separados por uma linha em branco

Dois espaços no fim de uma linha produzem uma quebra de linha  
teste

Atributos de texto: _itálico_, **negrito**, `monospace`

```markdown
_itálico_
**negrito**
`monospace`
```

Régua horizontal:

---

```markdown

```

Listas:
1. Frutas
    * maçã
    * banana
2. Vegetais
    - cenoura
    - brócolis

Assim se adiciona um link: [google](htt´://google.com)

![Image](../images/teste.png "icon")

> Criando um bloco de citações
>
> Múltiplos parágrafos

Aqui já acabou (pulando duas linhas)


A maior parte de comandos <abbr title="Hypertext Markup Language">HTML</abbr> é suportado

``` js
//Criando um bloco de código:
function teste(){
    return "Olá";
}
```

Criando tabelas
=


Criando uma boa documentação
=
---

Agora que você sabe usar markdown, a linguagem oficial da documentação no github, vamos aprender os principais pilares para escrevermos uma bela documentação

Por que você deve documentar?

Onde editar markdown:
- vs code
- github
- dillinger.io
