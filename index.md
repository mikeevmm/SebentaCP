## Introdução

Em geral, aprender os princípios de porgramação é um processo de tentativa e erro.

É possível estudar, no sentido académico mais típico, as estruturas mais
concretas ou abstratas presentes na programação, mas o fundamental já se
encontra nessa altura profundamente interiorizado -- um pouco como na matemática
ou física já há muito se ultrapassaram os conceitos algébricos básicos.

No entanto, por vezes este facto pode ser esquecido na introdução à programação;
por outro lado, manuais pedagógicos de programação podem
frequentemente ser morosos ou substimar (ou sobrestimar) o conhecimento prévio
matemático do leitor.

E nem sempre é fácil aprender programação por tentativa e erro quando não há tempo,
ou especial motivação.

Assim, nesta sebenta pretende-se fazer um apanhado dos conhecimentos mais essenciais
de programação, podendo funcionar como uma referência que pode também ser seguida
do princípio ao fim.

>Pague-me um café em **[`http://ko-fi.com/mikeevmm`](http://ko-fi.com/mikeevmm)**
>:)

## O Que é uma Linguagem de Programação

Apesar de soar filosófico, uma pergunta pertinente será em que consiste uma
linguagem de programação e, sobretudo, o que permite fazer.

Sucintamente, uma linguagem de programação consiste, como em qualquer linguagem,
num conjunto de vocabulário e regras gramaticais (designadas **sintaxe**) que
permitem comunicar um conjunto de intenções; neste caso ao computador.

Por exemplo, suponhamos `1 + 3` (uma "frase" legítima em Python): trata-se de um
conjunto de 3 "palavras", duas delas números e uma um operador matemático,
que tanto denota `a soma de um e três` como o número ("palavra") `4`.
A regra gramatical manifesta-se no facto de `+ 1 3` não fazer sentido.

Assim, uma linguagem de programação permite-nos definir um conjunto de ações
a tomar pelo computador, o que permite automatizar tarefas (tratamento de dados),
ou criar comportamentos complexos (simulação, jogos).

## O Que é Python e Como o Instalar

>Este capítulo é irrelevante se já tiver instalado `Python`, **verificando que
>a instalação não é de Python 2**.
>
>Para isso, abra uma linha de comandos (Windows) ou terminal (MacOS, Linux)
>e escreva `python` (carregando `enter`).
>Se uma instalação já estiver presente, poder-se-á ler a versão instalada
>na máquina; caso contrário dever-se-á observar um erro.

Python trata-se de uma linguagem de programação simples, recomendada para
principiantes pela sua sintaxe próxima do inglês, e abstração de operações,
ou seja, pelo facto de muitas operações comuns de realizar (e por vezes não
triviais de implementar) estarem já embutidas na língua.

Apesar disso, é extremamente poderosa, sendo por isso muito
utilizada por académicos, hackers,
ou para prototipar ou desenvolver ferramentas (onde a performance
não é crítica).

Prolongando o paralelismo entre Python e uma linguagem comum, é necessário
"ensinar" ao computador a interpretar código Python, ou seja, "instalar" Python.
Tal pode ser feito em `python.org`, onde instaladores se encontram disponíveis
para download.

>Uma vez que o *layout* do site oficial muda frequentemente, não considero vantajoso
>detalhar o processo de instalação.
>Aquando da escrita deste texto, o instalador pode ser obtido na tab *Downloads*,
>onde é possível fazer download de Python 3.6.1 (referido como Python3) ou
>2.7.13 (referido como Python2), sendo que nos interessa o primeiro.

O instalador inclui também o editor de código IDLE, normalmente utilizado na
cadeira de CP.

---

## Variável (*Variable*)

Um dos conceitos que poderá ser ambíguo para estudantes da área da matemática é
o conceito de variável.

Como se verificará ao longo deste texto, os conceitos associados a programação
são normalmente muito mais atómicos (básicos) do que o correspondente matemático.

