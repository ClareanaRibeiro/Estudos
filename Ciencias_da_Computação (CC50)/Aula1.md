# Aula 1: Linguagem C - Professor: David J. Malan

Para salvar arquivos na linguagem C, por padrão o final é `.c `(ex: nomeDoArquivo.c)

As diversas linguagens de progamação (JavaScript, Java, C, Phython, etc) precisam ser convertidas em binário (padrões de 0 e 1) para que os computadores entendam o código e o executem. 

**Compilador** - é um programa que faz essa conversão de linguagem de programação qlquer que seja (código fonte) para padrões de 0 e 1 (binário ou código de máquina).

A equipe do curso CC50 disponibilizou uma ferramenta chamada CS50 IDE, um ambiente de programação baseado na web que usa seu próprio servidor. (ide.cs50.io)
Já tem instalado no CS50 IDE, um compilador.

Na linguagem C essa compilação não é automática como em outras linguagens, e deve ser feita através do terminal.

**COMANDO NO TERMINAL PARA COMPILAR:**  `make nomeDoArquivo`

OBS: Não utiliza o `.c` no final, apenas o nome do arquivo puro.
OBS: Esse comando irá criar uma espécie de cópia do arquivo que receberá automaticamente o mesmo nome do arquivo sem o `.c`, só que agora compilado, ou seja, em binário, pronto para ser executado.

**COMANDO NO TERMINAL PARA EXECUTAR:**  `./nomeDoArquivo`

**FUNÇÕES** - São como miniprogramas, como uma ação ou um verbo, um bloco de instruções para executar determinada ação.
As funções podem receber argumentos, também chamados de parâmetros que ficam no código entre ( ). 
As funções podem devolver um resultado, chamado de retorno. O ideal é que esteja armazenado em uma variável para ser que possa ser utilizada posteriormente no código.

**BIBLIOTECA** - é um código que já foi escrito anteriormente por alguém para facilitar a realização de coisas simples. São como códigos pré definidos para serem reutilizados para facilitar.
(Ex: get_string é uma função já criada e pre definida da biblioteca CS50 que recebe algum input e o usa como prompt para o usuário, que permite que um input aceite o conteúdo a ser preenchido pelo usuário como uma string) 

Na criação de uma variável em C, deve-se dizer qual tipo de variável é. 
Ex: criação de uma variável chamada answer que é do tipo string: 

 `string answer = get_string ("What's you name?");`

Quando escrevemos o código atribuindo `=` o valor a uma variável, o computador vai executar primeiro o lado direito do `=` para depois executar o lado esquerdo que é armazenar o resultado na variável answer.

**%s** - é o formato de código para receber um valor. 

` printf ("hello, %s", answer); `

Significa apenas que queremos que a função printf substitua uma variável onde está o marcador %s. E a variável que queremos usar é answer, que passamos para printf como outro argumento, separado do primeiro por uma vírgula.


**Os arquivos de cabeçalho** terminam com `.h`. E se referem a algum outro conjunto de código, como uma biblioteca, que podemos usar em nosso programa. Nós os incluímos com linhas como `#include <cs50.h> `, por exemplo, para a biblioteca que contém a função get_string ou  `#include <stdio.h> `, para a biblioteca que contém a função printf.

~~~~ 

