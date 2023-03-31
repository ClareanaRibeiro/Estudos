# COMPILAÇÃO:

Para transformar o código fonte em código de máquina, usamos o comando ` make `
Mas na verdade o `make ` é um programa que chama o ` clang ` que é o compilador.
`clang ` pode ser utilizado ao invés do make conforme abaixo:

` $ clang nomeDoArquivo.c ` - Porém esse comando vai compilar e gerar um nome genérico para o programa ` a.out `

` $ clang -o nomeDoArquivo nomeDoArquivo.c `- Esse comando é mais específico pois vai compilar e salvar com  o ` nomeDoArquivo.c`

O comando make já faz isso automaticamente e mais... ainda já diz para o computador onde encontrar os 0 e 1s (código binário) das bibliotecas que utilizamos e fazemos referências no topo do código. Só usando `clang`, não será reconhecida as funções dessas bibliotecas.

` $ clang -o nomeDoArquivo nomeDoArquivo.c -lcs50 ` - Com esse comando as funções da biblioteca são reconhecidas.  

Compilar o código fonte em código de máquina é, na verdade, feito em etapas menores:
pré-processamento, compilação, montagem, linkagem/vinculação.

# MEMÓRIA:

Quando instalamos um programa ou salvamos um arquivo no computador, esses são salvos no **disco rígido/HD/SSD/CD** ou algum outro meio físico e não precisam de eletricidade para serem armazenados por longos períodos em nossos computadores. 

**RAM** (memória de acesso aleatório): onde os programas e arquivos são armazenados temporariamente em uma memória de curto prazo, apenas quando os mesmos estão sendo *executados*. Tem mais velocidade que os discos rígidos e precisam de eletricidade para funcionar.

Por isso, que quando estamos trabalhando em algum arquivo e esse ainda não foi salvo no disco rígido do computador, e a energia cai, o trabalho é perdido.


Em C, temos diferentes tipos de variáveis ​​que podemos usar para armazenar dados, e cada uma delas ocupa uma quantidade fixa de espaço da memória RAM. (Ex: bool e char = 1 byte, int = 4 bytes)

# ARRAY:

Em C, uma lista de valores armazenados um após o outro de forma contígua é chamada de array (uma espécie de matriz) e podemos acessar a informação de cada índice que se inicia por 0 com o uso dos colchetes. Em que o primeiro valor tem índice 0 e o segundo valor tem índice 1 e assim por diante.

~~~~

#include <cs50.h>
#include <stdio.h>

const int TOTAL = 3;

int main(void)
{
    int scores[TOTAL];
    for (int i = 0; i < TOTAL; i ++)
    {
         scores[i] = get_int("Pontuação:");
    }
    // Imprimir média
    printf ("Média: %f \n", (scores[0] + scores[1] + scores[2]) / TOTAL);
}

~~~~

OBSERVAÇÕES:

* A palavra **const** é usada para definir uma variável cujo valor nunca muda no prgrama, seu valor é fixo.

* A const **TOTAL** - por convenção, a variável é declarada fora da função principal(main) e em letra maiúscula para mostra a outros humanos que esta variável é uma constante afim de facilitar a visualização.


## Conversão de tipo de dado feito implicitamente pelo compilador:

Abaixo segue um programa para imprimir um único caracter:

~~~~ 

#include <stdio.h>

int main(void)
{
    char c = '#';
    printf("%c\n", c);
}

~~~~ 

Quando executado, o programa imprimirá ` # ` 
Mas se mudarmos e solicitarmos ao programa que imprima - printf("%i/n") - a variável `c` com tipo de dado inteiro.

~~~~

#include <stdio.h>

int main(void)
{
    char c = '#';
    printf("%i\n", (int) c);
}

~~~~

O programa imprimirá o número **35** que é o código ASCII para um símbolo #.


# STRINGS

Strings são, na verdade, apenas matrizes de caracteres e definidas não em C, mas pela biblioteca CS50. Se tivéssemos um array chamado s, cada caractere pode ser acessado com s[0], s[1] e assim por diante.

Uma string termina com um caractere especial, `\0`, ocupando um byte. Esse caractere é chamado de caractere nulo ou NUL. 

Dessa forma uma string declarada como `string s = "HI!" ` ocuparia não 3 bytes na memória e sim 4 bytes porque ao final da sequência de caracteres é reservado um espaço para `\0` para representar o final de uma string e indicar o início de uma nova string.

     H     I     !    \0
s   [0]   [1]   [2]   [3]






