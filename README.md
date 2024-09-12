
# Introdução ao C# e DataTables em .NET Core 8

C# é uma linguagem de programação moderna e versátil, amplamente utilizada para o desenvolvimento de aplicações web, desktop e móveis. Com a chegada do .NET Core 8, novas funcionalidades e melhorias foram introduzidas, tornando o desenvolvimento ainda mais eficiente.

Neste post, vamos criar uma aplicação simples em .NET Core 8 que utiliza o DataTables para exibir uma lista de itens categorizados. Vamos começar criando uma entidade para as categorias e outra para os itens.

## Estrutura do Projeto

### Entidade Categoria

**C#**

```csharp
public class Categoria
{
    public int Id { get; set; }
    public string Nome { get; set; }
}
```

### Entidade Item

**C#**

```csharp
public class Item
{
    public int Id { get; set; }
    public string Nome { get; set; }
    public int CategoriaId { get; set; }
    public Categoria Categoria { get; set; }
}
```

### Exemplo de Dados Fictícios

**C#**

```csharp
var categorias = new List<Categoria>
{
    new Categoria { Id = 1, Nome = "Eletrônicos" },
    new Categoria { Id = 2, Nome = "Moda" }
};

var itens = new List<Item>
{
    new Item { Id = 1, Nome = "Smartphone XYZ", CategoriaId = 1 },
    new Item { Id = 2, Nome = "Fone de Ouvido ABC", CategoriaId = 1 },
    new Item { Id = 3, Nome = "Camisa Estilosa", CategoriaId = 2 },
    new Item { Id = 4, Nome = "Tênis Confortável", CategoriaId = 2 }
};
```

### Configuração do DataTables

Para configurar o DataTables, você pode usar o seguinte código JavaScript:

**JavaScript**

```javascript
$(document).ready(function() {
    $('#example').DataTable({
        "ajax": {
            "url": "/api/itens",
            "dataSrc": ""
        },
        "columns": [
            { "data": "nome" },
            { "data": "categoria.nome" }
        ]
    });
});
```

### Conclusão

Com essas configurações, você terá uma tabela dinâmica que exibe itens categorizados, utilizando o DataTables em uma aplicação .NET Core 8. Isso é apenas o começo; você pode expandir essa aplicação para incluir funcionalidades como filtros, paginação e muito mais.
