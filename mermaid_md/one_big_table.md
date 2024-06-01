erDiagram
  BOOKINGS {
    int booking_id PK
    datetime booking_datetime
    datetime reservation_datetime
    datetime cancelled_datetime
    string customer_first_name
    string customer_last_name
    string customer_phone_number
    string customer_email_address
    string customer_street_address
    string customer_city
    string customer_state
    string customer_postcode
    int table_size
  }

  PAYMENTS {
    int payment_id PK
    datetime payment_datetime
    string customer_first_name
    string customer_last_name
    string customer_phone_number
    string customer_email_address
    string customer_street_address
    string customer_city
    string customer_state
    string customer_postcode
    string payment_description
    string payment_type
    decimal payment_amount
  }

  ORDERS {
    int order_id PK
    datetime order_datetime
    string customer_first_name
    string customer_last_name
    string customer_phone_number
    string customer_email_address
    string customer_street_address
    string customer_city
    string customer_state
    string customer_postcode
    string product_description
    string product_group_description
    bool has_gst
    int product_quantity
    decimal sale_price
    decimal gst
    decimal total_amount
  }