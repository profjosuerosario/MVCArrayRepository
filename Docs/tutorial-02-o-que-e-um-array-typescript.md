# Tutorial 02 — O que é um Array em TypeScript

## Objetivos

Ao final deste tutorial, você será capaz de:

- entender o que é um array;
- criar um array em TypeScript;
- acessar elementos de um array;
- compreender os índices;
- descobrir a quantidade de elementos de um array;
- acessar o primeiro e o último elemento.

---

## 1. Onde vamos escrever o código?

Neste tutorial, vamos continuar utilizando o projeto criado no **Tutorial 01**.

Não é necessário criar um novo projeto nem criar um novo arquivo.

Vamos trabalhar no mesmo arquivo:

```text
src/index.ts
```

A estrutura do projeto continuará sendo:

```text
projeto/
├── src/
│   └── index.ts
├── dist/
│   └── index.js
├── package.json
└── tsconfig.json
```

O arquivo `src/index.ts` é onde vamos escrever nosso código TypeScript.

Quando executarmos:

```bash
npx tsc
```

o TypeScript irá compilar o código e gerar o JavaScript dentro da pasta `dist`:

```text
src/index.ts
      │
      │ compilação
      ▼
dist/index.js
```

Para executar o programa, utilizaremos:

```bash
node dist/index.js
```

### Importante

Durante este tutorial, **não vamos criar vários arquivos para cada exemplo**.

Vamos começar com um código simples dentro do `src/index.ts` e, conforme novos conceitos forem apresentados, **vamos acrescentando código ao mesmo arquivo**.

Dessa forma, o programa vai crescer junto com o nosso aprendizado.

---

# 2. O que é um Array?

 Imagine que precisamos armazenar os nomes de vários alunos:

```text
Ana
Carlos
João
Maria
Pedro
```

Poderíamos criar uma variável para cada nome, mas isso rapidamente ficaria difícil de organizar.

Um **array** permite armazenar vários valores em uma única variável.

Vamos começar modificando o arquivo:

```text
src/index.ts
```

Apague o código anterior e coloque:

```typescript
const alunos = [
    "Ana",
    "Carlos",
    "João",
    "Maria",
    "Pedro"
];

console.log(alunos);
```

Agora compile:

```bash
npx tsc
```

E execute:

```bash
node dist/index.js
```

O resultado será semelhante a:

```text
[ 'Ana', 'Carlos', 'João', 'Maria', 'Pedro' ]
```

Temos agora uma variável chamada `alunos` que contém cinco valores.

---

# 3. Os elementos possuem índices

Nosso array possui cinco alunos.

Mas como podemos acessar apenas um deles?

Cada elemento possui um **índice**.

O primeiro índice de um array é `0`.

Nosso array pode ser representado assim:

```text
[0] → Ana
[1] → Carlos
[2] → João
[3] → Maria
[4] → Pedro
```

Para acessar um elemento, utilizamos o índice entre colchetes.

Vamos acrescentar uma nova linha ao nosso `src/index.ts`:

```typescript
const alunos = [
    "Ana",
    "Carlos",
    "João",
    "Maria",
    "Pedro"
];

console.log(alunos);

console.log(alunos[0]);
```

Compile novamente:

```bash
npx tsc
```

E execute:

```bash
node dist/index.js
```

Agora teremos:

```text
[ 'Ana', 'Carlos', 'João', 'Maria', 'Pedro' ]
Ana
```

O código:

```typescript
alunos[0]
```

significa:

> Acesse o elemento que está no índice `0` do array `alunos`.

Podemos acessar outro elemento.

Acrescente:

```typescript
console.log(alunos[2]);
```

Agora o arquivo está assim:

```typescript
const alunos = [
    "Ana",
    "Carlos",
    "João",
    "Maria",
    "Pedro"
];

console.log(alunos);

console.log(alunos[0]);
console.log(alunos[2]);
```

Compile e execute novamente.

O resultado será:

```text
[ 'Ana', 'Carlos', 'João', 'Maria', 'Pedro' ]
Ana
João
```

Isso acontece porque:

```text
0 → Ana
1 → Carlos
2 → João
3 → Maria
4 → Pedro
```

---

# 4. Quantos elementos existem?

Agora sabemos acessar elementos pelo índice.

Mas e se quisermos descobrir **quantos alunos existem no array**?

Para isso, utilizamos `length`.

Vamos continuar aumentando nosso programa.

Acrescente:

```typescript
console.log("Quantidade de alunos:", alunos.length);
```

Nosso código agora está assim:

```typescript
const alunos = [
    "Ana",
    "Carlos",
    "João",
    "Maria",
    "Pedro"
];

console.log(alunos);

console.log(alunos[0]);
console.log(alunos[2]);

console.log("Quantidade de alunos:", alunos.length);
```

Compile:

```bash
npx tsc
```

Execute:

```bash
node dist/index.js
```

O resultado será semelhante a:

```text
[ 'Ana', 'Carlos', 'João', 'Maria', 'Pedro' ]
Ana
João
Quantidade de alunos: 5
```

`length` representa a **quantidade de elementos** existentes no array.

Neste caso:

```typescript
alunos.length
```

retorna:

```text
5
```

É importante diferenciar:

```text
length → quantidade de elementos
índice → posição de um elemento
```

