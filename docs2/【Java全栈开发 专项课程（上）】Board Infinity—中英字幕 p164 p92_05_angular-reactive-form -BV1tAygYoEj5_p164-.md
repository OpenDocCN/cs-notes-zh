# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p164 p92_05_angular-reactive-form -BV1tAygYoEj5_p164-

Hi there in the previous video we learned about angular temperature driven form now in this video we will see what are reactive forms。

 so lets get started。Reactive forms in Angular provide a more flexible and programmatic way to working with forms。

 They are built using the form control form group and form area classes provided by Angular forms module。

 So let's understand and create a basic reactive form with an example。

 So let's go to the V S code here I have basic project ready And let's create a form here along with the template。

 So first of all， I will just。😊。

![](img/e1dd35125651c3e432e121df8d01a43c_1.png)

Sa form。And we can put here form group。And then， we can。Make it equal to my form。

And then we can bind it with a summit even。And then， we can call our。Subummit form。系退。Like this。

And let's close this form tag and inside the form， let's have a label。So we can have a label here。

 let's give it a for as name and lets give it a text as name as well。And then we can have input。

And to this input， Ill just give it a type of text。And let's give it an I D of name。

And let's give a form。Control name。To be just name。

And then we can mention required here at this point。

Then we can create one more label and this would be for email。And then we can have a email text。Here。

For this email， let's also create a input and lets give it a type of email。

And let's give it an ID of email as well and a form control name。To be emailed。Like this。

And next what we have to do is so here we are just giving it a name earlier we were using name now we are using form control name。

 okay。So here we can say email and let's say required as well。Next， we can have a button。

And to this button， we can give it a type of submit。And let's also give it a disabled。

Rebute here and disabled on the basis of we can mention here。My form dot valid。We can say my form。

Dot valid like this。And the text that we want to put in this button is lets say somebody。

So if I click on save。It will throw an error because we have not defined these functions that we are calling right？

So then in that case， let's go to app dot component dops and make this working。So， first of all。

 we have this submit form method and it will just print out form submit。

 this is the form submission logic。Now we are talking about reactive forms。So， first of all。

Let us go to app module lot Ts and for the temporary ribbon forms we use form modules。

 but in the case of reactive forms we use reactive forms module。

So it would be the active forms module and let's import it here as well。

Now let's go to add dotcompent。 Ts and let's start creating some options here。Now。

 what we want to do is。We can say app component。Implement。On in it。

And now we can say my form that we were using， so my form。And this would be linked to form group。

And this form group will be coming from angular forms。And then we can have a constructor。

And in this constructor， we can say private。Form builder。And you can assign it to the form builder。

That is again coming from angular forms。And let's just leave this empty for now。

And then what we can do is。You can just say Nng。Here。On in it。And we can see this。Dot my phone。

To be this start。Form builder。And we can say dot group。And now， we can。

Pass some object here into this method call。And here we can say name we want it to be array。

 and here we can pass empty string。And we can have a validator check so we can save validators。

And again， this validator will come from angular forms so we can see validator start required。

Similarly， we can do this for email as well。And we can just change it to email and then we can say validators are required and we also need to pass the third。

That is validators dot email。 So it will check for email validations as well。O。

So there is a slight change that we have to do here is that it would be my form。

And it would we have to assign it so we can say new form group。Like this。

And next what we have to do is this validator is not required。

And very details do email will come in a single area。So now if I click on save。

 you can see that it has been compiled successfully and let's test out our form。



![](img/e1dd35125651c3e432e121df8d01a43c_3.png)

You can see that initially it is disabled and now if I type let us say name as John and any email ID it is still disabled right that means validation is working but then what if I try to pass a valid email right valid email structure you can see。

So I if I will write here John at thelGmail do com。

 you can see that now the submit button has been enabled and the validation is working fine and if I click on submit you can see the form has been submitted。



![](img/e1dd35125651c3e432e121df8d01a43c_5.png)

![](img/e1dd35125651c3e432e121df8d01a43c_6.png)

So in this example， we use the form builder service to create an instance of form group called my form here。

 so we defined two form controls name and email along with their corresponding validation routes。

The form group is bound to form group directive in the template and individual form controls are bound using form control La here that we used。



![](img/e1dd35125651c3e432e121df8d01a43c_8.png)

Then we use this Nng submit event of the form and that is bound to submit form method in the component which logs the matches to the console upon form submission。

The submit button is disabled if the form is not valid using my form do valid property。So。

 reactive forms are suitable for complex forms with dynamic controls。

 conditional validation or custom form validation rules。

They offer more control and flexibility in handling form inputs and validations。

So this is all for this video， see you in the next video。Thank you。🎼。



![](img/e1dd35125651c3e432e121df8d01a43c_10.png)