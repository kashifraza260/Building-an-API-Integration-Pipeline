n8n Ai Automation
Owned By: Kashif Raza
Last Updated: 09/11/2026

Fetches orders from the Academy API, enriches them with customer
data, routes by priority and region, and sends enterprise orders
to a priority queue in batches.

## Flow
1. GetOrders: Fetches paginated orders from the Academy API
2. GetCustomers: Fetches customer records (parallel with orders)
3. MergeOrdersCustomers: Joins orders + customers on customer_id
4. AggregateOrders + SendToOrdersQueue: Batches and sends enriched orders
5. CheckSubscriptionTier: Splits enterprise vs other customers
6. FilterDelivered + BatchPriorityOrders: Filters and batches enterprise orders
7. SendToPriorityQueue: Posts priority orders to the Academy API
8. RouteByRegion: Routes non-enterprise orders by region
9. FinalizePipeline: Posts summary for grading

## Dependencies
- Requires: n8n Academy API Key credential

Part of: n8n Foundations Program Course N8N102, Section 1
