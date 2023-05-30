# Shopping Cart Service

> Sample shopping cart CRUD service using ASP.NET 6 and GraphQL

## Requirements

- [GNU Make](https://www.gnu.org/software/make/)
- [.NET Core 6](https://dotnet.microsoft.com/)
- [Angular](https://angular.io)

## Usage

To install project dependencies, run the following command:
```bash
make install
```

To run the `ui` project, run the following command:
```bash
make start_ui
```

To run the `bff` project, run the following command:
```bash
make start_bff
```

## Sample Queries & Mutations

```grapql
{
  products {
    id
    name
    description
    reviews {
      reviewer
      content
      stars
    }
  }
}

{
  reviews {
    reviewer
  }
}

mutation AddProduct($productInput: ProductInput!) {
  addProduct (product: { name: $productInput.name, price: $productInput.price, description: $productInput.description, manufacturer: $productInput.manufacturer }) {
    id
    name
    description
    price
    reviews {
      reviewer
      content
      stars
    }
  }
}

mutation AddReviewForProduct($id: ID!, $review: ReviewInput!) {
  addReview(id: $id, review: $review) {
    name
    description
    price
    
    reviews {
      reviewer
      content
      stars
    }
  }
}

mutation DeleteProductById($id: ID!) {
  deleteProductById(id: $id) {
    name
    description
    price
    manufacturer

    reviews {
      reviewer
      content
      stars
    }
  }
}
```

## Links

- [Very useful .NET GraphQL link](https://dev.to/berviantoleo/getting-started-graphql-in-net-6-part-1-4ic2)
- [Another very useful .NET GraphQL link](https://www.red-gate.com/simple-talk/development/dotnet-development/building-and-consuming-graphql-api-in-asp-net-core-5/)
- [Mutations guide](https://graphql.org/learn/queries/#mutations)
