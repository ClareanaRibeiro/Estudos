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

* A const **TOTAL** - por convenção é declarada fora da função principal(main) e em letra maiúscula para indicar que variável é uma constante afim de facilitar a visualização.


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
Mas e se mudarmos e solicitarmos ao programa que imprima **printf("%i/n")** a variável `c` com tipo de dado inteiro.

~~~~

#include <stdio.h>

int main(void)
{
    char c = '#';
    printf("%i\n", (int) c);
}

~~~~

O programa imprimirá o número **35** que é o código ASCII para um símbolo **#**.


# STRINGS

Strings são, na verdade, apenas matrizes de caracteres e definidas não em C, mas pela biblioteca CS50.           Se tivéssemos um array chamada s, cada caracter pode ser acessado com s[0], s[1] e assim por diante.

Uma string termina com um caractere especial, `\0`, que ocupa mais um byte na memória do computador. Esse caracter é chamado de caractere nulo ou NUL. 

Dessa forma uma string declarada como `string s = "HI!" ` ocuparia não 3 bytes na memória e sim 4 bytes porque ao final da sequência de caracteres é reservado um espaço para `\0` para representar o final de uma string e indicar o início de uma nova string.

     H     I     !    \0
    [0]   [1]   [2]   [3]



Segue abaixo um loop para imprimir todos os caracteres de uma string.

~~~~

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string s = get_string("Input:  ");
    printf("Saída: ");
    for (int i = 0; s[i] != '\0'; i++)
    {
        printf("%c", s[i]);
    }
    printf("\n");
}

~~~~ 

OBSERVAÇÃO:

A condição do looping para identificar o tamanho (comprimento) da string foi:  `s[i] != \0 ` - Já que em C, no final de cada string tem **\0** e essa condição está verificando se o índice que está sendo verificado é diferente de **\0**.

Porém na biblioteca de strings de C, temos a função **strlen**, que serve para obter o comprimento de uma string, e é justamente esse raciocínio que acontece por debaixo dos panos e foi utilizado para a construção dessa função.

~~~~

#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string s = get_string("Input: ");
    printf("Saída:\n");
    for (int i = 0, n = strlen(s); i < n; i++)
    {
        printf("%c\n", s[i]);
    }
}

~~~~

Segue abaixo o exemplo de 2 programas, ambos transformam os caracteres minúsculos em maiúsculas.
O 1º com o raciocínio utilizado para atingir esse objetivo e o 2º a partir do uso da função **toupper** que alguém criou com esse intuito e está inclusa na biblioteca **ctype**.

~~~~

#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string s = get_string("Before: ");
    printf("After:  ");
    for (int i = 0, n = strlen(s); i < n; i++)
    {
        if (s[i] >= 'a' && s[i] <= 'z')
        {
            printf("%c", s[i] - 32);
        }
        else
        {
            printf("%c", s[i]);
        }
    }
    printf("\n");
}

~~~~

OBSERVAÇÃO: 

* A condição vai avaliar caracter por caracter em looping. Se estiver em minúsculas (o que significa que tem um valor entre o de a e z), será convertido para maiúsculas.

* Pq ` - 32 `? - Porque no código ASCII, **a** minúsculo corresponde à 97 e **A** maiúsculo corresponde à 65. (97-65 =32). E o mesmo acontece assim em diante para todas as outras letras. Ex: b=98 | B=66 (A diferença sempre será 32.)

~~~~

#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string s = get_string("Antes: ");
    printf("Depois:  ");
    for (int i = 0, n = strlen(s); i < n; i++)
    {
        printf("%c", toupper(s[i]));
    }
    printf("\n");
}

~~~~

OBSERVAÇÃO:

* Aqui a função **toupper** vai transformar o caracter minúsculo em maiúsculo e caso o caracter já estiver maiúsculo irá permanecer maiúsculo.

* A função **toupper** espera que passe como parâmetro apenas 1 caracter (char - c), e não suporta que passe uma string, por isso é indispensável o uso do loop.

Assim como a função *toupper* na biblioteca *ctype*, e a função *strlen* na biblioteca *string*, existem diversas outras funções já criadas anteriormente por outras pessoas afim de facilitar a vida disponíveis em outras bibliotecas. Por isso a vantagem de utilizar uma linguagem popular.









