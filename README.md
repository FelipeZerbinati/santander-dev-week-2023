# Santander dev week
Java RESTful API

## Diagrama de classes
```mermaid
classDiagram
    class User {
        +String name
        +Account account
        +Card card
        +Feature[] features
        +News[] news
    }

    class Account {
        +String number
        +String agency
        +float balance
        +float limit
    }

    class Card {
        +String number
        +float limit
    }

    class Feature {
        +String icon
        +String description
    }

    class News {
        +String icon
        +String description
    }

## Diagrama de classes
```mermaid
classDiagram
    class Vendedor {
        +String nome
        +Zona[] zonas
        +void gerarRoteiroVisitas()
    }

    class Zona {
        +String nome
        +Setor[] setores
        +Vendedor titular
    }

    class Setor {
        +String nome
        +int periodoVisita
        +Cliente[] clientes
        +void calcularProximaVisita()
    }

    class Cliente {
        +String nome
        +String endereco
        +String CNPJ
        +String tipoCobranca
        +String bancoCobranca
        +String horarioVisita
        +String condicaoEntrega
        +String diaEntrega
        +String periodoVisita
        +String situacao
        +String ramoAtividade
        +String condicaoPagamento
        +String contato
        +String telefone
        +HistoricoVendas historico
        +PosicaoFinanceiraConsolidada posicaoFinanceira
        +PosicaoFinanceiraDetalhada posicaoFinanceiraDetalhada
        +Estoque estoque
        +void registrarEstoque()
        +void tomarPedido()
    }

    class HistoricoVendas {
        +Produto[] produtosVendidos
        +void exibirHistorico()
    }

    class PosicaoFinanceiraConsolidada {
        +double limiteCredito
        +double totalVencido
        +double totalAVencer
        +double disponibilidadeCredito
        +void exibirPosicao()
    }

    class PosicaoFinanceiraDetalhada {
        +Fatura[] faturasVencidas
        +Fatura[] faturasAVencer
        +void exibirDetalhes()
    }

    class Estoque {
        +Produto produto
        +int quantidade
    }

    class Produto {
        +String codigo
        +String descricao
        +double precoMedio
        +double mediaVendas
        +int[] ultimosPeriodos
        +void calcularReposicao()
    }

    class Fatura {
        +String numero
        +String dataEmissao
        +String dataVencimento
        +double valor
        +int diasAtraso
    }

    class Pedido {
        +Produto produto
        +double precoUnitario
        +double desconto
        +void registrarPedido()
    }

    Vendedor --> Zona : gerencia
    Zona --> Setor : cobre
    Setor --> Cliente : possui
    Cliente --> HistoricoVendas : possui
    Cliente --> PosicaoFinanceiraConsolidada : consulta
    Cliente --> PosicaoFinanceiraDetalhada : consulta
    Cliente --> Estoque : armazena
    Cliente --> Pedido : toma
    HistoricoVendas --> Produto : exibe
    PosicaoFinanceiraDetalhada --> Fatura : detalha
    Estoque --> Produto : armazena


