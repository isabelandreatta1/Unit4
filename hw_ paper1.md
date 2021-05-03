
## Homework May 3rd - Respond to Paper 1 Questions

### Question 9 

The invetory of office supplies used in the school is stored on a computer as a single file. 

Each of the office supplies in the inventory (such as paper, ink, toner, printers, pens, staplers, pencils and scissors) has a unique ID number, name, maximum quantity and remaining quantity. 

**Outline the steps in an algorithm that would ouput a list of supplies with the quantity to be ordered [4]** 

```
Class OfficeSupplies
  string list = list_of_supplies
  
  function Get_order_quantity(list_of_supplies)
    ouput = []
    loop i from 0 to list_of_supplies.length
      item_name = [i]
      maximum quantity = [i][2]
      remaining_quantity = [i][3]
      order_quantity = (maximum_quantity - remaining_quantity)
      output.append(item_name + order_quantity) 
    end loop 
    return order_quantity
    end function 

print OfficeSupplies(list_of_supplies = ["pencil",1242,100,20],["stapler",2766,10,7]).Get_order_quantity
```


### Question 10 

A company promotes its products online. To make a purchase, customers are required to register with the company and provide data like their name, date of birth, age, gender and email address. Once registered, more than one customer is able to access the server to retrieve and modify their data at the same time. 

**(c) (i) State where the customer data is held during the process of modifying their data. [1]** 

The place when customer data is modified is the RAM, or Random Access Memory. This is the location for temporary storage. 

**(ii) Explain how the operating system ensures that each customer’s data is secure when multiple users are accessing the data at the same time. [4]**

The operating system has multiple security measures that multiple users can not access each other's data. The most common is by providing users an identity and allowing their authentification. Examples of authentification measuress include username and passwords, use log files to trace user activity and therefore allowing unathorised users to be discovered, and even in certain cases, using biometric data. 

The company is considering sharing its customers’ data with marketing organizations. 

**(d) Explain why there could be ethical issues for the company when sharing its customers’ data. [6]**

There are a multitude of ethical issues which could arrise from such event. Firstly, they may be violating the privacy of their users because they never got the explicit consent to share such information with third parties. This infringement of privacy not only may come from the legal violation of privacy, but also by never getting the explicit consent, the user may have not understood the implications. Additionally, by sharing their customer data to a marketing organisation, they company is capitalising off of their customer's data they extrapolated, therefore incentivising to gather more data on their users. Another concern is the manipulation of marketing organisations, since a marketing company may use the data aqcuired to target volunerable users to buy products, as a result of aggressive marketing and exploitive use of data. A less mentioned but importantt ethical concern could be the dehumanisation of the customer, as they are then reduced to numbers and data as a means of making more money. 
