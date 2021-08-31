# Validation Controls In ASP.NET

* Validation is important part of any web application
* An important aspect of creating ASP.NET Web pages for user input is to be able to check that the information users enter is valid.
* ASP.NET provides a set of validation controls that provide an easy-to-use but powerful way to check for errors and, if necessary, display messages to the user.
* There are six types of validation controls in ASP.NET
1. RequiredFieldValidation Control
2. CompareValidator Control
3. RangeValidator Control
4. RegularExpressionValidator Control
5. CustomValidator Control
6. ValidationSummary

* ControlToValidate property is mandatory to all validate controls.
* One validation control will validate only one input control but multiple validate control can be assigned to a input control.

| Validation Control       | 	Description                                                                                      |
|------------------------- | ------------------------------------------                                                        |
| RequiredFieldValidation  | Makes an input control                                                                            |
| CompareValidator         | Compares the value of one input control to another input control                                  |
| RangeValidator           | 	Checks that the user enters a value that falls between two values                                |
| RegularExpressionValidator| Ensures that the value of an input control matches a specified pattern                           |
| CustomValidator           | Allows you to write a method to handle the validation of the value entered                       |
| ValidationSummary         | Displays a report of all validation errors occurred in a Web page                                |

* All validation controls are rendered in form as <span> (label are referred as <span> on client by server)
  
### RequiredFieldValidator Control
  
  <asp:RequiredFieldValidator ID="rfvcandidate" 
   runat="server" ControlToValidate ="ddlcandidate"
   ErrorMessage="Please choose a candidate" 
   InitialValue="Please choose a candidate">
   
</asp:RequiredFieldValidator>
  
  ### RangeValidator Control
  
  <asp:RangeValidator ID="rvclass" runat="server" ControlToValidate="txtclass" 
   ErrorMessage="Enter your class (6 - 12)" MaximumValue="12" 
   MinimumValue="6" Type="Integer">
   
</asp:RangeValidator>
  
  ### CompareValidator Control
  
  <asp:CompareValidator ID="CompareValidator1" runat="server" 
   ErrorMessage="CompareValidator">
   
</asp:CompareValidator>
  
  ### RegularExpressionValidator
  
  <asp:RegularExpressionValidator ID="string" runat="server" ErrorMessage="string"
   ValidationExpression="string" ValidationGroup="string">
   
</asp:RegularExpressionValidator>
  
  ### CustomValidator
  
  <asp:CustomValidator ID="CustomValidator1" runat="server" 
   ClientValidationFunction=.cvf_func. ErrorMessage="CustomValidator">
   
</asp:CustomValidator>
  
  ### ValidationSummary
  
  <asp:ValidationSummary ID="ValidationSummary1" runat="server" 
   DisplayMode = "BulletList" ShowSummary = "true" HeaderText="Errors:" />
   
  
 
  



















