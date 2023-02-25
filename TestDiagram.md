## Test Diagram
```mermaid
sequenceDiagram
    participant dotcom
    participant iframe
    participant viewscreen
    dotcom->>iframe: loads html w/ iframe url
    iframe->>viewscreen: request template
    viewscreen->>iframe: html & javascript
    iframe->>dotcom: iframe ready
    dotcom->>iframe: set mermaid data on iframe
    iframe->>iframe: render mermaid
```
@startuml

skin rose
left to right direction
title Банкомат
actor клиент
actor Банк
rectangle Банкомат {
клиент -- (Снатие наличных)
клиент -- (Проверка баланса)
клиент -- (Пулучение кредита)
 (Снатие наличных) .> (Проверка баланса) : include
  (Пулучение кредита) .> (Проверка баланса) : extend
Банк -- (Проверка работоспособности)
}
@enduml