Trata-se do caso aqui: designa-se simplesmente por variável uma entidade que
contenha um valor, e que possa ser acessada como tal. Nem sempre será sinónima
do valor que contém (como se verá mais à frente), mas é muitas vezes esse o caso.

Em Python, uma variável é definida quando lhe é atribuída um valor. No IDLE:

```python
>>> x = 3
```

A variável `x` contém agora o valor `3`, podendo ser chamada, obtendo-se o valor
correspondente:

```python
>>> x
3
```

Podemos manipular variáveis, obtendo novos valores, ou mudar o valor da variável:

```python
>>> x = 3
>>> x
3
>>> x + 1
4
>>> x
3
>>> x = x + 1
>>> x
4
```

Existem restrições aos nomes de variáveis, nomeadamente:

+ Não podem conter espaços; `x y` seria intrepretado como duas variáveis, `x` e `y`.

+ São *case-sensitive*, isto é, maiúsculas e minúsculas **não** são irrelevantes.
 `X` ≠ `x`.

+ Não podem começar com um dígito, embora possam conter dígitos. `a1` é válido,
 enquanto que `1a` não.

+ Apenas podem conter os caracteres alfanuméricos normais; letras, números,
 e *underscores* (`_`).

## Comentários

Um comentário trata-se, à partida, de um pedaço de código ignorado na execução
do programa.

Do ponto de vista prático, comentários são particularmente úteis na manutenção
de código a longo termo, permitindo adicionar notas explicando o raciocínio ou
utilização do programa, assim como comportamentos ou valores esperados.

Comentários são delimitados à esquerda por um cardinal (`#`), e extendem-se até ao
fim da linha. Podem seguir código a ser executado.

Por exemplo:

```python
>>> a = 3 # Este texto é ignorado.
>>> # a = 4
>>> a
3
```

Ao longo deste texto, comentários serão também usados como acima, isto é, para adicionar
informação contextualmente, sem que se deva atribuir valor programático ao texto.

## Operações Aritméticas

Estão definidas os seguintes operadores aritméticos em Python:

+ `+` - soma
+ `-` - subtração
+ `*` - multiplicação
+ `/` - divisão
+ `%` - módulo; se `r` for a parte inteira de `a/b`, então `b = r + b%a` (resulta
 no "resto" da divisão).
+ `**` - expoente; `a**b` significa `a` levantado a `b`.
+ `//` - *floor division*; parte inteira de uma divisão, tal que `b = a*(b//a) + b%a`.

