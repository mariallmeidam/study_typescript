# TypeScript

-  Linguagem baseada no JavaScript
-  Possuem tipagem éstatica
-  Volta a ser código JS quando é convertido/transpilado

### Diferenças entre tipagens

#### Estática

Não permite a alteração do tipo da linguagem depois de declarada
Exemplos: int a = "texto" // Isso não pode ocorrer

#### Dinâmica

Possui tipos porém pode ser transferida facilmente para outro tipo

## Diferença entre JS e TS

JavaScript:

-  Tipagem dinâmica
-  Programação estruturada
-  Funções
-  Prototypes
-  Funções construtoras

TypeScript

-  Tipagem estática
-  Orientada a objetos
-  Genéricos
-  Namespace
-  Decorators

TypeScript -> JavaScript || JavaScript !-> TypeScript

## Tipagem Estática

### Tipagem Explicita

```
let valor: number
valor = "frase" // Não é possível
```

float = int
-> Números que possuem ponto flutuante ou não não são diferenciados

### Tipagem NÃO Explicita

```
let fraselegal = "Carpe Diem"
frase legal = 10 // Não é possivel
```

-> O TS já entende "fraseLegal" como string

## Tipo utilizados em TS

-  Number | decimal e inteiro
-  String
-  Booleano
-  Any | Pode ser modificado (qualquer)
-  Array | let list: number[] = [2,3,4,5] , let list: Array<number> = [2,3,4,5]
-  Tupla | Array de números diferentes let array = [number, string];
-  Enum | Constante de valores pré definidos
-  Unknown | Pode ser qualquer coisa
-  Null
-  Undefined
-  Void | Tipo de função que não retorna nenhum valor

## Programação Orientada a Objetos

Oferece a possibilidade de utilização de classes, interfaces, encapsulamento, herança ...

### Classes

```
class Exemplo {
    // atributos
    // construtor
    // getter e setter
    // métodos
}
```

### Herança

Utilizamos o comando extends para hendar classes. Se tivermos métodos iguais na classe herdada
utilizamos o comando super.

```
class Base {
    nome: string;

    constructor(nome: string) {
        this. nome = nome;
    }

    print(msg: string = 'Class Base') {
        console.log(msg)
    }
}
```

```
class Herdeira extends Base {
    nome: string;

    constructor(nome: string) {
        super(nome)
    }

    print(msg: string = 'Class Herdeira ') {
        super.print(msg)
    }
}
```

### Encapsulamento

Como em outras linguagens, por meio de getters e setters permite que o usuários
acesse atriutos protegidos por meio de getters e setters.

```
class Exemplo {
    private_nome: string;

    get nome():string {
        return this._nome;
    }

    set nome(nome:string): void {
        this._nome = nome;
    }
}
```

### Abstratas

Servem de exemplo para classes filhas, dando a estrutura e atributos

```
abstract class Abstrata {

    constructor(public nome: string) {
    }

    print(): void {
        console.log('Nome' + this.nome)
    }

    abstract otherPrint(): void;
}
```

```
class Filha extends Abstrata {
    constructor() {
        super('Class Filha Abs');
    }

    print(): void {
        console.log('Class Filha Abs');
    }

    otherPrint(): void {
        console.log('Other print method');
    }
}
```

### Interfaces

Definem a estruta de quem herda elas. Todos os métodos e atributos devem ser
implementados nas classes filhas, mas alguns atributos podem ser opcionais.

```
interface Interface {
    atributo1: string;
    atributo2?: number;

    print();
}
```

```
class Filha implements Interface {
    atributo1: string = 'Class Filha';
    atributo2?: number = 1;

    print() {
        console.log(this.atributo1);
    }
}

```

## Instalação

Instalação globalmente

```
npm i -g typescript
```

Verificação da instalação

```
tsc -v
```

Criando o projeto

```
tsc --init
```

Criando arquivos

```
tsc <<Nome do arquivo>>
```

### Compilação de arquivos TS

-  Instalação do plugin "Code Runner"
-  Instalação de depências

```
npm i -g ts-node
```

Para rodar o arquivo executar: CTRL + ALT + N

## React + Typescript

Por padrão o React utiliza JavaScript mas pode ser utilizado também como TypeScript.
No React utiliza-se arquivos de extensões .js ou jsx, com TypeScript utilizamos
.ts ou tsx.

Para criar um projeto com TypeScript, executamos o comando abaixo:

```
npx create-react-app <<nome-do-projeto>> --template Typescript
```

Se o projeto já estiver sido criado utilize o comando:

```
npm install --save-dev typescript
```

Nesse caso necessitando da alteração no arquivo package.json:

```
{
    "scripts": {
        "build": "tsc",
    }
}
```

Para rodar o arquivo execute:

```
npm run buildx
```