Nosso array possui:

```text
Quantidade de elementos: 5
```

Mas seus índices são:

```text
0
1
2
3
4
```

Portanto:

> Um array com cinco elementos possui índices de `0` até `4`.

---

# 5. Acessando o último elemento

Agora sabemos que:

```typescript
alunos.length
```

informa a quantidade de elementos.

Mas como podemos acessar o último elemento?

Não queremos escrever:

```typescript
alunos[4]
```

porque isso só funcionaria enquanto o array tivesse exatamente cinco elementos.

Imagine que amanhã acrescentemos outro aluno:

```typescript
const alunos = [
    "Ana",
    "Carlos",
    "João",
    "Maria",
    "Pedro",
    "Lucas"
];
```

O último índice passaria a ser `5`.

Precisamos de uma forma que funcione independentemente da quantidade de elementos.

Como `length` informa a quantidade de elementos, podemos utilizar:

```typescript
alunos.length - 1
```

No nosso exemplo:

```text
length = 5

5 - 1 = 4
```

Portanto:

```typescript
alunos[alunos.length - 1]
```

acessa o último elemento.

Vamos acrescentar essa linha ao programa:

```typescript
console.log("Último aluno:", alunos[alunos.length - 1]);
```

Nosso código agora está assim:

```typescript
const alunos = [
    "Ana",
    "Carlos",
    "João",
    "Maria",
    "Pedro"
];

console.log(alunos);

console.log(alunos[0]);
console.log(alunos[2]);

console.log("Quantidade de alunos:", alunos.length);

console.log("Último aluno:", alunos[alunos.length - 1]);
```

Compile:

```bash
npx tsc
```

Execute:

```bash
node dist/index.js
```

Resultado:

```text
[ 'Ana', 'Carlos', 'João', 'Maria', 'Pedro' ]
Ana
João
Quantidade de alunos: 5
Último aluno: Pedro
```

---

# 6. O que acontece com um índice que não existe?

Nosso array possui cinco elementos:

```text
0 → Ana
1 → Carlos
2 → João
3 → Maria
4 → Pedro
```

O que acontece se tentarmos acessar:

```typescript
alunos[5]
```

Vamos experimentar.

Acrescente ao final do programa:

```typescript
console.log("Índice 5:", alunos[5]);
```

O arquivo agora está assim:

```typescript
const alunos = [
    "Ana",
    "Carlos",
    "João",
    "Maria",
    "Pedro"
];

console.log(alunos);

console.log(alunos[0]);
console.log(alunos[2]);

console.log("Quantidade de alunos:", alunos.length);

console.log("Último aluno:", alunos[alunos.length - 1]);

console.log("Índice 5:", alunos[5]);
```

Compile e execute novamente.

O resultado será:

```text
Índice 5: undefined
```

Por quê?

Porque não existe um elemento no índice `5`.

Temos:

```text
0 → Ana
1 → Carlos
2 → João
3 → Maria
4 → Pedro
```

O índice `5` seria uma sexta posição, mas nosso array possui apenas cinco elementos.

---

# 7. Nosso código até aqui

Ao longo do tutorial, começamos com um array simples e fomos acrescentando funcionalidades.

O código final é:

```typescript
const alunos = [
    "Ana",
    "Carlos",
    "João",
    "Maria",
    "Pedro"
];

console.log(alunos);

console.log(alunos[0]);
console.log(alunos[2]);

console.log("Quantidade de alunos:", alunos.length);

console.log("Último aluno:", alunos[alunos.length - 1]);

console.log("Índice 5:", alunos[5]);
```

# 8. Exercício 1

Agora vamos aplicar os mesmos conceitos.

No arquivo:

```text
src/index.ts
```

substitua o exemplo dos alunos por um array chamado `frutas`:

```text
Maçã
Banana
Laranja
Abacaxi
Manga
```

Depois, utilizando o mesmo array, mostre:

1. o array completo;
2. a primeira fruta;
3. a terceira fruta;
4. a quantidade de frutas;
5. a última fruta.

Não utilize:

```text
for
forEach
map
filter
```

Utilize apenas os conceitos apresentados neste tutorial:

```text
array
índice
length
```

Depois compile:

```bash
npx tsc
```

E execute:

```bash
node dist/index.js
```

---

# 9. Exercício 2

Crie um array chamado `notas` contendo:

```text
7
8
6
9
10
```

Depois mostre:

- a primeira nota;
- a segunda nota;
- a última nota;
- a quantidade de notas.

Em seguida, tente acessar:

```typescript
notas[5]
```

Observe o resultado.

Depois explique:

> Por que `notas[5]` não retorna uma nota?

---

# 10. Checklist

Antes de avançar para o próximo tutorial, verifique se você consegue:

- [ ] explicar o que é um array;
- [ ] criar um array;
- [ ] acessar um elemento pelo índice;
- [ ] explicar por que o primeiro índice é `0`;
- [ ] utilizar `length`;
- [ ] explicar a diferença entre `length` e índice;
- [ ] acessar o primeiro elemento;
- [ ] acessar o último elemento;
- [ ] explicar o que acontece quando um índice não existe;
- [ ] compilar o arquivo `src/index.ts`;
- [ ] executar o arquivo gerado em `dist`.

---