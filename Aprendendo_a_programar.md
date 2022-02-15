O que é uma linguagem de programação?
=

Os computadores têm fama de serem muito "inteligentes", mas isso é um mito. Na realidade, eles são só muito obedientes, e precisam que você diga passo a passo (em mínimos detalhes) o que você quer fazer. Sendo assim, você trabalhará com algoritmos, que funcionarão como uma receita de bolo que ele deverá seguir. Mas como já dito, o computador é burrinho, e não entende nossa linguagem. 

A "língua" que os computadores falam é binário (esse sistema recebe esse nome pois só possui duas possíveis entradas, 0 ou 1), provavelmente, nesse momento você deve estar pensando que não seria muito agradável passar um bom tempo contando quantos 0 em sequência você deve digitar até o próximo um, só pra fazer algo simples, como uma soma. E realmente não era uma experiência muito agradável, pra você ter noção, esse é o código escrito para lançamento do foguete Apollo (naquela época, as instruções eram marcadas em papel, com ou sem furo - 0 e 1). 

Para entender um pouco melhor esse processo assista ao vídeo [How do computers read code?](https://www.youtube.com/watch?v=QXjU9qTsYCc)

Sendo assim, foram criadas novas linguagens para dizer ao computador o que fazer, algo mais próximo da linguagem humana, que seria futuramente "traduzida" para a linguagem de máquina. A primeira linguagem inventada (que foi comercializada) foi o Assembly, em 1947, por Kathleen Booth. Aqui está uma comparação entre um código assembly e um código binário que fazem a mesma coisa, a soma entre dois valores:


Apesar de ser mais fácil que escrever um código direto em binário, concorda que ainda é muito complexo fazer as coisas em assembly? A galera daquela época também achava, e foi assim que a história se repetiu, e foram criadas novas linguagens, baseadas diretamente em binário, ou dessa vez baseando-se em assembly, como é o caso da linguagem que teremos foco a partir de agora, a Linguagem C, criada em 1972, por Dennis Ritchie

C
=

C é uma linguagem de uso muito amplo, e super consolidada no mercado (tendo em vista que tem 50 anos de idade e continua sendo usada em sistemas modernos). A linguagem C recebeu durante toda sua vida, algumas atualizações e também serviu de base para "novas" linguagens (C++ e C#), com implementação de novos conceitos e funções. Novas entre aspas pois essas podem ser interpretadas como um super pacote da linguagem C, como se ela tivesse recebido um buff, mas mantido sua essência.  Um código escrito em C, por exemplo, é facilmente adaptado para C++ ou C#, tendo em vista que elas compartilham quase toda a mesma sintaxe e semântica (Apesar disso, caso você trabalhe com alguma dessas linguagens algum dia, não se prenda a programar como faria em C e explore o potencial de cada uma, pois se não trouxessem melhoras significativas, nem teriam sido inventadas). Além dessas duas, temos os exemplos de Python e Java que são 100% diferentes de C, mas que foram contruídas baseando-se nessa linguagem, tendo portanto alguns elementos semelhantes, que fazem com que, caso você saiba C, será mais fácil de estudar essas novas linguagens.

Figura de linguagens mais populares

Dentre as aplicações de C e suas variantes, encontram-se:
- Sistemas opercionais (Todos os windows, MAC OS X, Chrome OS, entre outros)
- Navegadores web (Chrome, Firefox, Safari, Opera)
- Office (Microsoft office, libreOffice, Corel Office)
- Clientes de e-mail (Outlook, IBM lotus notes, Mozilla thunderbird)
- Players de mídia (Windows media player, VLC Media player, Software Apple Ipod)
- Bancos de dados (Oracle, MySQL, Microsoft SQL Server, MongoDB, )
- Jogos (GTA, DOOM 3, Counter Strike, Diablo 1 e 2)
- Game engines (Unity, Unreal, Godot)
- Aplicativos de edição (Photoshop, Blender, OBS, Acrobat Reader)
- Outras lingaugens e ferramentas de programação (JavaScript, node.js, TensorFLow, Visual studio)
- **Sistemas embarcados** 

Para a área de embarcados (que é a que nos interessa aqui), a lingugagem C é, sem discussões, a linguagem com maior utilização. Sabendo disso, estudaremos então um pouco sobre como programar nossos sistemas da aviônica usando essa grande aliada. 

Apesar disso tudo, a linguagem C tem sim seus defeitos (como a não implementação do conceito de orientação a objetos; pressupor que o programador sabe o que está fazendo, ocasionando problemas como memory leaks, buffer overruns, segmentation faults) e tem recebido potenciais substitutos muito interessantes, como é o caso do Rust, a maior aposta para substituir C na área de embarcados. Mas deixemos isso como tarefa de casa para um futuro próximo...

Estrutura de um código C
-

``` C
//Isso é um comentário. Tudo que vier precedido de duas barras não é lido pelo computador na hora da execução
//Isso ajuda na hora de documentar o código, deixando informações importantes ao leitor do mesmo

#include <stdio.h> //Chamada da biblioteca standard

//Aqui temos a função main, que será onde o código iniciará
int main(){ 
    //Aqui entra o seu código
    return 0; //Aqui encontra-se o retorno da função. No caso, estamos retornando um valor vazio no main, para indicar que o programa deve ser encerrado
}
```

É importante lembrar que o código será lido de cima para baixo, da esquerda para direita, linha por linha, executando os comandos passados em cada uma dessas.

Além disso, é importante que você **NÃO ESQUEÇA O PONTO E VÍRGULA NO FINAL**. Mas não adianta falar isso agora, é algo que você só se acostumará depois de muitas vezes passar horas procurando um erro no código e descobrir que era um ponto e virgula faltando em uma das linhas

Olá mundo
-

Como de costume, vamos então fazer nosso primeiro código em C, para nos dar boas vindas à linguagem.

``` C
#include <stdio.h>

int main(){
    printf("Olá mundo"); //A função printf retorna a mensagem entre parenteses no console
    return 0;
}
```

Variáveis
-

Vamos declarar agora algumas variáveis e estudar seus diferentes tipos

``` C
#include <stdio.h>

int main(){
    int inteiro = 3;
    float racional = 3.5;
    char caracter[1] = "a"; //Entre parêntes é o tamanho do texto
    char frase[9] = "Olá mundo";
    bool booleano = true;
    return 0;
}
```

Cada variável possui um identificador que usaremos para printarmos elas no console, usando o "printf":

``` C
printf("Inteiro : %i", inteiro);
printf("Float: %f", racional);
printf("Char: %s", caracter);
printf("Char: %s", frase);
printf("Bool: %d", booleano); //Printa 1 se for verdadeiro, e 0 se for falso
```

É claro que você não precisa printar com esse exato mesmo texto, mas você deve referenciar o tipo certo da variável com o "%" e depois de fechar a string, colocar uma vírgula e a variável referente.

Para printarmos mais de uma variável, basta repetir o processo:
``` C
printf("O inteiro vale %i e o float vale %f", inteiro, racional);
```

Operadores 
-

Operadores matemáticos
-

Símbolo   | Significados 
--------- | ------------  
\- | Subtração 
\+ | Adição 
/ |Divisão 
\* | Multiplicação
\** | Exponenciação
% | Resto da divisão (módulo)

Operadores relacionais
-

Símbolo   | Significados 
--------- | ------------ 
== | igual
!= | diferente
< | menor
\> | maior
\<= | menor ou igual
\>= | maior ou igual



Seguem exemplos de utilização de cada um desses:

```C
int a = 10;
int b = 3;
int c = 2;
int soma = a+b; //Retorna 13
int sub = a-b; //Retorna 7
int div = a/c; //Retorna 5
int mult = a*b; //Retorna 30
int expo = a**b; //Retorna 1000
int resto = a%b; //Retorna 1
bool maior = (a>b); //Retorna true
bool menor = (a<b); //Retorna false
bool menor_igual = (a<=b); //Retorna false 
bool maior_igual = (a>=b); //Retorna true
bool igual = (a==b); //Retorna false
bool diferente = (a!=b); //Retorna true
```

static, volatile, const


Condicionais
-

Existem algumas situações em que você vai optar pelo que quer fazer, baseando-se em uma outra informação, como por exemplo uma checagem de tipo, uma comparação entre variáveis ou o resultado de uma operação.

Vamos para o código, para entender exatamente como isso funciona

```C
#include <stdio.h>

int main(){
    int a = 10;
    int b = 2;
    if(a > b){ //Se o que está entre parênteses for verdade, o que está dentro das chaves é feito
        printf("A variável a é maior do que b");
    } else{ //Se não, essa nova chave é realizada
        printf("A variável a é menor do que a");
    }
    return 0;
}
```

Consegue perceber a relação? Lembre sempre que o "if" é um "se" que vai validar a operação entre parênteses, e o "else" é um "se não", o qual o programa só lerá o que está entre chaves, caso o "if" não tenha obtido um retorno verdadeiro.

Além disso, existem casos em que você pode fazer várias operações, e nesse caso, podemos fazer dois tipos de checagem, uma com "else if" (é um "se não" que também tenta validadar uma operação, como no "if", ao invés de ser o último caso):

```C
#include <stdio.h>

int main(){
    int a = 2;
    if(a == 0){ 
        printf("a variável é 0");
    } elif (a == 1){
        print("a variável é 1");
    } else{
        printf("a variável é maior que 1");
    }
    return 0;
}
```

Mas para casos grandes, em que você quer fazer várias checagens comparativas de valor para uma mesma variável, o "else if" não é ideal, pois em um caso que chegue no else, o computador terá perdido muito tempo tentando validar todas as condições impostas. Nesses casos, é mais interessante que utilizemos uma estrutura chamada "switch":

```C
#include <stdio.h>

int main(){
    int a = 2;
    switch(a){
        case 0:
            printf("a variável é 0");
            break; //para a checagem
        case 1:
            printf("a variável é 1");
            break;
        case 2:
            printf("a variável é 2");
            break;
        default:
            printf("a variável é maior que 2"); //equivalente ao else (um caso geral em que nenhuma das condições foi verdadeira)
            break;
    }
}
```

Criando funções
-

Existem alguns momentos em que você terá que repetir várias operações de um mesmo tipo em sequência, para economizar o trabalho de copiar e colar repetidas vezes um bloco gigante de texto, você pode criar um bloco de código chamado função.

Aqui está um exemplo prático:

```C
#include <stdio.h>

int main(){
    int a = 2;
    int b = 3;
    int c = 4;
    int d = 5;
    int cinco = soma(a,b); //O retorno da soma de a+b é salvo na variável cinco (que possui esse nome de forma bem clara a respeito do resultado nesse caso), e é printado "resultado = 5" no console
    int seis = soma(a,c);
    int sete = soma(a,d);
    return 0;
}

int soma(int a, int b){
    int resultado;
    resultado = a+b;
    printf("resultado = %i \n", resultado);
    return resultado;
}
```

Percebe como fica muito mais organizado e legível assim do que se fizessemos da seguinte forma?

```C
#include <stdio.h>

int main(){
    int a = 2;
    int b = 3;
    int c = 4;
    int d = 5;
    cinco = a+b;
    printf("resultado = %i \n", resultado);
    seis = a+c;
    printf("resultado = %i \n", resultado);
    sete = a+d;
    printf("resultado = %i \n", resultado);
    return 0;
}
```

Talvez você não tenha notado a grandiosidade das funções, devido à baixa complexidade da operação que estamos realizando, mas imagine um caso em que seja feita a aquisição de dados de um sensor, por exemplo. Seria inviável ter esse código escritos repetidas vezes. 

Loops
-

Pensando novamente em otimização, e não repetição, o que faríamos pra executar a função de soma criada no esquema anterior n vezes??

É pensando nesses casos de iteração que existem os loops (ou laços), que sãe estruturas que se repetem de acordo com um parâmetro de saída do mesmo.

Em C existem três principais tipos de laço, são eles

**While:**

Checa a condição antes mesmo de começar, podendo nem entrar no loop caso ela não seja atendida.

```C
#include <stdio.h>

int main(){
    int j = 0;
    while(j < 99){ //Enquanto isso for verdadeiro, o que estiver dentro do loop é executado
        printf("x = %i", aux);
        j++;
    }
    return 0;
}
```

**Do While:**

Garante que o código seja executado pelo menos uma vez, já que a condição só é checada no final.

```C
#include <stdio.h>

int main(){
    int j = 0;
    do{
        printf("x = %i", aux);
        j++;
    } while(j < 99) //Enquanto isso for verdadeiro, o que estiver dentro do loop é executado
    return 0;
}
```

**For:**

Repete n vezes o código, independente de uma condição inicial. Ele sempre será executado ao chegar nele

```C
#include <stdio.h>

int main(){
    for(int aux = 0; aux < 99; aux++){ //for(valor inicial; condição de parada; incremento)
        printf("x = %i", aux); //Tudo que esta entre as chaves será executado em loop
    }
    return 0;
}
```

Nesse caso, implementamos o mesmo código com valor inicial em 0, incremento de 1 e parada em 99, mas como visto nas observações de cada estrutura, elas possuem aplicações específicas de utilização. Você deve ser inteligente para identificar qual a melhor estrutura de repetição de acordo com a sua situação de uso.

Structures
-

Em C não temos implementado o conceito de programação orientada a objetos (POO é algo muito importante que trataremos na seção de boas práticas), mas possui algo que lembra (em relação a variáveis) a declaração de um objeto. Essas são as structures, que definem um conjunto de variáveis de diferentes tipos ligadas entre si.

Vamos dar um exemplo prático:

```C
struct carro{
    char modelo[20];
    char marca[20];
    int ano;
    char dono[20];
}
```

Essa é a struct carro, que contem as quatro variáveis, de modelo, marca, ano e dono. Vamos fazer um exemplo agora de como declarar esse valores:

```C
struct carro meu_carro; //Criando a variável meu_carro do tipo carro (definida na struct)

meu_carro.modelo = "Gol";
meu_carro.marca = "Volkswagen";
meu_carro.ano = 1994;
meu_carro.dono = "Daniel";
```

Agora temos a variável "meu_carro", com suas "subariáveis" definidas, e que podem ser acessadas a qualquer momento. Esse conceito é muito útil quando você precisa organizar elementos relacionados a variás variáveis iguais, pois você tem um grau a mais de abstração.

Listas
-

Podemos também criar listas com várias variáveis do mesmo tipo. Essa estrutura é chamada array, e ela é declarada da seguinte forma:

```C
int numeros_primos[5] = {1,2,3,5,7};
char dias da semana[7][10] = ["segunda", "terça", "quarta", "quinta", "sexta", "sábado", "domingo"]; //A primeira dimensão indica a quantidade de termos na lista (7 termos), e o segundo é o tamanho dos chars de cada item (máximo de 10 caracteres)
```

No caso da lista de chars que fizemos, ela funciona como uma matriz (uma lista de duas dimensões). Isso pode ser feito também com outros tipos de variável, e no lugar de cada item da lista principal, teremos uma sublista:

```C
int numeros[4][3] = {{1,2,3},{4,5,6},{7,8,9}};
```

E para acessar os termos de cada uma dessas listas, basta chamar o nome da lista com o termo desejado entre os colchetes.

```C
printf("O primeiro número primo é: %i", numeros_primos[0]); //É importante perceber que a contagem dos index (posição) começa em 0, e não no 1
printf("Hoje é %s", dias_da_semana[6]); //Logo, o último termo será representado pelo tamanho da lista menos um. Nesse caso, printamos "Hoje é domingo"
printf("Cinco: %i", numeros[1][1]);

```

Ponteiros
-

Um ponteiro guarda um endereço de memória. Utilizamos isso para acompanhar e manipular o alocamento de variáveis dentro de um código.

Exemplo mais simples:

```C
int numero = 5;
int *posicao = &numero; //O ponteiro posição aponta para o endereço de memória em que está alocada a variável numero
```

Isso é importante para técnicas como a alocação dinâmica e a criação de listas encadeadas.

Sobre a alocação dinâmica:

http://linguagemc.com.br/alocacao-dinamica-de-memoria-em-c/


Sobre listas encadeadas:

https://www.ime.usp.br/~pf/algoritmos/aulas/lista.html



Bibliotecas e arquivos externos
-

Uma biblioteca é um arquivo com porções de código que já foram escritos e que por muitas vezes possuem funções extremamente úteis. Temos que agradecer muito aos abençoados que criam bibliotecas com funções que nos tomariam 100 linhas e muita dor de cabeça se fóssemos escrevê-las. Mas como já fizeram isso, tudo que precisamos fazer é importar esse pacotes e utilizar dessas funções.

Você, sem perceber, está fazendo isso desde seu primeiro código. A biblioteca "stdio.h" é uma das mais utilizadas, devido ao caráter fundamental de suas funções (como a "printf", por exemplo). Como dito, você já sabe então que a importação de uma biblioteca se dá da seguinte forma:

``` C
#include <stdio.h>
```

Além da "stdio", existem variás outras bibliotecas que serão grandes aliadas durante a sua vida de programação, e você irá as decobrindo de acordo com sua necessidade. Mas para não te deixar perdido agora no começo, deixarei aqui uma lista com algumas bibliotecas interessantes e suas utilizações:

1. **math.h**
    - Biblioteca com várias funções matemáticas prontas, como média, raiz quadrada, entre outras
2. **string.h**
    - Manipulação de strings (conjuntos de char)
3. **alloc.h**
    - Função para gerenciamento da memória
4. **stdlib.h**
    - Funções de uso geral, como conversão de tipos, organização de arrays, etc

Além disso, você pode organizar seu código em vários arquivos (o que é extremamente interessante e será citado na seção de boas práticas), e até mesmo criar suas próprias bibliotcas.

Nesses casos, você fara a importação do arquivo existente na mesma pasta de origem do seu arquivo atual da seguinte forma:

``` C
#include "my_lib.h"
```

Nesse caso, seu único arquivo ".c" será o principal,e os demais funcionaram como bibliotecas de onde você importará funções, variáveis, e qualquer outra coisa que quiser, logo, devem receber a terminação ".h"

Exercícios
-

Bom, agora você já tem uma boa base em relação à sintaxe de C e deve estar apto a criar seus próprios códigos. Para confirmar isso, resolva os seguinte exercícios, e envie para "olavo1611@gmail.com" até o dia 05/02 (você será avaliado). Caso tenha dúvidas, não se acanhe em me chamar em "16996426659".

1. Crie um código em C que printe n números da sequência fibonacci (o primeiro deverá sempre ser o número 1,e número n de repetições deve ser escolhido pelo usuário)

2. Crie um código em C que leia os valores de um array de 10 posições, e calcule a média, a moda e a mediana de tais valores (cada um desses resultados deve ser retornado por uma função responsável por realizar as operações necessárias para encontrá-lo)

3. Crie um código em C para cadastro de automóveis, utilizando structures. (O usuário deve entrar com o modelo, ano e cor do carro, e esses valores devem ser adicionados a uma lista salva em um arquivo txt)

4. Escreva um programa que declare um inteiro, um real e um char, e ponteiros para inteiro, real, e char. Associe as variaveis aos ponteiros (use &). Modifique os valores de cada variável usando os ponteiros. Imprima os valores das variáveis antes e após a modificação.

Boas práticas
=

Como você deve ter percebido durante

Nomes
-

Nomes de arquivos, variáveis, funções

Comentários
-

Documentação
-

Programação orientada a objetos
-

1) Faça sempre um comentário no início do código com as seguintes informações:

Nome do programa
Objetivo do programa
Nome do programador
Data de criação

Identação
-

Design patterns
-

----

6) Declare as variáveis logo após o título da rotina. Não declare as variáveis “soltas” no meio do código da função.
Organize seu código, sempre declarando as variáveis logo após o título da rotina e em seguida inicialize-as.