É de notar que muitas das vezes estes operadores estão definidos para
entidades que não numéricas; ver-se-á mesmo que é possível definir o resultado
destas operações para [tipos](#tipos-types) originais.

## Tipos (*Types*)

>Esta secção deverá ser, sobretudo, uma referência.
>Os diferentes tipos existentes são, com a prática, fixados, e a sua
>designação é mais importante para pesquisas (por exemplo), do que
>na escrita de código propriamente dito.
>Além disso, alguns tipos dependem do conceito de outros, como se verá.

Os valores podem ser de tipos difrentes. A manifestação mais direta deste facto
surge na comparação de elementos, que normalmente só pode ser efetuada entre
dois elementos do mesmo tipo.

Por exemplo, `1 > 2` é verdadeiro, mas qual o significado da comparação `"a" > 2`
(onde `"a"` é a letra)?

Em Python, há um número de tipos já definidos, dos quais falaremos dos mais relevantes.

### String (*Fio* (de letras))

Como já vimos, uma série de caracteres alfanúmericos (letras) define não
uma sequencia textual, mas sim uma variável.

Mas como fazer para definir texto, no sentido literal?

A um conjunto de caracteres delimitado por um par de aspas (*quotes*, `"`)
ou plicas (*single quotes*, `'`), chama-se uma `string`, e define, precisamente,
um pedaço de texto. Podemos atribuir esse valor a uma variável:

```python
>>> x = 'hello world!'
>>> x
'hello world!'
```

>Conseguir que uma máquina "diga" *Hello World* é um dos exercícios mais celebrados
>e é normalmente utilizado como o exercício (relevante) mais básico possível,
>assim como uma boa métrica da complexidade da linguagem.
>Algumas línguas mais exotéricas, como *Brainfuck*, têm `Hello World`s mais...
>[complexos](#Brainfuck-Hello-World).

Strings funcionam como [listas](#list-lista), na medida em que cada letra pode
ser acedido pelo seu índice, como elementos da `string`.

```python
>>> x[0] # Primeiro elemento de "hello world"
'h'
```

Além disso, `string`s podem ser somados, e até multiplicados:

```python
>>> 'some' + ' ' + 'text'
'some text'
>>> 'spam' * 3
'spamspamspam'
```

>Este último caso, de multiplicação de `string`s, leva por vezes a erros com
>cálculo numérico, onde se usa, acidentalmente, `string`s em vez de números:
>
>```python
>>>> x = "3"
>>>> x*3
>"333"
>```

### Int (*inteiro*, *integer*)

Como o nome indica, um `int` é o tipo correspondente a valores inteiros.
A sua definição é subtil, pois o tipo `float` (que veremos já a seguir) pode também
definir um qualquer valor inteiro; a diferença está no facto de um `int` verdadeiramente
*não ter a capacidade* de definir um valor que não inteiro.

>A diferença entre `int` e `float` encontra-se muito mais presente em Python2,
>onde o quociente entre dois inteiros era *sempre* ainda um inteiro.
>Este comportamento levava de tal forma a erros dissimulados que foi simplesmente
>removido em Python3.

Vimos já multiplos exemplos de variáveis com tipos `int`:

```python
>>> x = 3
>>> x
3
```

A noção mais formal de `int` depende de como o seu valor é guardado na memória
do computador, de um ponto de vista mais técnico. Essa questão encontra-se
abordada na seccção [referente a memória](#valores-e-memória).

>Na minha opinião, as questões de memória e arquitetura surgem naturalmente
>numa fase posterior, em que começam a aparecer preocupações com optimização.
>
>No entanto, esta matéria é por vezes introduzida no início do semestre, pelo
>que o capítulo correspondente procura ser auto-contido e pode ser lido desde já.

`int`s (e [`float`s](#float-floating-point-ponto-flutuante) ) operam aritmeticamente
como esperado para valores numéricos, com a notável exceção da divisão de `int`s
**em Python2**:

```python
>>> 3/2
1
```

### Float (*floating point*; *ponto flutuante*)

O tipo `float` também representa um número mas como o nome *ponto flutuante* indica,
de certa forma, este possui uma natureza fracional; entre `3.14159` e `314.59`
o ponto "flutua".

Em termos práticos, um `float` representa um valor decimal, com uma precisão limitada
(ver [Representação de Valores e Memória](#valores-e-memória)).

Pode ser declarado explicitamente, ou resultar da divisão de dois `int`s (**em Python3!**):

```python
>>> 1.51
1.51
>>> 3/5 # Python3 apenas
0.6
>>> 1.0/3 # Python2 e 3
0.5
```

É de notar, ainda, que de operações entre um [`int`](#int-inteiro-integer) e um `float`
resulta ainda num `float` (como esperado):

```python
>>> 1.513 + 2
3.513
```

### List (*lista*)

Uma lista pode ser descrita como um conjunto **ordenado** de elementos, que
**poderão ou não** ser repetidos.

Trata-se de um conceito fundamental na programação, sendo que muitos exercícios dependem
fundamentalmente do conceito de lista.

Uma lista, sintaticamente, é delimitada por dois parentesis retos (`[ ]`), e os seus
elementos são separados por vírgulas. Estes elementos podem ser de qualquer tipo,
sendo que uma lista pode conter elementos de diferentes tipos (incluindo listas),
ou outras variáveis.

Acede-se aos elementos de uma lista pelo seu índice, sendo que o primeiro elemento
tem índice `0`, o segundo `1`, ..., de acordo com a sintaxe `list[index]`.

>A questão do *zero indexed* (primeiro índice 0 e consequentes) ou *one indexed*
>(primeiro índice 1 e consequentes) é fonte, compreensivelmente, de protesto.
>
>A razão para o *zero index* ser a norma não é apenas histórica; de um
>ponto de vista prático, muitas das sucessões consideradas são tais que é
>conveniente ter o índice a variar de `0...i`.
>
>[... É um ponto de discussão ativa.](http://www.cs.utexas.edu/users/EWD/transcriptions/EWD08xx/EWD831.html)

Os elementos de uma lista podem ser alterados, como se fossem uma variável.
Diz-se, por isso, **mutável**.

Por exemplo:

```python
>>> l = ['some text', 3, 2.14]

>>> l
['some text', 3, 2.14]

>>> l[0]
'some text'
>>> l[3]
# Erro --- a lista não tem quatro elementos!

>>> x = 3.14
>>> l = [x, x]
>>> l
[3.14, 3.14]

>>> l = [1, 2, 3]
>>> l[0] = 0
>>> l
[0, 2, 3]
```

Listas podem ser somadas, ou multiplicadas, com resultados semelhantes
aos que se obtêm para [`string`s](#string-fio-de-letras):

```python
>>> [1, 2, 3] + ['a', 5]
[1, 2, 3, 'a', 5]
>>> ['lovely', 'spam'] * 3
['lovely', 'spam', 'lovely', 'spam', 'lovely', 'spam']
```

### Tuple (*tupla*)

Uma tupla é semelhante a uma lista, mas cujos elementos são imutáveis, isto
é, não podem ser alterados.

É delimitada por parêntesis curvos (`( )`), sendo que se define uma tupla
vazia/de um só elemento como `(,)`/`(x,)`, a fim de desambiguar de uma expressão
entre parêntesis.

Os elementos numa tupla podem ser de qualquer tipo (incluindo outras tuplas),
sendo separados por vírgulas.
O acesso aos mesmos é efetuado da mesma forma que para uma lista.

Por exemplo:

```python
>>> x = ( 1, 'a', ('b', 2) )
>>> x
(1, 'a', ('b', 2))
>>> x[0]
1
>>> x[2]
('b', 2)
>>> x[2][0]
'b'
```

Tuplas apresentam resultados muito semelhantes aos que se obtêm
para `string`s e `list`s, quando operadas aritmeticamente:

```python
>>> (1, 'a') + ('c',)
(1, 'a', 'c')
>>> ('p', 'b', 'x') * 3
('p', 'b', 'x', 'p', 'b', 'x', 'p', 'b', 'x')
```

### Set (*conjunto*)

Um `set` representa um conjunto no sentido matemático tradicional.

A ordem dos seus elementos é **irrelevante**, e não pode possuir o mesmo
elemento mais do que uma vez.

É delimitado por chavetas (`{ }`), embora tenha de possuir elementos na sua
declaração (sendo que caso contrário se declarou um [dicionário](#dictionary-dicionário)).

Por exemplo:

```python
>>> {3,1,2}
{1, 2, 3}

>>> {1,1,1}
{1}
```

>`Set`s não podem ser operados aritmeticamente, tendo de se usar as suas
>funções internas; tratar-se-á este caso mais à frente.

### Dictionary (*dicionário*)

Um dicionário faz corresponder a um elemento, a **key** (*chave*), outro elemento,
**value** (*valor*), sendo que o tipo de qualquer do valor é arbitrário
(podendo, de facto, ser um outro dicionário).

>O tipo da chave não é, na verdade, de todo arbitrário, tendo esta de ser *hashable*.
>Isto significa que elementos mutáveis, como listas ou dicionários, não podem ser
>usados como chaves em dicionários, sendo que tal resulta no erro
>`TypeError: unhashable type`.
>
>Esta questão é discutida mais a fundo no apêndice [Hashable Elements](#hashable-elements).

São declarados com chavetas (`{ }`), e opcionalmente já com chaves e valores correspondentes,
de acordo com a sintaxe

```python
{ chaveA : valorA, chaveB : valorB }
```

Acede-se aos valores pela chave correspondente, sendo que a sintaxe correspondente
é semelhante ao da lista. Tomando um novo exemplo, já com valores:

```python
>>> d = {} # Dicionário vazio
>>> d = {'a' : 1, 'b' : 2}
>>> d['a']
1
>>> x = d['b']
>>> x
2
```

Por razões óbvias, as chaves deverão ser únicas (pois a referência a um valor tornar-se-ia
ambígua), mas não há qualquer restrição aos valores.

>Dicionários não podem ser operados aritmeticamente, simplesmente porque
>tal não tem uma interpretação lógica consistente.

### Exemplo

#### Como representar uma lista telefónica

Um dicionário é frequentemente comparado com uma lista telefónica. Suponhamos os
seguintes nomes e números:

```text
Adolfo Dias             263779913

Oscar Allonso           249113132

Jose Aguiar de Mota     251998195

Henrique Olhao          229505463
```

>Ignoramos para já acentuação, uma vez que tal introduz complicações, devido
>[à representação interna de texto](#valores-e-memória).

Estes dados podem facilmente ser guardados num dicionário, para
posterior acesso. Representemos os nomes como `string`s, e os números de
telefone como `int`s:

```python
{
    'Adolfo Dias' : 263779913,
    'Oscar Alhonso' : 249113132,
    'Jose Aguiar de Mota' : 251998195,
    'Henrique Olhao' : 229505463
}
```

>Em Python, ao contrário do que se verifica noutras linguas, o espaçamento
>é muito relevante, como se verá à frente.
>
>No entanto, na declaração de elementos como `list`s, `tuple`s ou `dictionary`s,
>o espaçamento usado é, normalmente, irrelevante, sendo sobretudo uma
>questão estética.

Supondo que este dicionário se encontra atribuido à variável `d`,

```python
>>> d['Adolfo Dias']
263779913
```

---

## Scripts

>A noção de *script* não pertence especificamente a Python, nem é necessariamente
>formalmente um conceito de programação, mas poderá ser confundida com o uso da shell
>numa primeira aproximação, pelo que aqui se refere.

Até agora tem-se apresentado como exemplo comandos únicos numa *shell* de Python.

>Uma *shell* é uma interface onde o utilizador pode fornecer
>comandos e observar o seu resultado, interagindo com o mesmo.

Em geral, é mais interessante designar, à partida, um conjunto de instruções
a executar, podendo correr o programa de uma só vez.

A estes ficheiros é dado o nome `script`.

Um script de Python é qualquer ficheiro com a terminação `.py`.

Na prática, é comum recorrer ao IDLE, o editor de texto incluido com
a instalação oficial de python para escrever scripts.
`File > New File` cria um novo ficheiro, que pode ser guardado em
qualquer local. Este pode depois ser corrido em `Run > Run Module`,
ou carregando `F5`.

## Funções

Apesar do nome, num contexto de programação, *função* toma um significado
diferente (sendo por vezes designada por *método* ou *rotina*).

Trata-se de uma aplicação, à qual, quando é passada um número de *argumentos*,
(i.e., parâmetros), toma um valor resultante, indicado pela *keyword* `return`.

Em Python, uma função `cube_plus_sum` poderia ser definida da seguinte forma:

```python
def cube_plus_sum(a, b):
    x = b**3
    return x + a
```

Observa-se que:

+ O conteúdo da função encontra-se delimitado
 por um *tab* (ou 4 espaços) no início de cada linha.
+ Um argumento funciona como uma variável valida apenas dentro
 da função, cujo valor é definido quando a função é chamada.
+ O nome de uma função deve obedecer às mesmas regras que
 [variáveis](#variável-variable).

Existe um número de funções pre-definidas em Python. Uma das mais importantes
será a função `print`, que dado um qualquer número de parâmetros, os imprime.

Por exemplo:

```python
def cube_plus_sum(a, b):
    return b**3 + a

print( cube_plus_sum(2, 4) )
```

Correndo o exemplo acima, observa-se de *output*:

```python
66
```

>A função `print` é verdadeiramente útil, pelo que se constata ainda que:
>
> + `print` imprime vários elementos separados por um espaço, quando
>  separados por vírgulas
> + Dois `print`s consecutivos encontram-se separados por um parágrafo,
>  salvo se o último elemento do primeiro `print` se encontrar precedido
>  por uma vírgula (em Python2. No caso de Python3 é possível especificar
>  um separador nulo usando `print('text', end='')`)

Uma função pode ainda não devolver qualquer valor, sendo utilizada para
representar uma ação composta efetuada várias vezes (reduzindo assim a
repetição de código e tornando o mesmo mais fácil de manter).

```python
def print_equivalent_resistance(a, b):
    equiv = a * b / (a + b)
    print("The equivalent resistance of", a, "in parallel with", b, 'is', equiv)

print_equivalent_resistance(5,10)
print_equivalent_resistance(1,1)
print_equivalent_resistance(12,3)
print_equivalent_resistance(b=3, a=12)
```

Com output

```text
The equivalent resistance of 5 in parallel with 10 is 3.3333333333333335
The equivalent resistance of 1 in parallel with 1 is 0.5
The equivalent resistance of 12 in parallel with 3 is 2.4
The equivalent resistance of 12 in parallel with 3 is 2.4
```

> Note-se o arredondamento em 3.3(3)

## Casting

Por vezes, faz sentido interpretar um tipo como um tipo diferente.

O caso mais óbvio será o de operar sobre um número dado como `string`.

Suponhamos que, dado uma variável do tipo `string`, `x`, contendo um número,
procuramos obter o seu triplo.

Como [visto antes](#string-fio-de-letras), não é possível multiplicar o valor
diretamente:

```python
>>> x = '3'
>>> x*3
'333'
```

Não só o resultado é incorreto, como ainda se encontra no formato de `string`!

Devemos então converter o valor dado para o tipo correto esperado -- chama-se
a este processo *casting* (atirar - de um tipo para outro). Em Python, basta
para tal chamar o tipo de destino como função, passando-lhe o valor a
converter:

```python
>>> x = '3'
>>> y = int(x)
>>> y * 3
9
```

Podemos converter o resultado de volta para `string`:

```python
>>> str(y) * 3
'999'
```

## Objectos

## Escapes

## Hexadecimal

---

## Valores e Memória

Um computador, de uma forma reducionista, pode ser tomado como um conjunto
de lâmpadas em série. Cada uma destas lâmpadas poderá estar ligada ou desligada,
pelo que, associando `1` a ligado e `0` a desligado, cada estado da máquina
pode ser caracterizado por uma sequência de `1`s e `0`s.

O acima descrito trata-se de uma ilustração de um sistema binário, que matematicamente
pode ser bem descrito; trata-se, de facto, apenas de um sistema em base 2.

A noção de sistema de numeração é fácil de entender, observando a base decimal.
Suponhamos o número `9213`.

>Apelando ao ensino primário...

Temos que este número é composto por `3` unidades, `1` dezena, `2` centenas e
`9` milhares. Atribuindo a cada uma destas categorias um índice, começando em
zero, então observa-se que

$$ 9213 = 3  \cdot  10^0 + 1 \cdot 10^1 + 2 \cdot 10^2 + 9 \cdot 10^9 $$

De facto, no sistema decimal, cada dígito tem 10 estados possíveis, `0...9`,
e cada número é dado como uma soma de termos do tipo \$$ d * 10^i $$
, onde `i` é o índice do dígito. Por isso se diz que o sistema de numeração
decimal é **base 10**.

Note-se ainda que esta lógica se extende para decimais:

$$ 0.314 = 0 \cdot 10^0 + 3 \cdot 10^{-1} + 1 \cdot 10^{-2} + 4 \cdot 10^{-3} $$

Assim, uma mudança de sistema de numeração (normalmente dito mudança de base),
para uma base `b` consiste apenas na representação de números usando `0...b`
dígitos, onde cada dígito `d` de índice `i` tem o valor:

$$ d*b^i $$

O aparelho descrito acima tem, portanto a capacidade de descrever qualquer valor
(inteiro, positivo):

```text
Binário         Decimal
0       ----->  0
1       ----->  1
10      ----->  2
11      ----->  3
100     ----->  4
         ...
```

Claro que para representar números maiores, serão necessários mais dígitos;
mais *bits*. Com 32 bits (de onde vem *arquitetura 32-bits*), pode-se representar
um valor no intervalo `0  a  4.294.967.295`.

Podemos também mapear números para outros símbolos; em primeira aproximação
consideremos como representar números negativos:

Um número pode ser negativo ou positivo. Podemos portanto reservar o primeiro
*bit* para indicação do sinal. Tomando 8 *bits* de memória:

```text
00000000 ---> 0
00000001 ---> 1
10000001 ---> -1
```

Claro que o intervalo possível de representar é diminuído, podendo-se apenas
representar em módulo, no esquema acima,

$$ 2^7 = 128 \text{ combinações.} $$

Por outro lado, podemos também atribuir números a letras (e outros símbolos
alfanuméricos). É dado o nome de **codificação de caracteres** (*character-encoding*)
a um padrão que faça corresponder a uma sequência de bits um caracter.

Dois dos *character-encodings* mais comuns e importantes serão **ASCII** e
**UTF-8**.

### ASCII

De acordo com o *standard* ASCII, cada letra (ou, em geral, símbolo) é representada
por 7 bits, permitindo portanto codificar 128 caráteres, dos quais 33 são de controlo
(e.g. parágrafo ou *newline*).

Baseado no alfabeto e caractéres comuns na língua inglesa, permite codificar apenas
uma variedade limitada de símbolos. No entanto é possivelmente o *encoding* mais comum
na programação.

[ASCII na Wikipédia](https://en.wikipedia.org/wiki/ASCII)

### UTF-8

De acordo com o *encoding* UTF-8, cada caráter é representado por 1 a 4 bytes.

> 1 byte são 8 bits,
> [embora, historicamente, tal não tenha sido sempre verdade](https://en.wikipedia.org/wiki/Byte).

Permite, assim, representar 1.112.064 símbolos diferentes, incluindo todo o "alfabeto"
ASCII, assim como muitos outros símbolos (incluindo, na atual especificação, emojis).

[UTF-8 na Wikipédia](https://pt.wikipedia.org/wiki/UTF-8)

## Apêndices

### Hashable Elements

Uma função diz-se de *hashing* se mapear elementos de tamanho variável para
elementos (de chegada) de tamanho fixo. Se dois elementos diferentes forem
codificados para o mesmo objeto de tamanho fixo, é dito que existe uma colisão.

> Naturalmente, pretende-se que existam poucas colisões.

Assim, um tipo é *hashable* se para cada elemento existir uma um elemento
identificativo (de tamanho fixo) que não mude (e, em geral, seja único).

Torna-se então mais intuitivo justificar que as chaves de um dicionário tenham
de ser elementos *hashable*; supondo que a um elemento `K` (*key*) associamos
um valor `V`, com `K` *hashable* e hash `H(K)`, temos, esquematicamente:

```math
D : H(K) ---> V
```

Assim, quando procuramos o valor associado a `K`,

```math
D(K) = D[ H(K) ] = V
```

Se o elemento `K` não puder ser coerentemente transformado por `H`, o que
se verifica para objetos mutáveis, este processo é impossível, pelo que se
justifica que não possam ser chaves em dicionários.

[Mais informação sobre Hash Functions.](https://en.wikipedia.org/wiki/Hash_function)

### Brainfuck Hello World

```brainfuck
++++++++++[>+++++++>++++++++++>+++>+<<<<-]>++.>+.+++++++..+++.>++.<<+++++++++++++++.>.+++.------.--------.>+.>.
```

[Main informação sobre Brainfuck.](https://en.wikipedia.org/wiki/Brainfuck)

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"
type="text/javascript"></script>