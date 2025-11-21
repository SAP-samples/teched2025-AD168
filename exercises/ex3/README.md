# Intelligent Approval Recommendations 

In this exercise we will see how **Intelligent Recommendation** feature of **Process Automation** capability of **SAP Build** assist users in making decision to approve or reject specific tasks.<br>

# Context
**Intelligent recommendation** in Process Automation help users make informed decisions on tasks. These recommendations are powered by a trained AI model that analyzes task details and generates a confidence level (a numeric value indicating the likelihood of a correct decision). Users can view this confidence level for each assigned task, allowing them to assess the AI's suggestion and confidently proceed with their approval or rejection actions.

## Details of tenant and login

1. Click to open [Task Center](https://ad168-skhq09xc.launchpad.cfapps.eu10.hana.ondemand.com/site?siteId=0e6b844f-5e77-423d-b661-31875a69365e#Shell-home)
2. Sign in with **tdct3ched1.accounts.ondemand.com** and not the Default Identity Provider
3. User id : **AD168-XXX@education.cloud.sap** 
4. Password : **TechEd25onTour!** 
    - If already signed in with your user number(used for previous exercise), please sign-out and sign-in again with the above credentials.


## Section 1 : Intelligent Recommendation Creation for Specific Task:

> [!IMPORTANT]
> This section is performed by the Task Center Administator. For this exercise, we have have already created and activated the intelligent recommendation model. The model is also trained with some predefined data. You do not have to follow the steps in this section. It is only for information purpose so that you understand how the model are created, activated and trained for intelligent recommendations. 

Below steps explains how an **Intelligent Recommendation** model is created for 'Department Approval Task' of 'Purchase Order Approval process'. 

> [!WARNING]
> **DONOT RUN THESE STEPS**

1. In the Task Center home page click on _Task Center Administration_ tab. <br>
   ![](/exercises/ex3/images/1.TaskCenterHome.png)<br><br>
2. In Task Center Administration tile, navigate to the _Intelligent Recommendations_ tab.<br>
   ![](/exercises/ex3/images/2.TaskCenterAdminHome.png) <br><br>
3. Select **Create Model** option to create a new intelligent recommendation model.<br>
   ![](/exercises/ex3/images/3.IRHome.png) <br><br>
4. In the Create Intelligent Recommendation Model dialog box, provide the following details:
   - Task Provider: Select 'SAPBuildPA5' from the dropdown list.
   - Task Type: Select 'Department Approval Task' from the dropdown list.
   - Model Name: Provide a name for the model, e.g., "Department Approval Intelligent Recommendation".
   - Configure Task Type Attributes:
     - Numerical Attributes: Select attributes whose values might change (e.g., Total Price).
     - Categorical Attributes: Select attributes whose values are definite (e.g., Supplier, Department).

   ![](/exercises/ex3/images/4.CreateIRPayload.png)<br><br>
5. Choose **Create**.<br>
   An intelligent recommendation model is created and is listed under Intelligent Recommendations with the _Preparing Data_ status.
   ![](/exercises/ex3/images/5.CreatedIR.png) <br><br>
6. A click on the recommendation shows the details including task attributes selected.
   ![](/exercises/ex3/images/6.CreatedIRDetail.png) <br><br>
7. The model transitions to _In Training_ status once **1000** tasks have been completed following the creation of the Intelligent Recommendation model.
   ![](/exercises/ex3/images/7.IRInTraining.png) <br><br>
8. The model transitions to _Ready for Activation_ status once training has been successfully completed. 
   The accuracy of the model is displayed at the benchmark section.<br>
   ![](/exercises/ex3/images/8.IRInReadyToActivate.png) <br><br>
   Select **Activate** option.
   ![](/exercises/ex3/images/9.IRActivating.png) <br><br>
9. Once activation is completed, The model transitions to _Active_ state.
   ![](/exercises/ex3/images/10.IRActive.png) <br><br>
10. Now Intelligence recommendation capabilities are accessible to the users.

## Section 2: Intelligent Recommendation Visualization for Approval Tasks: 

In this section, you will navigate to task center application and see recommendations for _Department Approval Task_ of _Purchase Order Approval process_.

1. In the **Task Center** home page click on **Task Center** tile. <br>
   ![](/exercises/ex3/images/12.TaskCenterHomeWithTasks.png)<br><br>
2. In the **Task Typer** filter dropdown select **Department Approval Task**. <br>
   ![](/exercises/ex3/images/13.TaskTypeSelection.png)<br><br>
3. Click on **Go** to filter the tasks! <br>
   ![](/exercises/ex3/images/14.GoInTaskCenter.png)<br><br>
4. You can see **Confidence level** column in the task list. <br>
   If the Confidence Level column is not available in the task table, although it appears in the filters, use the Personalize option (in the top right corner of the table) to display or rearrange the table columns. <br>
   ![](/exercises/ex3/images/15.ConfidenceLevels.png)<br><br>
   _**A higher confidence level encourages positive action on the task!**_

## Summary
Now you know how intelligent recommendations assist users in making approval decisions.
For more information, refer to the official documentation: [Intelligent Recommendations in SAP Build Process Automation](https://help.sap.com/docs/task-center/sap-task-center/configure-intelligent-recommendations-destination).


Thank you! Do reach out to us in case of any other queries... 