7) Seja sempre claro e objetivo. Não convém usar comandos muito rebuscados só porque você aprendeu uma forma interessante de fazer uma determinada operação, mas que ninguém (ou quase ninguém) usa. Pense que outra pessoa pode ter que dar manutenção no código e ficar confusa com um comando exótico.

8 ) Procure não fazer rotinas excessivamente extensas. Quanto menor e mais objetiva for a rotina, melhor.

9) Evite repetições de código. Caso um trecho de código apareça várias vezes no programa, construa uma rotina e chame-a quando for necessário. Quanto menor for o tamanho da rotina, normalmente é mais fácil para depurar.

10) Faça o planejamento. Tenha sempre qual é seu objetivo em mente. Não saia escrevendo código sem saber direito o que vai fazer. Elabore um diagrama no mínimo. Acredite, isso ajuda muuuito.

11) Evite a utilização de Números Mágicos:
Os chamados números mágicos são valores que aparecem no código e são usados como constantes, embora não tenham sido declarados como tal. Ao invés de usar o número utilize uma constante previamente declarada com #define.
(pi, por exemplo. O nº de euler, etc...)

12) Utilize o espaçamento de forma a tornar o código mais legível.

13) Declare as constantes no início do código e nunca no meio do mesmo.

14) Utilize sempre letras maiusculas para nomear as constantes em linguagem C.

15) Utilize sempre { } mesmo que seja para apenas um comando dentro do bloco.

16) Não exagere nos comentários. Comandos óbvios não precisam ser comentados.

17) Explique fórmulas complexas e passos complicados de um determinado algoritmo. Nesses casos, um comentário explicativo torna-se obrigatório a fim de que a manutenção do código possa ser feita com menos esforço.

18) Escreva os comentários necessários na medida que for escrevendo o código. Não escreva o código e deixe para comentar depois. É bem mais
fácil elaborar os comentários quando você ainda se lembra dos detalhes.
