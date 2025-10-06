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
  	Deployment succeessful message should appear
5. Deploy the Variant project  to your Environment that you just now created.
   <br>![](/exercises/ex2/images/Deploy_PO_Approval_PV.png)
   Deployment succeessful message should appear
   



## Exercise 2.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
