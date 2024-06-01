erDiagram
  HUB_CUSTOMER {
    string hub_customer_hk PK
    string customer_bk
    datetime load_datetime
    string record_source
  }

  HUB_BOOKING {
    string hub_booking_hk PK
    string booking_bk
    datetime load_datetime
    string record_source
  }

  HUB_ORDER {
    string hub_order_hk PK
    string order_bk
    datetime load_datetime
    string record_source
  }

  HUB_PRODUCT {
    string hub_product_hk PK
    string product_bk
    datetime load_datetime
    string record_source
  }

  HUB_PAYMENT {
    string hub_payment_hk PK
    string payment_bk
    datetime load_datetime
    string record_source
  }

  LINK_CUSTOMER_BOOKING {
    string link_customer_booking_hk PK
    datetime load_datetime
    string record_source
    string hub_customer_hk
    string hub_booking_hk
  }

  LINK_CUSTOMER_ORDER {
    string lkni_customer_order_hk PK
    datetime load_datetime
    string record_source
    string hub_customer_hk
    string hub_order_hk
  }

  LINK_ORDER_BOOKING {
    string link_order_booking_hk PK
    datetime load_datetime
    string record_source
    string hub_order_hk
    string hub_booking_hk
  }

  LINK_ORDER_PRODUCT {
    string link_order_product_hk PK
    datetime load_datetime
    string record_source
    string hub_order_hk
    string hub_product_hk
  }

  LINK_ORDER_PAYMENT {
    string link_order_payment_hk PK
    datetime load_datetime
    string record_source
    string hub_order_hk
    string hub_payment_hk
  }

  SAT_CUSTOMER {
    string sat_customer_hk PK
    datetime load_datetime
    string record_source
    string hash_diff
    string first_name
    string last_name
    string phone_number
    string email_address
    string address_hash
  }

  SAT_BOOKING {
    string sat_booking_hk PK
    datetime load_datetime
    string record_source
    string hash_diff
    datetime booking_datetime
    date reservation_date
    time reservation_time
    datetime cancelled_datetime
    int table_size
  }

  SAT_ORDER {
    string sat_order_hk PK
    datetime load_datetime
    string record_source
    string hash_diff
    datetime order_datetime
    decimal total_amount
    decimal gst
  }

  SAT_PRODUCT {
    string sat_product_hk PK
    datetime load_datetime
    string record_source
    string hash_diff
    string product_description
    string product_group_hash
    bool has_gst
  }

  SAT_PAYMENT {
    string hash PK
    date load_date
    string source
    string hash_diff
    datetime payment_datetime
    decimal payment_amount
    string payment_type_hash
  }

  SAT_CUSTOMER_ADDRESS {
    string hash PK
    date load_date
    string source
    string hash_diff
    string street_address
    string city
    string state
    string postcode
  }

  HUB_CUSTOMER ||--o{ SAT_CUSTOMER : "1:M"
  HUB_CUSTOMER ||--o{ SAT_CUSTOMER_ADDRESS : "1:M"

  HUB_BOOKING ||--o{ SAT_BOOKING : "1:M"
  HUB_ORDER ||--o{ SAT_ORDER : "1:M"
  HUB_PRODUCT ||--o{ SAT_PRODUCT : "1:M"
  HUB_PAYMENT ||--o{ SAT_PAYMENT : "1:M"

  LINK_CUSTOMER_BOOKING ||--o{ HUB_CUSTOMER : "1:M"
  LINK_CUSTOMER_BOOKING ||--o{ HUB_BOOKING : "1:M"
  LINK_CUSTOMER_ORDER ||--o{ HUB_CUSTOMER : "1:M"
  LINK_CUSTOMER_ORDER ||--o{ HUB_ORDER : "1:M"
  LINK_ORDER_BOOKING ||--o{ HUB_ORDER : "1:M"
  LINK_ORDER_BOOKING ||--o{ HUB_BOOKING : "1:M"
  LINK_ORDER_PRODUCT ||--o{ HUB_ORDER : "1:M"
  LINK_ORDER_PRODUCT ||--o{ HUB_PRODUCT : "1:M"
  LINK_ORDER_PAYMENT ||--o{ HUB_ORDER : "1:M"
  LINK_ORDER_PAYMENT ||--o{ HUB_PAYMENT : "1:M"