# Vertical Slice Architecture Example

A minimal ASP.NET Core API organized by feature instead of by technical layer. Everything one use case needs lives in one folder.

## Structure

```
Applications/Features/Products/
  AddProduct/      command, handler, validator, endpoint, response
  GetProducts/     query, handler, endpoint, response
Domain/Entities/   Product
Infrastructure/    AppDbContext
```

Adding a feature means adding a folder — no edits scattered across Application, Service and Controller layers.

## Key Ideas

- One slice per use case: request, validation, handling and endpoint together
- Command/query separation without a full CQRS infrastructure
- Feature-scoped DI registration via `ProductServiceExtension`
- Validation with FluentValidation next to the request it validates

`VerticalSliceArchitecture_Advantages_Disadvantages.md` in the API project discusses the trade-offs against layered architecture.

## Getting Started

```bash
git clone https://github.com/Fcakiroglu16/vertical-slice-architecture-example.git
cd vertical-slice-architecture-example
dotnet run --project VerticalSliceArchitecture.API
```

Use `VerticalSliceArchitecture.API.http` to call the endpoints.

## Requirements

- .NET SDK
