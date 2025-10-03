# Purchase Order Approval - Process Variants

In this exercise, we will learn how to create different Process Variants for the Purchase Order Approval Process in :<br>

1. Variant Template Editor - Template developer is usually a pro developer and creates the variant template, the default variant.<br>

2. Variant Management Editor - Variant user - usually a business configuration expert - accesses the variant management editor from the tile in your SAP Build Work Zone, standard edition site and creates and defines the order of the variants<br>

## Create Process Variant Template 

1. Click on "Purchase Requisition Process" an open <br>
2. Click on + after "Determine Approver" and choose Variant Template 
<br>![](/exercises/ex1/images/PV_Create.png)
3. Give name as "Purchase Order Variant Template" and Save <br>
4. Click on "Open Variant Template"<br>
5. Click on "Add Steps" and add all the available steps.
<br>![](/exercises/ex1/images/Add_Steps.png) 
6. Steps available in Variant Editor will look as below:
<br>![](/exercises/ex1/images/Available_Steps.png)
7.Click on "Add Default Variant" in the General tab and Create a new one with name "Default Variant" which will act as a fallback if no other variant is created or no other start condition is met
<br>![](/exercises/ex1/images/Default_Variant.png)
8.Click on + after the Process and add Variant Steps to Default Variant
<br>![](/exercises/ex1/images/Add_Default_Variant.png)
9.Add Department Approval Process step to the Default Variant
<br>![](/exercises/ex1/images/Add_Dept_Default_Variant.png)
10..Click on + after the Process , click on Controls and Events and add Branch called "Parallel Branch" to Default Variant
<br>![](/exercises/ex1/images/Add_Parallel_Branch.png),
<br>Parallel branches are created so that 2 or more steps can execute simlataneously without waiting for the previous step to compelete. But all the parallel branches have to be completed before next step can proceed though.<br>
11. Add Steps Finance Approval Process and Legal Department Approval Process as parallel branches
<br>![](/exercises/ex1/images/Add_Fin_Legal_Parallel_Branch.png)
12. Click on + and Add Step Procurement Approval Process. Default Variant finally will look like below:
<br>![](/exercises/ex1/images/Final_Default_Variant.png)
13. <br>Save the Default Variant<br>
14. Click on Variables tab and add attributes
<br>![](/exercises/ex1/images/Add_Variables.png)
15.Add all the attributes from the process context
<br>![](/exercises/ex1/images/Add_Attributes.png)
    1. ApprovalStatus<br>
    2. Totalprice<br>
    3. Approver<br>
    4. Company<br>
    5. DeliveryAddress<br>
    6. DeliveryDate<br>
    7. Department<br>
    8. PaymentTerms<br>
    9. RequestedBy<br>
    10. Supplier<br>
16. Create 2 Global outcomes, one for approved status and one for rejected status. Global outcomes are the overall outcome of a process variant
17. Create a global outcome if overall approval status of all the steps in the variant is "Approved"  <br>
18. Create another global outcome if overall approval status of all the steps in the variant is "Rejected"  <br>
        

   




## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

