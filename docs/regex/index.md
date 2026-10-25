# Primeiros passos com RegEx

Regular expression ou expressões regulares é um método para definir um padrão de texto/caracteres (sejam alfabéticos, numéricos ou de controle) a partir de um conjunto de metacaracteres. REGEX pode ser usado para validação, busca e manipulação de textos.

**Pattern**: Criamos um pattern (padrão) quando usamos um conjunto de metacaracteres (regex) para definir um padrão textual que queremos encontrar/combinar.

**Match**: Este termo refere-se ao casamento de um sequência de caracteres que obedece ao padrão regex que definimos. O termo casar é uma tradução comumente usada, porém ela poderia ser substituida por combinar, encontrar, igualar, entre outras.

## Os principais metacaracteres
### Representantes
|Metacaracter|Nome|Função|
|------------|----|------|
|.|Ponto|Um catactere qualquer (conhecido como curinga)|
|[]|Lista|Lista de caracteres permitidos|
|[^]|Lista negada|Lista de caracteres não permitidos|

### Quantificadores
|Metacaracter|Nome|Função|
|------------|----|------|
|?|Opcional|Zero ou um|
|+|Mais|Um ou mais|
|*|Asterisco|Zero, um ou mais|
|{n} ou {n,m}|Chaves|n vezes ou de n até m|

### Âncoras
|Metacaracter|Nome|Função|
|------------|----|------|
|^|Circunflexo|Início da string/linha|
|$|Cifrão|Fim da string/linha|
|\b|Borda|Início ou fim de palavra|

### Outros
|Metacaracter|Nome|Função|
|------------|----|------|
|\\|Escape|Torna literal o caracter seguinte|
|\||Ou|Operador lógico ou|
|()|Grupo|Delimita um grupo|

Na linha de comando de sistemas como GNU/Linux, o * e ? tem funções distintas dos metacaracteres do REGEX. Em Bash, por exemplo, estes metacaracteres são vistos como representantes, enquanto no REGEX são metacaracteres quantificadores.

O que é colocado dentro da lista não é metacaracter, por exemplo: [g.r]ato casa com 'gato', '.ato' e 'rato'. Porém, o hífen(-) é interpretado como metacarater, quando colocado entre dois caracteres, o hífen representa o intervalo entre eles. Por exemplo, [0-3] representa 0, 1, 2 e 3.
