# Garagem de Carros com Jest

Atividade prática avaliativa de programação orientada a objetos com **TypeScript** e testes automatizados com **Jest**.

O projeto é um sistema simples para controlar uma garagem de carros, com as classes `Car` e `Garage`.

## Funcionalidades

- Criar carros com marca, modelo e ano.
- Controlar se o carro está armazenado, pelo atributo `stored`.
- Adicionar e remover carros da garagem, atualizando o `stored` automaticamente.
- Contar os carros da garagem.
- Procurar um carro pelo modelo.
- Impedir carros duplicados (mesma marca, modelo e ano).
- Buscar todos os carros de uma marca (desafio adicional).

## Estrutura do projeto

```text
garagem-jest
├── src
│   ├── Car.ts
│   └── Garage.ts
├── tests
│   └── Garage.test.ts
├── jest.config.js
├── package.json
├── package-lock.json
└── tsconfig.json
```

## Classes

### `Car`

| Método | Descrição |
|---|---|
| `getBrand()` | Retorna a marca do carro |
| `getModel()` | Retorna o modelo do carro |
| `getYear()` | Retorna o ano do carro |
| `getStored()` | Retorna se o carro está armazenado |
| `setStored(value)` | Altera o estado de `stored` |

As propriedades são `private`, e o acesso é feito apenas pelos métodos (encapsulamento). O `stored` começa como `false`.

### `Garage`

| Método | Descrição |
|---|---|
| `addCar(car)` | Adiciona o carro e define `stored` como `true`. Lança erro se já existir um carro com a mesma marca, modelo e ano |
| `removeCar(car)` | Remove o carro e define `stored` como `false` |
| `getCarCount()` | Retorna a quantidade de carros na garagem |
| `findCarByModel(model)` | Retorna o carro com o modelo informado, ou `undefined` |
| `getCarsByBrand(brand)` | Retorna todos os carros da marca informada (desafio) |

## Como executar

Instale as dependências:

```bash
npm install
```

Execute os testes:

```bash
npm test
```

## Testes

Os testes ficam em `tests/Garage.test.ts` e seguem o padrão **AAA** (Arrange, Act, Assert). São 18 testes:

- **Testes 1 a 4:** criação do carro e alteração do `stored`.
- **Testes 5 a 9:** adicionar e remover carros e o estado de `stored`.
- **Testes 10 e 11:** busca por modelo, com carro existente e inexistente.
- **Teste 12:** bloqueio de carros duplicados.
- **Testes 13 a 16:** marca e ano do carro encontrado, remoção entre vários carros e estados após a remoção.
- **Desafio 1 e 2:** busca de carros por marca.

## Tecnologias

- TypeScript
- Jest
- ts-jest
