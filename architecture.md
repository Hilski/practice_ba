# 🧱 Архитектура системы (C4)

## Диаграмма контекста

```plantuml
@startuml
!includeurl https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml
Person(seller, "Продавец")
System(sellerSystem, "Подсистема продавцов")
System(marketplace, "Маркетплейс")

Rel(seller, sellerSystem, "Работает с", "HTTPS")
Rel(sellerSystem, marketplace, "Интеграция по API")
@enduml
```

## Диаграмма контейнеров

```plantuml
@startuml
!includeurl https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml
System_Boundary(sellerSystem, "Продавец-система") {
  Container(web, "Web UI", "React", "UI для продавца")
  Container(api, "API Gateway", "Node.js", "REST API")
  Container(service, "Seller Service", "Java Spring", "Бизнес-логика")
  Container(db, "PostgreSQL", "Хранилище данных")
  ContainerQueue(kafka, "Kafka", "Очередь событий")
}

Person(seller, "Продавец")
Rel(seller, web, "Работает с")
Rel(web, api, "HTTP")
Rel(api, service, "gRPC / REST")
Rel(service, db, "JDBC")
Rel(service, kafka, "Пишет события")
@enduml
```