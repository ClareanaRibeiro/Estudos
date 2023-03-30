# COMPILAÇÃO:

Para transformar o código fonte em código de máquina, usamos o comando ` make `. 
Mas na verdade o `make ` é um programa que chama o ` clang ` que é o compilador.
`clang ` pode ser utilizado ao invés do make conforme abaixo:

` $ clang nomeDoArquivo.c ` - Porém esse comando vai compilar e gerar um nome genérico para o programa ` a.out `

` $ clang -o nomeDoArquivo nomeDoArquivo.c `- Esse comando é mais específico pois vai compilar e salvar com `o nomeDoArquivo.c`

O comando make já faz isso automaticamente e mais... ainda já diz para o computador onde encontrar os 0 e 1s(código binário) das bibliotecas que utilizamos e fazemos referências no topo do código. Só usando `clang`, não será reconhecida as funções dessas bibliotecas.

` $ clang -o nomeDoArquivo nomeDoArquivo.c -lcs50 ` - Esse comando sim seria o completo para utilizar que sejam reconhecidas as funções da biblioteca.

Compilar o código-fonte em código de máquina é, na verdade, feito em etapas menores:
pré-processamento, compilação, montagem, linkagem/vinculação.

# Memória

Quando instalamos um programa ou salvamos um arquivo no computador, esses são salvos no **disco rígido/HD/SSD/CD** ou algum outro meio físico e não precisam de eletricidade para serem armazenados por longos períodos em nossos computadores. 

**RAM** (memória de acesso aleatório): onde os programas e arquivos são armazenados temporariamente em uma memória de curto prazo, apenas quando os mesmos estão sendo *executados*. Tem mais velocidade que os discos rígidos e precisam de eletricidade para funcionar.

Por isso, que quando estamos trabalhando em algum arquivo e esse ainda não foi salvo no disco rígido do computador, e a energia cai, o trabalho é perdido.


Em C, temos diferentes tipos de variáveis ​​que podemos usar para armazenar dados, e cada uma delas ocupa uma quantidade fixa de espaço. (Ex: bool e char = 1 byte, int = 4 bytes)


