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
<br>![](/exercises/ex0/images/CustomVar.png)<br>
<br>![](/exercises/ex0/images/ConCustVar.png)

7. Because we are using PR Submission Form to Trigger the process, we will remove it from next step. Select Product Information Form, click on three dots, click on Remove and Save the process.
<br>![](/exercises/ex0/images/RemoveForm.png)
   
## Script Generation

In this step we will write a custom script using Generative AI to calculate total price value and assign to custom variable.

1. Click on ‘+’ next to Trigger, select Script Task from smart menu,
<br>![](/exercises/ex0/images/AddScriptTask.png)

2. Click on Open Editor
<br>![](/exercises/ex0/images/OpenEditor.png)

3. Select the existing script and delete it<br>
<br>![](/exercises/ex0/images/DeleteScript.png)

3. Click on Generate, enter the following prompt "Generate script that calculates totalprice by looping through each element in $.context.startEvent.items and calculates totalprice by multiplying $.context.startEvent.items.itemPrice and $.context.startEvent.items.quantity and convert to string and assign to $.context.custom.totalprice"<br>
<br>![](/exercises/ex0/images/GenScript.png)

4. System will generate script, check if script is fine, Accept it, Validate Script, Apply and Save Process.<br>
<br>![](/exercises/ex0/images/Script.png)

 ## Rules Generation
 
 In this step we will create a business rule using Generative AI to dynamically determine approvers of purchase requisitions.

 1. After script task, click on "+", select Decision from smart menu<br>
 <br>![](/exercises/ex0/images/Decision.png)
   
 2. Click on Blank Decision<br>
 <br>![](/exercises/ex0/images/BlankDec.png) 
   
 3. Give the name as "Determine Approver" and click on Create.<BR>
 <br>![](/exercises/ex0/images/CreateDec.png)

 4. Decision will be opened in a new tab, from right side panel create input parameter "Supplier" (string) , output parameter "Approver" (string) and Save the Process.
 <br>![](/exercises/ex0/images/DeterApp.png)
 
 5. Click on Generate, select Generate Rule, enter the following prompt and Save Process:
"create a decision table rule with name "approver determination" to determine approver based on supplier such that if the supplier is 1710, the purchase requisition must be approved by the "adminmanager@sap.com". If supplier is 1720, it must be approved by "procurementmanager@sap.com"

Note: Replace email ID with valid process automation user email id for testing purpose.<br>
<br>![](/exercises/ex0/images/GenRule.png)<br>
<br>![](/exercises/ex0/images/RulePrompt.png)


6. Go back to Purchase Requisition tab, click on ‘+’ button after Script Task, select Decision from smart menu and select Determine Approver decision which we created in last step.


7.	Insert this code.
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
