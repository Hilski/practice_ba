# Модель данных подсистемы продавцов

В данной модели описаны основные сущности, необходимые для функционирования подсистемы продавцов маркетплейса.

---

## Основные сущности

### 1. Seller (Продавец)
- `id` (PK)
- `company_name`
- `inn`
- `email`
- `phone`
- `registration_status` (pending / approved / rejected)
- `created_at`

### 2. Product (Товар)
- `id` (PK)
- `seller_id` (FK → Seller.id)
- `name`
- `description`
- `price`
- `sku`
- `category_id` (FK → Category.id)
- `status` (draft / pending / approved / rejected)
- `created_at`

### 3. Inventory (Складской остаток)
- `id` (PK)
- `product_id` (FK → Product.id)
- `quantity`
- `warehouse_location`
- `updated_at`

### 4. Order (Заказ)
- `id` (PK)
- `product_id` (FK → Product.id)
- `buyer_id` (FK → Buyer.id)
- `quantity`
- `status` (new / confirmed / shipped / delivered / canceled)
- `ordered_at`

### 5. Buyer (Покупатель)
- `id` (PK)
- `full_name`
- `email`
- `phone`
- `address`

### 6. Question (Вопрос к товару)
- `id` (PK)
- `product_id` (FK → Product.id)
- `buyer_id` (FK → Buyer.id)
- `question_text`
- `answer_text`
- `asked_at`
- `answered_at`

### 7. Category (Категория)
- `id` (PK)
- `name`
- `parent_id` (FK → Category.id)

---

## Диаграмма ER (PlantUML)

```plantuml
@startuml

' Стиль IE — информация по модели данных маркетплейса

entity "Seller" {
  * id : UUID
  --
  company_name : string
  inn : string
  email : string
  phone : string
  registration_status : enum
  created_at : datetime
}

entity "Product" {
  * id : UUID
  --
  seller_id : UUID
  name : string
  description : text
  price : decimal
  sku : string
  category_id : UUID
  status : enum
  created_at : datetime
}

entity "Inventory" {
  * id : UUID
  --
  product_id : UUID
  quantity : int
  warehouse_location : string
  updated_at : datetime
}

entity "Order" {
  * id : UUID
  --
  product_id : UUID
  buyer_id : UUID
  quantity : int
  status : enum
  ordered_at : datetime
}

entity "Buyer" {
  * id : UUID
  --
  full_name : string
  email : string
  phone : string
  address : string
}

entity "Question" {
  * id : UUID
  --
  product_id : UUID
  buyer_id : UUID
  question_text : text
  answer_text : text
  asked_at : datetime
  answered_at : datetime
}

entity "Category" {
  * id : UUID
  --
  name : string
  parent_id : UUID
}

' связи
Seller ||--o{ Product
Product ||--o{ Inventory
Product ||--o{ Order
Product ||--o{ Question
Buyer ||--o{ Order
Buyer ||--o{ Question
Category ||--o{ Product

@enduml
