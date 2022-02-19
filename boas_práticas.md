
Como escrever melhores código (Boas práticas)
=

Como você deve ter percebido durante o capítulo anterior, existem várias formas de fazer a mesma coisa. E nós, programadores, temos total liberdade para criarmos um código da forma que quisermos. Mas é importante também pensarmos que em algum momento precisaremos revisitar esse código (ou mostrá-lo a outra pessoa), e para que todos entendam o que está acontecendo, existem algumas convenções importantes de serem consideradas, de forma a tornar o seu código mais legível e produtivo. 

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
