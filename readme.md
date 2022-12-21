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
Product-A  unit-price: 120 THB
Product-B  unit-price: 130 THB
Product-C  unit-price:  10 THB

## Order-001
Product-A  5 pieces  --> 600 THB
Product-B  3 pieces  --> 390 THB
Product-C  2 pieces  -->  20 THB
Shipmentfee          --> 523 THB

## Order-001-log result
Product-A  120 + 60 = 180 THB/piece
Product-B  130 + 61 = 191 THB/piece
Product-C   10 + 20 =  30 THB/piece
Shipmentfee             0 THB
Alignment               0 THB

# Write a function that support 
## input
1. price : [120, 130, 10]
2. amount : [5,3,2]
3. fee : 523

## output
1. result = [180, 191, 30]
2. align = 0
