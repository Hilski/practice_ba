# Взаимодействие компонентов подсистемы продавцов

В данном разделе описаны основные сценарии взаимодействия между продавцом, API-сервисами, базой данных и внешними системами. Диаграммы представлены в формате PlantUML.

---

## Сценарий 1: Регистрация продавца

<a href="Registration.png" target="_blank">
  <img src="Registration.png" width="500"/>
</a>

[Открыть PUML](https://github.com/Hilski/practice_ba/blob/main/interaction/Registration)

---

## Сценарий 2: Размещение и модерация карточки товара

<a href="Publication.png" target="_blank">
  <img src="Publication.png" width="500"/>
</a>

[Открыть PUML](https://github.com/Hilski/practice_ba/blob/main/interaction/Publication)

---

## Сценарий 3: Обработка заказа

<a href="Order.png" target="_blank">
  <img src="Order.png" width="500"/>
</a>

[Открыть PUML](https://github.com/Hilski/practice_ba/blob/main/interaction/Order)

---

## Примечания

- Все взаимодействия между сервисами происходят по REST и/или через Kafka.
- Аутентификация пользователя осуществляется через централизованный Auth Service.
- Статусы заказов и товаров обновляются асинхронно.
