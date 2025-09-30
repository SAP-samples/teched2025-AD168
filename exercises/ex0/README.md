# Purchase Order Approval Process 

In this exercise we will learn how to use Joule for Developers capabilities of SAP Build in Process Automation. We will use following features to create a sample Purchase Requisition Approval process:

1. Generate Process Template<br>
2. Generate Form<br>
3. Generate Script<br>
4. Generate Business Rules<br>

Note: Save work with each step just to make sure we do not lose out on any information.

## Enable Generative AI option

Login to SAP Build Lobby Navigate to Control Tower and ensure "Enable Generative AI" is enabled.
<br>![](/exercises/ex0/images/GenAI.png)

## Project Creation

1. Login to SAP Build Lobby and Click on create > Process Automation<br>
<br>![](/exercises/ex0/images/ProjectCreation.png)

2.Enter project Name & Description and click Create. This will create a project with given name & description.<br>
<br>![](/exercises/ex0/images/NameDesc.png)

## Process Generation

In this step we will generate Purchase Requisition Approval process template using Generative AI.

1. Click on Generate and select Process<br>
<br>![](/exercises/ex0/images/GenProc.png)

2.Enter following prompt "Generate an empty process template called Purchase Requisition with an approval form" and click on send icon<br>
<br>![](/exercises/ex0/images/GenProcPromt.png)

 System will create a process template and open design editor to continue designing the process<br>
 <br>![](/exercises/ex0/images/ProcTemp.png)

## Form Generation

In this step we will generate a form using Generative AI and use it as Trigger Form to start the process.

1. Click on "+" button after "Add a Trigger" step. From Smart Menu, select Form.<br>
<br>![](/exercises/ex0/images/Form.png)

2.	Enter the prompt to generate PR Submission Form "Create PR Submission Form with fields Company, Supplier, Delivery Address, Delivery Date, Payment Terms, Requested By and Department and a table with fields Item, Description, Quantity, Item Price".<br>
<br>![](/exercises/ex0/images/PRSubForm.png)

3. Once the form is generated, Click on Save.<br>
<br>![](/exercises/ex0/images/Save.png)

4. Click on Add a Trigger, select Submit a Form, choose the form which we created in the last step and Save.<br>
<br>![](/exercises/ex0/images/Trigger.png)

5. Click on ![](/exercises/ex0/images/Arrow.png) to open side process panel, select Variables, configure a process custom variable "Totalprice" (of string type) and Save the process.<br>
<br>![](/exercises/ex0/images/CustomVar.png) <br>![](/exercises/ex0/images/ConCustVar.png)

6. Because we are using Product Information Form to Trigger the process, we will remove it from next step. Select Product Information Form, click on three dots, click on Remove and Save the process.

   


 
4.	Insert this code.
``` abap
 DATA(params) = request->get_form_fields(  ).
 READ TABLE params REFERENCE INTO DATA(param) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.
```

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
