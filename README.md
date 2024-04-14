# Failed_Orders_Analysis_Gett
I choose this Business Analysis Assignment from StrataScratch.

## Data Description
Two data sets: data_orders and data_offers, both being stored in a CSV format. The data_orders data set contains the following columns:
* order_datetime - time of the order
* origin_longitude - longitude of the order
* origin_latitude - latitude of the order
* m_order_eta - time before order arrival
* order_gk - order number
* order_status_key - status, an enumeration consisting of the following mapping:
    4 - cancelled by client,
    9 - cancelled by system, i.e., a reject
* is_driver_assigned_key - whether a driver has been assigned
* cancellation_time_in_seconds - how many seconds passed before cancellation
* The data_offers data set is a simple map with 2 columns:
* order_gk - order number, associated with the same column from the orders data set
* offer_id - ID of an offer

