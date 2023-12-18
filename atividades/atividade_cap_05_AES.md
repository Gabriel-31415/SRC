# Atividade Cap. 05 - AES

## 1. Qual foi o conjunto original de critérios usados pelo NIST para avaliar as cifras AES candidatas?
As cifras foram avaliadas por quatro principais características: segurança, custo, características de implementação e algoritmo. O NIST
convidou a comunidade criptográfica a montar ataques contra as cifras.

## 2. Qual foi o conjunto final de critérios usados pelo NIST para avaliar as cifras AES candidatas?
O Rijndael aparenta ter consistentemente um bom desempenho, tanto em hardware quanto em software em uma larga faixa de ambientes computacionais, sem levar em conta o seu uso nos modos de realimentação ou não realimentação. Seu tempo de expansão da chave é excelente, e a agilidade da sua chave é boa. Seu baixo requerimento de memória o faz bem apropriado para ambientes de espaço restrito, nos quais ele também apresenta excelente desempenho. As operações do Rijndael estão entre as mais fáceis de defender contra ataques de tempo e de análise de potência. Adicionalmente, ele aparenta permitir implementações de defesa contra esses ataques sem impacto significante sobre seu desempenho.

## 3. Qual é a diferença entre Rijndael e AES?
Rijndael é o algoritmo subjacente, e AES é a especificação que padroniza como o Rijndael deve ser usado para garantir a segurança e interoperabilidade em sistemas criptográficos.

## 4.Responda:
### (a) Qual é a finalidade do array Estado?
É vetor que armazena os resultados intermediários em um bloco de 128 bits após cada estágio do processamento.
### (b) Como é construída a S-box?
1. Inicialize a S-box com os valores em byte em sequência crescente linha por linha. A primeira linha contém {00}, {01}, {02}, ..., {0F}; a segunda linha contém {10}, {11} etc.; e assim por diante. Desse modo, o valor
do byte na linha y, coluna x é {yx}.
2. Mapeie cada byte na S-box com seu inverso multiplicativo no corpo finito GF(2 8 ); o valor {00} é mapeado consigo mesmo.
3. Considere que cada byte na S-box consiste em 8 bits rotulados (b 7 , b 6 , b 5 , b 4 , b 3 , b 2 , b 1 , b 0 ). Aplique uma transformação a cada bit de cada byte na S-box.
### (c) Descreva rapidamente o estágio SubBytes, ShiftRows, MixColumns, AddRoundKey, e o algoritmo de expansão de chave.
Quatro estágios diferentes são usados, um de permutação e três de substituição:
SubBytes: utiliza uma S-box para realizar uma substituição byte a byte do bloco
ShiftRows: uma permutação simples
MixColumns: uma substituição que utiliza aritmética sobre GF(2 8 )
AddRoundKey: um XOR bit a bit simples do bloco atual com uma parte da chave expandida
O algoritmo de expansão de chave do AES utiliza como entrada uma chave de 4 words (16 bytes) e produz um array linear de 44 words (176 bytes).
## 5. Quantos bytes em Estado são afetados por ShiftRows?
A primeira linha de Estado não é alterada. Para a segunda linha, é realizado um
deslocamento circular à esquerda por 1 byte. Para a terceira linha, é feito um deslocamento circular à esquerda
por 2 bytes. Para a quarta linha, ocorre um deslocamento circular à esquerda por 3 bytes.

## 6. Use a chave 1010 0111 0011 1011 para encriptar o texto claro "ok" conforme expresso em ASCII, ou seja, 0110 1111 0110 1011. Os projetistas do S-AES obtiveram o texto cifrado 0000 0111 0011 1000. E você?

## 7. Compare AES com DES. Para cada um dos seguintes elementos do DES, indique o elemento comparável no AES ou explique por que ele não é necessário no AES.
### (a) XOR do material da subchave com a entrada da função f.
Tranformações de cada rodada
### (b) XOR da saída da função f com a metade esquerda do bloco.
AddRoundKey
### (c) função f.

### (d) permutação P.
ShiftRows
### (e) troca de metades do bloco.
O AES não precisa fazer a troca de metade por que processa o bloco de dados inteiro como uma única matriz.

## 8. (1 ponto-extra) Calcule a saída da transformação MixColumns para a seguinte sequência de bytes de entrada "67 89 AB CD". Aplique a transformação InvMixColumns ao resultado obtido para verificar seus cálculos. Altere o primeiro byte da entrada de "67"para "77", realize a transformação MixColumns novamente para a nova entrada e determine quantos bits mudaram na saída. Nota: você pode realizar todos os cálculos à mão ou escrever um programa que dê suporte a eles. Se escolher escrever um programa, ele deverá ser feito inteiramente por você; nesta tarefa,não use bibliotecas ou código fonte de domínio público (você pode se guiar pelos exemplos Sage disponibilizados).

## 9. (2 pontos-extra) Crie um software que possa encriptar e decriptar usando S-AES. Dados de teste: um texto claro binário de 0110 1111 0110 1011 encriptado com uma chave binária de 1010 0111 0011 1011 deverá dar o texto cifrado binário 0000 0111 0011 1000. A decriptação deverá funcionar da mesma forma.
