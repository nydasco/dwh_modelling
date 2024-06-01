erDiagram
  CUSTOMER_STREAM {
    string activity_id PK
    datetime ts
    string customer FK
    string activity
    string anonymous_customer_id
    json feature_json
    float revenue_impact
  }

  CUSTOMER_DIM {
    int customer PK
    string first_name
    string last_name
    string phone_number
    string email_address
    string street_address
    string city
    string state
    string postcode
  }

  CUSTOMER_STREAM ||--o{ CUSTOMER_DIM : "customer"