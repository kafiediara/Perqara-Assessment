create table orders_detail  
as 
select od.order_status, oid.order_id, oid.price , oid.freight_value, od.order_purchase_timestamp,
od.order_approved_at,od.order_delivered_carrier_date,od.order_delivered_customer_date,od.order_estimated_delivery_date,
s.seller_city,s.seller_state,ord.review_score,opd.payment_type,opd.payment_installments,opd.payment_value,
opd.payment_sequential,cd.customer_city,cd.customer_state,pcnt.product_category_name_english
from
    stg_order_items_dataset as oid
    join stg_orders_dataset as od on (oid.order_id = od.order_id )
    join stg_sellers_dataset as s on (oid.seller_id = s.seller_id)
    join stg_order_reviews_dataset as ord on (oid.order_id = ord.order_id)
	join stg_order_payments_dataset as opd on (oid.order_id = opd.order_id)
	join stg_customers_dataset as cd on (od.customer_id = cd.customer_id)
	join stg_products_dataset as pd on (oid.product_id = pd.product_id)
	join stg_product_category_name_translation as pcnt on (pd.product_category_name = pcnt.product_category_name)
