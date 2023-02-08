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
 - **int**: número inteiro (32 bits/ 4 bytes)
 - **long**: número inteiros longos maiores que o int (64 bits/ 8 bytes)
 - **float**: número real com até 6 dígitos (32 bits/4 bytes)
 - **double**: número real com mais dígitos do que um float (64 bits/8 bytes)
 - **string**: uma linha de caracteres
  
Na biblioteca CS50 tem funções correspondentes para obter entrada de vários tipos: `get_char`, `get_int`, `get_long`, `get_float`, `get_double`, `get_string`.

  
Para a função printf, também, existem diferentes marcadores de posição para cada tipo:

- **%c**: para char
- **%i**: para int
- **%li**: para long
- **%f**: para floats e double
- **%s**: para string

### Operadores:

`+`  `-`  `*` `/` `%` (para calcular o resto)

### Açúcar sintático:

São como expressões abreviadas com a mesma funcionalidade. 
Como exemplo abaixo, a declaração da variável contador que se somará mais 1.

`int numero = 0 `  // declaração de variável do tipo int 

`contador = contador + 1` é o mesmo que `contador += 1" ` que é o mesmo que ` contador++ ` 






