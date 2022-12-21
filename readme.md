# Overview
TS company sales products including shipment service.
we would like to log the cost of each product purchasing,
which will have various cost-of-product as per shipment fees.

Our to-move legacy accout system cannot handle floating point.
Therefore, for any combination that service fee cannot be dvided to integer unit-cost
suggest an additional service fee to make the service fee applicable

An order can consist of multiple product and amount of purchasing 

# Example 
## Product info
|   Product   | Unit-price |
|-------------|------------|
| Product-A   |     120    |
| Product-B   |     130    |
| Product-C   |      10    |

## Order-001
|   Product   |   Piece   |  Cost   |
|-------------|-----------|---------|
| Product-A   |      5    |   600   |
| Product-B   |      3    |   390   |
| Product-C   |      2    |    20   |
| Shipmentfee |           |   523   |

## Order-001-log result
|   Product   | Product-price | Service-cost |  Cost   |
|-------------|---------------|--------------|---------|
| Product-A   |      120      |       60     |  180    |
| Product-B   |      130      |       61     |  191    |
| Product-C   |       10      |       20     |   30    |
| Shipmentfee |               |              |   -     |
| Alignment   |               |              |   0     |

# Write a function that supports
## input arguments
1. price : [120, 130, 10]
2. amount : [5,3,2]
3. fee : 523

## output result as
1. result = [180, 191, 30]
2. fee_align_suggest = 0
