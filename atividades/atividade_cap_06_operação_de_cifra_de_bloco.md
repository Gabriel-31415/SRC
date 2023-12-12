Questões retiradas do livro-texto da disciplina.Conforme conversamos em sala de aula, as atividades devem ser realizadas para apresentação e discussão em sala, sempre nas aulas das quintas-feiras, atribuindo ao estudante uma nota de 0 ou 1 por cada atividade realizada e apresentada.
1. O que é encriptação tripla?

 **É usar três estágios de encriptação, podendo usar 3 chaves ou 2 chaves.**

2. O que é ataque meet-in-the-middle?

**É uma forma de ataque em que os dados trocados entre duas partes são de alguma forma interceptados, registrados e, possivelmente, alterados pelo atacante sem que as vitimas se apercebam.**

3. Quantas chaves são usadas na encriptação tripla?

**Pode ser duas chaves ou três chaves, mas como a geração de 3 chaves é bastante custoso, mas foi descoberto de usar duas chaves em uma sequência encriptar-decriptar-encriptar.**

4. Por que a parte do meio do 3DES é decriptação, em vez de encriptação?

**Não existe significado criptográfico no uso da decriptação para o segundo estágio. Sua única vantagem é
que permite que os usuários do 3DES decriptografem dados criptografados pelos usuários do DES único mais
antigo**

5. Por que alguns modos de operação de cifra de bloco só utilizam a encriptação, enquanto outros empregam encriptação e decriptação?

**Preservar o investimento já feito em software e equipamento para usar um tipo de algoritmo, no caso do DES é usar encriptação múltipla e múltiplas chaves.**

6. Você deseja construir um dispositivo de hardware para realizar encriptação de bloco no modo cipher block chaining (CBC) usando um algoritmo mais forte do que DES. 3DES é um bom candidato. A Figura 1 mostra duas possibilidades, ambas acompanhando a definição do CBC. Qual das duas você escolheria:
 (a) Por segurança?

**Não sei dizer se há diferença no aumento de segurança na possibilidade b.**

 (b) Por desempenho?

**A primeira opção, por causa que possui somente um loop. Os loops não podem ser executados em paralelo.**

8. Crie um software que possa encriptar e decriptar no modo cipher block chaining usando uma das seguintes cifras: módulo affine 256, módulo Hill 256, S-DES, DES. Teste os dados para S-DES usando um vetor de inicialização binário de 1010 1010. Um texto claro binário de 0000 0001 0010 0011 encriptado com uma chave binária de 01111 11101 deverá dar um texto claro binário de 1111 0100 0000 1011. A decriptação deverá funcionar de modo correspondente.
