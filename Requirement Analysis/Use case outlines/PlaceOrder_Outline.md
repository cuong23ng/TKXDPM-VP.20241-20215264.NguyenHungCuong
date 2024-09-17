# Use case "Place Order"
## Basic flow of the event
1. Customer requests to place order in the cart
2. AIMS software checks the availability of products in the cart 
3. AIMS software displays the form of delivery information with order information 
4. Customer enters and submits delivery information (Table 2) 
5. AIMS software calculates and updates order information with shipping fees (Table 3) 
6. Customer asks to pay order 
7. AIMS software calls UC “Pay order” 
8. AIMS software display general information of the order (Table 4) 
9. AIMS software send invoice and payment transaction information to the customer’s email

## Alternative flows of the event
| No | Location | Condition | Action | Resume location |
| --- | --- | --- | --- | --- |
| 1 | Step 3 | If the inventory quantity of these products is insufficient | The AIMS software notifies that the products in the cart are not available and stay at the use case “View cart” | Use case ends |
| 2 | Step 6 | If there are any required fields left blank or invalid information | AIMS software notifies that the delivery info is invalid (blank or wrong format) | Step 3 |
| 3 | Step 5 | If the user chooses to place a rush order | AIMS software inserts use case “Place rush order” | Step 5  (in “flow of events” above) |
| 4 | Step 6 | If the users want to adjust the delivery method or the items | AIMS software backs to the form of information | Step 3 |
| 5 | Step 9 | If customer cancels the order before the order is approved | AIMS software refunds to the customer using VNPAY | Use case ends |
