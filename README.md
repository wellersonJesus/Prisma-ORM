<h1 align="center">
  <center>Prisma: o ORM Node.js 
</center>
</h1>

<p align="center">Prisma-ORM. Projeto simples TypeScript usando npm. <a href="https://www.prisma.io">PrismaIO</a>Projeto fundação para a API REST. 
</p>

## Dev

- [WellersonJesus](https://www.instagram.com/wellerson.jesus)

## Pré-requisitos

- [Node.js](https://nodejs.org/en/)
- [Yarn](classic.yarnpkg.com/en/docs/install)

## Instalação e execução

```bash
#Faça clone desse repositório;
$ git clone
#cd prisma_decode;
$ yarn
#Para instalar models prisma projeto
$ yarn prisma generate
#Para rodar a aplicação;
$ yarn dev ou npm run dev
#Acesse a URL `
$ http://localhost:3000`;
```

## log api

```ts
const prismaClient = new PrismaClient({
  log: ["error", "info", "query", "warn"],
});
```

## incluir informações select com relacionamento

```ts
const product = await prismaClient.product.findFirst({
  where: {
    id,
  },
  include: {
    ProductCategory: {
      // Seleciona o model
      include: {
        category: true, // Dentro do model seleciono o relacionamento que quero trazer completo.
      },
    },
  },
});
```

## insominia

```ts
Create Product
POST - localhost:3000/product
{
  "name":"teclado phoda",
	"bar_code":"sldjkfdfdf0dfsd2d2adfdfasfaf",
  "price":"400"
}
```

```ts
Create Category
POST - localhost:3000/Category
{
  "name":"informatica"
}
```

```ts
Create Category Product
POST - localhost:3000/CategoryProduct
{
  "id_product":"cfdc673e-3581-4109-a686-9683fde8a8b5",
	"id_category":"03b180fc-4110-4127-b0ed-64de75424b04"
}
```

```ts
Create Product With Category
POST - localhost:3000/productWithCategory
{
  "name":"teclado phoda",
	"bar_code":"sldjkfdfdf0dfsd2d2adfdfasfaf22",
  "price":"400",
	"id_category": "03b180fc-4110-4127-b0ed-64de75424b04"
}
```

```ts
Find Product
GET - localhost:3000/product/cfdc673e-3581-4109-a686-9683fde8a8b5
```

```ts
Find Category
GET - localhost:3000/category/03b180fc-4110-4127-b0ed-64de75424b04
```
