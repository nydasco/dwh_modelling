erDiagram
  CUSTOMER {
    int customer_id PK
    string first_name
    string last_name
    string phone_number
    string email_address
    string street_address
    string city
    string state
    string postcode
    json metrics_json
  }

  PRODUCT {
    int product_id PK
    string product_description
    string product_group_description
    bool has_gst
    json metrics_json
  }