erDiagram
  FACT_ORDER {
    int order_date_id FK
    int order_time_id FK
    int customer_id FK
    int product_id FK
    decimal quantity
    decimal unit_amount
    decimal total_amount
    decimal total_gst
  }

 DIM_CUSTOMER {
    int customer_id PK
    string first_name
    string last_name
    string phone_number
    string email_address
    int address_id FK
  }

  DIM_ADDRESS {
    int address_id PK
    string street_address
    int city_id FK
    int state_id FK
    int postcode_id FK
  }

  DIM_CITY {
    int city_id PK
    string city
  }

  DIM_STATE {
    int state_id PK
    string state
  }

  DIM_POSTCODE {
    int postcode_id PK
    string postcode
  }

  DIM_DATE {
    int date_id PK
    date date
    int day
    int month
    int quarter
    int year
    string day_name
    string month_name
  }

  DIM_TIME {
    int time_id PK
    time time
    int hour
    int minute
    int second
    string period
  }
  
  DIM_PRODUCT {
    int product_id PK
    string product_description
    int product_group_id FK
    bool has_gst
  }

  DIM_PRODUCT_GROUP {
    int product_group_id PK
    string product_group_description
  }

  FACT_ORDER ||--o{ DIM_CUSTOMER : "customer_id"
  FACT_ORDER ||--o{ DIM_DATE : "order_date_id"
  FACT_ORDER ||--o{ DIM_TIME : "order_time_id"
  FACT_ORDER ||--o{ DIM_PRODUCT : "product_id"
  
  DIM_CUSTOMER ||--o{ DIM_ADDRESS : "1:M"
  DIM_ADDRESS ||--o{ DIM_CITY : "1:M"
  DIM_ADDRESS ||--o{ DIM_STATE : "1:M"
  DIM_ADDRESS ||--o{ DIM_POSTCODE : "1:M"

  DIM_PRODUCT ||--o{ DIM_PRODUCT_GROUP : "1:M"