# Aula 1: Linguagem C - Professor: David J. Malan

Para salvar arquivos na linguagem C, por padrão o final é .c (ex: nomeDoArquivo.c)

As diversas linguagens de progamação (JavaScript, Java, C, Phython, etc) precisam ser convertidas em binário (padrões de 0 e 1) para que os computadores entendam o código e o executem. 

**Compilador** - é um programa que faz essa conversão de linguagem de programação qlquer que seja (código fonte) para padrões de 0 e 1 (binário ou códigon de máquina).

A equipe do curso CC50 disponibilizou uma ferramenta chamada CS50 IDE, um ambiente de programação baseado na web que usa seu próprio servidor. (ide.cs50.io)
Já tem instalado no CS50 IDE, um compilador.

Na linguagem C essa compilação não é automática como em outras linguagens, e deve ser feita através do terminal.

**COMANDO NO TERMINAL PARA COMPILAR:**  `make nomeDoArquivo`
OBS: Não utiliza o .c no final, apenas o nome do arquivo puro.
OBS: Esse comando irá criar uma espécie de cópia do arquivo que receberá automaticamente o mesmo nome do arquivo sem o .c, só que agora compilado, ou seja, em binário, pronto para ser executado.

**COMANDO NO TERMINAL PARA EXECUTAR:**  `./nomeDoArquivo`

**FUNÇÕES** - São como miniprogramas, como uma ação ou um verbo, um bloco de instruções para executar determinada ação.
As funções podem receber argumentos, também chamados de parâmetros que ficam no código entre (). 
As funções podem devolver um resultado, chamado de retorno. O ideal é que esteja armazenada em uma variável para ser que possa ser utilizada posteriormente no código.

**BIBLIOTECA** - é um código que já foi escrito anteriormente por alguém para facilitar a realização de coisas simples. São como códigos pré definidos para serem reutilizados para facilitar.
(Ex: get_string é uma função já criada e pre definida da biblioteca CS50 que pedirá ao usuário uma string, ou alguma sequência de texto, e a retornará ao nosso programa. get_string recebe algum input e o usa como prompt para o usuário,que permite que um input aceite o conteúdo a ser preenchido pelo usuário como uma string) 

Na criação de uma variável em C, deve-se dizer qual tipo de variável é. (Ex: criação de uma variável chamada answer que é do tipo string:
                             `string aswer = get_string ("What's you name?");`
Quando escrevemos o código atribuindo `=` o valor a uma variável, o computador vai executar primeiro o lado direito do `=` para depois executar o lado esquerdo que é armazenar o resultado na variável answer.

**%s** - é o formato de código para receber um valor. ` printf ("hello, %s", aswer); `
significa apenas que queremos que a função printf substitua uma variável onde está o marcador %s. E a variável que queremos usar é answer, que passamos para printf como outro argumento, separado do primeiro por uma vírgula.


Arquivos de cabeçalho:
