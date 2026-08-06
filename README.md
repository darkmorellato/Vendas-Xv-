# Dados por Mês

Esta pasta contém os dados de vendas separados por mês para o dashboard XV Analytics.

## Estrutura de Arquivos

- **`manifest.json`**: Define a ordem de exibição dos meses no dashboard.
- **`MM-AAAA.json`**: Arquivos individuais contendo os dados de cada mês. O prefixo numérico (ex: `01-`, `02-`) controla a ordem.

## Formato dos Arquivos de Mês

Cada arquivo `MM-AAAA.json` contém um objeto com as seguintes propriedades:

```json
{
  "label": "Mês Ano",
  "total": 123,
  "data": [
    {
      "name": "Nome do Produto ou Item",
      "quantity": 1,
      "percentage": 0.0097
    }
  ]
}
```

- `label`: Nome amigável do período (ex: "Maio 2026").
- `total`: Quantidade total de itens vendidos no mês.
- `data`: Lista de itens vendidos, com `name`, `quantity` e `percentage` (valor decimal, ex: 0,97% → 0,0097).

## Como Adicionar um Novo Mês

1. Crie um novo arquivo JSON seguindo o formato acima.
2. Nomeie o arquivo com prefixo numérico para definir a ordem, por exemplo `09-jun2026.json`.
3. Atualize `manifest.json` inserindo a nova chave (ex: `"jun2026"`) na posição adequada da lista `_ordem_exibicao`.
4. O dashboard carregará automaticamente o novo mês.

## Notas

- O dashboard (`index.html`) lê o `manifest.json` e depois carrega cada arquivo da pasta.
- Não renomeie as chaves internas (`mai2026`, `abr2026`, etc.) — elas são usadas como identificadores.