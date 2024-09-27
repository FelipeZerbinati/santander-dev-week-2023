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

    User "1" <-- "1" Account
    User "1" <-- "N" Card
    User "1" <-- "1" Feature
    User "1" <-- "N" News

