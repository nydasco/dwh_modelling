erDiagram
  CUSTOMER {
    int customer_id PK
    string first_name
    string last_name
    string phone_number
    string email_address
    int address_id FK
  }

  ADDRESS {
    int address_id PK
    string street_address
    int postcode_id FK
  }

  POSTCODE {
    int postcode_id PK
    string postcode
    int city_id FK
  }

  CITY {
    int city_id PK
    string city
    int state_id FK
  }

  STATE {
    int state_id PK
    string state
  }

  BOOKING {
    int booking_id PK
    datetime booking_datetime
    date reservation_date
    time reservation_time
    datetime cancelled_datetime
    int customer_id FK
    int table_size
  }

  ORDER {
    int order_id PK
    int booking_id FK
    datetime order_datetime
    int customer_id FK
    decimal total_amount
    decimal gst
  }

  ORDER_DETAIL {
    int order_detail_id PK
    int order_id FK
    int product_id FK
    int product_quantity
    decimal sale_price
    decimal gst
  }

  PRODUCT {
    int product_id PK
    string product_description
    int product_group_id FK
    bool has_gst
  }

  PRODUCT_GROUP {
    int product_group_id PK
    string product_group_description
  }

  PRODUCT_PRICE {
    int product_price_id PK
    int product_id FK
    date start_date
    date end_date
    decimal unit_cost
  }

  PAYMENT {
    int payment_id PK
    datetime payment_datetime
    int order_id FK
    int payment_type_id FK
    decimal payment_amount
  }

  PAYMENT_TYPE {
    int payment_type_id PK
    string payment_description
  }

  CUSTOMER ||--o{ BOOKING : "1:M"
  CUSTOMER ||--o{ ORDER : "1:M"
  BOOKING ||--o| ORDER : "1:0"
  ORDER ||--o{ ORDER_DETAIL : "1:M"
  ORDER_DETAIL ||--|| PRODUCT : "M:0"
  PRODUCT ||--o{ PRODUCT_PRICE : "1:M"
  PRODUCT_GROUP ||--o{ PRODUCT : "1:M"
  ORDER ||--o{ PAYMENT : "1:M"
  PAYMENT_TYPE ||--o{ PAYMENT : "1:M"

  ADDRESS ||--o{ CUSTOMER : "1:M"
  POSTCODE ||--o{ ADDRESS : "1:M"
  CITY ||--o{ POSTCODE : "1:M"
  STATE ||--o{ CITY : "1:M"
