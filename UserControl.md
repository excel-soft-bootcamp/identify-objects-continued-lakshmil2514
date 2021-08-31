# User Controls

* ASP.NET allows the users to create controls
* These user defined controls are categorized into:

1. User Controls

These are derived from the System.Web.UI.UserControl class.
These controls have the following characteristics:

* They have an .ascx extension.
* They may not contain any <html>, <body>, or <form> tags.
* They have a Control directive instead of a Page directive.
  
2. Custom Controls
  
  They are compiled into a Dynamic Link Library (DLL) and used as any other ASP.NET server control. They could be created in either of the following way:

* By deriving a custom control from an existing control
* By composing a new custom control combing two or more existing controls.
* By deriving from the base control class.
  
  




