#include <cs50.h> 
#include <studio.h>

  int main (void)
  {
    string answer = get_string ("What's your name?);
    printf ("Hello, %s", answer);
  } 
  
~~~~

A parte do código `int main (void)` é um tipo de código base da linguagem C.

Toda vez que for feita uma alteração no código, não basta apenas salvar, deve-se sempre compilar o arquivo com o comando no terminal ` make nomeDoArquivo ` para depois executar ` ./nomeDoArquivo ` 

### Principais comandos no terminal:

- Para visualizar arquivos ou pastas dentro da pasta (diretório) atual: ` ls `

- Para exluir um arquivo: ` rm nomeDoArquivo `  - Depois confirmar a exclusão com yes ou y

- Para renomear um arquivo: ` mv nomeDoArquivo.c  novoNome.c `

- Para criar uma pasta (diretório): ` mkdir nomeDaPasta `

- Para mover um arquivo para uma pasta: ` mv nomeDoArquivo.c nomePasta/ `

- Para entrar em uma pasta (diretório): ` cd nomeDaPasta `
  Ficará dessa forma no terminal em azul: `  ~/NomeDaPasta/ $ `

- Para acessar o diretório principal ou pai (como se fosse a pasta Meus Documentos): ` cd .. `

- Para mover um arquivo para diretório principal: ` mv nomeDoArquivo.c .. `

- Para excluir uma pasta (diretório): ` rmdir nomePasta/ `

DICA: Quando o arquivo é executável, ou seja, depois que foi compilado e está em binário, pronto para ser executado, o arquivo aparece na cor verde no terminal seguido de um * 

### Tipos de dados:

Cada um desses tipos de dados tem um número especicífico de bits.

 - **bool**: uma expressão booleana que retorna verdadeiro ou falso
 - **char**: um único caractere ASCII como a ou 2
 - **string**: uma linha de caracteres
 - **int**: número inteiro (32 bits/ 4 bytes)
 - **long**: número inteiros longos maiores que o int (64 bits/ 8 bytes)
 - **float**: número real com até 6 dígitos (32 bits/4 bytes)
 - **double**: número real com mais dígitos do que um float (64 bits/8 bytes)
   
Na biblioteca CS50 tem funções correspondentes para obter entrada de vários tipos: `get_char`, `get_int`, `get_long`, `get_float`, `get_double`, `get_string`.

  
Para a função printf, também, existem diferentes marcadores de posição para cada tipo:

- **%c**: para char
- **%s**: para string
- **%i**: para int
- **%li**: para long
- **%f**: para floats e double

### Operadores:

`+`  `-`  `*` `/` `%` (para calcular o resto)

### Açúcar sintático:

São como expressões abreviadas com a mesma funcionalidade. 
Por exemplo, a declaração da variável contador que se somará mais 1.

`int contador = 0 `  // declaração de variável do tipo int 

`contador = contador + 1` é o mesmo que `contador += 1 ` que é o mesmo que ` contador++ ` 

### Condições:

- If
- If / else
- If / else if/ else

Segue abaixo exemplo de código a ser analisado:

~~~~

#include <cs50.h>
#include <stdio.h>

int main(void)
{
     // Solicita um caracter para o usuário
     char c = get_char("Você concorda? Digite s para sim ou n para não");

     // Verifica se concordou
     if (c == ‘S’ || c == ‘s’)
     {
         printf(“Concordo.\n”); 
     }
     else if (c == ‘N’ || c == ‘n’)
     {
        printf(“Não concordo..\n”); 
     }
}

~~~~

OBSERVAÇÕES:

* Para comparar dois valores usamos ` == `. O uso de apenas um ` = ` é para atribuição de valor a uma variável.

* Usamos ` || `  para indicar um “ou” lógico, onde qualquer uma das expressões pode ser verdadeira para que a condição seja seguida. Usamos ` && ` para indicar um “e” lógico, onde ambas as condições deveriam ser verdadeiras.

* Em C, deve-se usar aspas simples ` ’  ` para envolver caracteres únicos.

* ` \n ` é usado para pular linha.

### Expressões booleanas e loops (laço de repetição): while, do while  e for

- **while** - é uma estrutura de repetição, ou seja, uma estrutura que usamos para repitir um trecho de código enquanto uma certa condição for verdadeira.

- **do while** - parecida com while, a diferença é que executa-se ao menos uma vez o bloco de código e só depois confirma se a condição se cumpre.

~~~

int i = 0;
while (i < 50)
{
    printf(“Oi mundo!\n”); 
    i++;
}

~~~


Porém esse caso o código poderia ser melhorado usando o laço de repetição **for** 


~~~ 

int i = 0;
for (int i = 0; i < 50; i++)
{
    printf(“Oi mundo!\n”); 
}

~~~

- **for** - O uso do loop do tipo for é mais recomendado, uma vez que tudo relacionado ao loop está na mesma linha, e somente o código que realmente desejamos executar multiplas vezes está dentro do loop.
Sua estrutura ` for (int i = 0; i < 50; i++) ` consiste em: declaração da variável, condição e incremento.

Note que condições do tipo if e loops do tipo for, não colocamos um ` ; ` no final. É assim que a linguagem C foi projetada e uma regra geral. Apenas as linhas para ações ou verbos tem `; ` no final como se fosse o fim de um raciocínio.


Vamos analisar o código abaixo:

~~~

#include <cs50.h>
#include <stdio.h>

int get_positive_int(void);

int main(void)
{
     int i = get_positive_int();
     printf(“%i\n”);
}

// Solicita um número inteiro positivo ao usuário
int get_positive_int(void)
{
     int n;
     do
     {
          n = get_int(“Número positivo: \n”); 
	 }
     while(n < 1);
     return n;
}

~~~


OBSERVAÇÕES:

* Convencionalmente, a função principal(main) deve ser a primeira do programa, então precisamos declarar a função `get_positive_int `primeiro com um protótipo, antes de usá-la, e depois definí-la. O compilador lê o código de cima para baixo, então ele precisa saber que a função existirá posteriormente no arquivo. 

* Precisamos declarar a variável ` n ` fora do loop do-while, pois a usaremos após o término do loop. O **escopo** de uma variável se refere ao contexto, ou linhas de código, dentro do qual ela existe. Por exemplo, se uma variável é declarada dentro de uma função { }, ela será válida apenas para aquela função, não podendo ser reaproveitada posteriormente no código. Pode-se declarar a variável inicialmente sem atribuir valor a ela e só depois o valor ser atribuido quando for pertinente.

* Na biblioteca do cs50, possui a função get_int mas o intuito é coletar do usuário apenas números pares, por isso a criação da função get_positive_int.`

* Com um loop do-while, o programa fará algo primeiro, depois verificará alguma condição e repetirá enquanto a condição for verdadeira. Nesse caso, primeiro vai pedir o número ao usuário para depois verificar a condição.

* Observe que a função `get_positive_int `agora começa com ` int `, indicando que ela tem um valor de retorno do tipo int que foi armazenada na variável `n `e poderá ser utilizada posteriormente no código.


### Memória, Imprecisão e Bug do milênio

Note no código abaixo que foi especificado para 50 o número de casas decimais com  ` % .50f ` a ser printado do resultado da divisão entre x e y, supondo que usuário preencheu como 1 e 10 respectivamente.

~~~

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    float x = get_float("x: ");
    float y = get_float("y: ");
    	
    printf(“%.50f\n", x / y;); 
}

~~~ 

Resultado do que será impresso: 

`0,10000000149011611938476562500000000000000000000000 `

Esse resultado errado ocorre porque não temos bits suficientes para armazenar esse valor. 
Com um número finito de bits para um float, não podemos representar todos os números reais, então o computador tenta fazer uma aproximação mais próximo que puder do valor. Isso se chama **imprecisão de vírgula flutuante**.

**overflow (“vazamento”) de inteiro** - Em um computador pessoal, por exemplo, o maior inteiro que é possível representar em sua memória é 4.294.967.295. Caso alguma conta executada pelo computador dê um resultado acima desse número, ocorrerá o que chamamos de overflow, que é quando o computador faz uma conta e o resultado não pode ser representado, por ser maior do que o valor máximo permitido (em inglês overflow significa trasbordar).

**BUG do milênio ou Y2K**, ocorreu porque os computadores foram programados para armazenar anos com apenas 2 digitos. E na passagem do ano de 99 para 2000, os programas tiveram que armazenar apenas 00, levando a confusão entre os anos 1900 e 2000.


