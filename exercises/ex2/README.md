# Deploy and Run Process(Variants)
In this exercise, we will learn how to Deploy and Run the process. If process variants are modelled, depending on the start condition, one of the process variant will be triggered and if the start condition does not match any of the variants, the default variant will be triggered as fallback.

## Release and Deploy the project

After completing these steps you will have released and deployed the project...

1. Click on Release to release a version of the template project.
   <br>![](/exercises/ex2/images/Release_Template_Project.png)
2. Create an Environment with name of your user id prefixed by Env (for example , if your userid is user001, then create an Environment with name Envuser001
<br>![](/exercises/ex2/images/Env1.png)
<br>![](/exercises/ex2/images/Env2.png)
3.	Deploy the template project to your Environment that you just now created.
   <br>![](/exercises/ex2/images/Deploy_Template_Project.png)
  	Deployment succeessful message should appear<br>
4. Deploy the Variant project  to your Environment that you just now created.
   <br>![](/exercises/ex2/images/Deploy_PO_Approval_PV.png)
   Deployment succeessful message should appear<br>
  
## Run the Process 

After completing these steps you will learn how to trigger a process which triggers appropriate variant if configured.
If there are no variants configured, the process just runs all the steps configured in it.

1.	Click on Control Tower and the Environnment you created in the previous step.
<br>![](/exercises/ex2/images/ClickEnv.png)
2. Click on More->Processes and Workflows<br>
3. Click on Search and give "Purchase Req"<br>
4.Choose the latest version of "Purchase Requisition Process"<br>
5.Click on Start New Instance<br>
<br>![](/exercises/ex2/images/Start_New_instance.png)
6.Provide the payload , sample payload below :<br>
``` Payload
 {
        "company": "SAP",
        "supplier": "1710",
        "deliveryAddress": "SAP",
        "deliveryDate": "2025-10-06",
        "paymentTerms": "Credit",
        "requestedBy": "SAP BTP",
        "department": "BTP",
        "items": [
            
        ]
    }

``` 
7. Click on "Start New Instance and Close "<br>
8. Click on Show Instances<br>
9. Click on Running instance and you can see that a Task "PR Submission Form" is available <br>
10.This form will be available in the My Inbox, click on My Inbox icon to see this task and further tasks.
   <br>![](/exercises/ex2/images/Running_instance.png)

## Summary

You've now learnt how to model a process using Generative AI features, how to model different process variants with outcomes, parallel steps/branches etc.. and last but not the least, how to release, deploy and trigger a process(variant) in SAP Build Process Automation...

Thank you ! Do reach out to us in case of any other queries.. 
