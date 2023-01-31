Aula 0 - Inicialização
Professor: David J. Malan

# O que é Ciência da Computação?
A Ciência da Computação estuda metodologias, técnicas e instrumentos computacionais visando automatizar processos e desenvolver soluções. 
A ciência da computação é fundamentalmente sobre resolução de problemas.
Podemos pensar na resolução de problemas como o processo de pegar algumas informações (detalhes sobre nosso problema) e gerar alguns resultados (a solução para nosso problema). 

# Entendendo o funcionamento dos computadores

> Representação de números

Nós usamos o sistema decimal (de base 10) para representar números, ou seja, com 10 dígitos (0 à 9).
Os computadores usam sistemas binários (de base 2), onde todas as quantidades se representam com base em dois números: 0 e 1.

*BIT - Simplificação para dígito binário. Pode assumir 2 possibilidades: 0 ou 1.

*BYTE - É composto por 8 bits, ou seja, uma cadeia de bits formada por vários 0 e 1.

> Representação de letras

Se os computadores só entendem números, poderemos atribuir os números do sistema binário a letras específicas do alfabeto. 
1 byte é o necessário para representar qualquer caracter (letras, números, sinais de pontuação).

*ASCII - Foi definido um mapeamento padrão de números em letras. A letra “A”, por exemplo, é o número 65, ou em padrão de bits é representada por 01000001. E a letra "B" é o número 66 e assim por diante.

Quando escrevemos "HI!" (72/ 73/ 33 - tabela ASCII), o computador recebe, tecnicamente, um padrão de bits (total de 24 bits), que representa uma letra específica no código ASCII. Cada letra é normalmente representada com um padrão de oito bits, ou um byte, então as sequências de bits que receberíamos são 01001000 , 01001001 e 00100001.
 
Temos 256 possibilidades representadas com 8 bits (1 byte), que são representadas na tabela ASCII, mas não são o suficiente. Ainda falta a representaçãodos caracteres de acentuação, símbolos utilizados em outras linguas, além dos emojis.

*UNICODE - Sistema que utiliza não apenas 8 bits (como ASCII), mas também 16, 24, 32 bits combinados em padrões de 0 e 1 que suporta todas as linguas humanas e emoji, pois existe uma quantidade muito maior de possibilidades.

*Emoji - são padrões de 0 e 1 que representam cada emoji dependendo das combinações.
O emoji 😂 é representado pelo decimal (128514) que corresponde ao padrão de bits (000000011111011000000010)

> Representação de imagens

Para a representação de cores, os computadores utilizam padrões de 0 e 1, atribuindo números para diferentes cores. Uma das formas de representar cores é o RGB.

*RGB - Representa a quantidade de Red, Green e Blue que possuiu para formação de uma cor. 

Da mesma forma que é aplicada para as letras, temos a possibilidade de 256 combinações utilizando 8 bits de padrão 0 e 1.

*PIXEL - são os quadradinhos minúsculos (pontos) que representam alguma cor. 1 pixel usa 24 bits, ou 3 bytes.

             R         G       B 
1 pixel =  8 bits   8 bits   8 bits = TOTAL de 24 bits para representar a formação da cor de cada pixel
        qtdade de vermelho, de verde e azul respectivamente

As imagens são compostas por muitos, milhares ou milhões desses pixels. Então, usando três bytes para representar a cor de cada pixel, podemos criar imagens.

*Resolução de uma imagem - é quantos pixels ou pontos há horizontalmente e verticalmente.

As medidas das imagens são em kilobytes (milhares de bytes), magabytes (milhoes de bytes) e as medidas dos arquivos de vídeo são em gigabytes (bilhoes de bytes).

> Representação de vídeos

