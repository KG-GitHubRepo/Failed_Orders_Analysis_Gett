# Failed_Orders_Analysis_Gett
Business Analysis Assignment from StrataScratch.

Gett, previously known as GetTaxi, is an Israeli-developed technology platform solely focused on corporate Ground Transportation Management (GTM). They have an application where clients can order taxis, and drivers can accept their rides (offers). At the moment, when the client clicks the Order button in the application, the matching system searches for the most relevant drivers and offers them the order. In this task, we would like to investigate some matching metrics for orders that did not completed successfully, i.e., the customer didn't end up getting a car.

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

## Assignment

1. Build up distribution of orders according to reasons for failure: cancellations before and after driver assignment, and reasons for order rejection. Analyse the resulting plot. Which category has the highest number of orders?
2. Plot the distribution of failed orders by hours. Is there a trend that certain hours have an abnormally high proportion of one category or another? What hours are the biggest fails? How can this be explained?
3. Plot the average time to cancellation with and without driver, by the hour. If there are any outliers in the data, it would be better to remove them. Can we draw any conclusions from this plot?
4. Plot the distribution of average ETA by hours. How can this plot be explained?

## Insights

1. Distribution of Orders by Reasons for Failure
    * More Cancellations without Driver Assignment:
        * A higher number of cancellations occur when no driver is assigned compared to when a driver is assigned.
        * Client Cancellations without Driver Assignment: 13,435 instances.
    * Potential Reasons for Client Cancellations without Driver Assignment:
        * Long Waiting Times: Customers may cancel due to perceived long waiting times for driver assignment.
        * Technical Glitches: Delays or failures in the system might hinder driver assignment.
        * Competing Services: Customers may opt for alternative transportation options while waiting.

2. Distribution of Failed Orders by Hours
    * Peak Hours for Cancellations:
        * Highest Cancellation Hours: 8:00, 21:00, 22:00, and 23:00.
        * These hours likely correspond to peak order times, possibly due to rush hours, evening activities, or late-night travel needs.
    * Explanation of Peak Hours:
        * Morning Peak (8:00): Likely due to morning rush hour when people are commuting to work.
        * Evening Peaks (21:00-23:00): Possibly due to people returning home from work, social activities, or other evening engagements.

3. Average Time to Cancellation with and without Driver, by Hour
    * Longer Time to Cancellation with Driver Assigned:
        * On average, cancellations take longer when a driver is assigned.
        * Peak Cancellation Time: Occurs at 3:00, suggesting a notable number of client cancellations during this hour.
    * Possible Reasons:
        * Clients may wait longer when a driver is assigned in anticipation of the ride but eventually cancel due to delays or changed plans.

4. Distribution of Average ETA by Hours
    * Correlation Between Waiting Time and Failed Orders:
        * As the average waiting time (ETA) for clients increases, the number of failed orders also increases.
    * Highest Count of Cancellations: 8:00
        * Clients likely experienced extended waiting periods during this time, leading to increased cancellations.

## Recommendations

1. Improve Driver Matching Efficiency:
    * Enhance the algorithm to reduce the time taken to assign drivers to orders.

2. System Reliability:
    * Address technical glitches to ensure smoother operations and quicker driver assignments.

3. Customer Communication:
    * Keep customers informed about expected waiting times and possible delays to manage their expectations.

4. Resource Allocation:
    * Ensure adequate driver availability during peak hours to reduce cancellations due to long waiting times.
