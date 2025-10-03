# Purchase Order Approval - Process Variants

In this exercise, we will learn how to create different Process Variants for the Purchase Order Approval Process in :<br>

1. Variant Template Editor - Template developer is usually a pro developer and creates the variant template, the default variant.<br>

2. Variant Management Editor - Variant user - usually a business configuration expert - accesses the variant management editor from the tile in your SAP Build Work Zone, standard edition site and creates and defines the order of the variants<br>

## Create Process Variant Template 

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex1/images/01_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

