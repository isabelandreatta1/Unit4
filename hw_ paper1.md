
## Homework May 3rd - Respond to Paper 1 Questions

### Question 9 

The invetory of office supplies used in the school is stored on a computer as a single file. 

Each of the office supplies in the inventory (such as paper, ink, toner, printers, pens, staplers, pencils and scissors) has a unique ID number, name, maximum quantity and remaining quantity. 

**Outline the steps in an algorithm that would ouput a list of supplies with the quantity to be ordered [4]** 

```
Class OfficeSupplies (supply_name, supply_ID, maximum_quantity, remainting_quantity)
  string supply_name
  integer supply_ID
  integer maximum_quantity
  integer remaining_quantity
  
  function Get_order_quantity(name, maximum_quantity, remaining_quantity)
    order_quantity = (maximum_quantity - remaining_quantity) 
    return order_quantity
    end function 
    
OfficeSupplies.add("pencil",1242,100,20)
OfficeSupplies.add("stapler",2766,10,7)

```


### Question 10 

A company promotes its products online. To make a purchase, customers are required to register with the company and provide data like their name, date of birth, age, gender and email address. Once registered, more than one customer is able to access the server to retrieve and modify their data at the same time. 

**(c) (i) State where the customer data is held during the process of modifying their data. [1]** 

**(ii) Explain how the operating system ensures that each customer’s data is secure when multiple users are accessing the data at the same time. [4]**

The company is considering sharing its customers’ data with marketing organizations. 

**(d) Explain why there could be ethical issues for the company when sharing its customers’ data. [6]**
