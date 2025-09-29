# Level 1 Heading

In this exercise we will learn how to use Joule for Developers capabilities of SAP Build in Process Automation. We will use following features to create a sample Purchase Requisition Approval process:

Generate Process Template<br>
Generate Form<br>
Generate Script<br>
Generate Business Rules<br>

## Level 2 Heading

Login to SAP Build Lobby Navigate to Control Tower and ensure "Enable Generative AI" is enabled.
<br>![](/exercises/ex0/images/GenAI.png)

2.	Insert this code.
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
