# Data Binding in Angular

- Data binding is the core concept of Angular 8 and used to define the communication between a component and the DOM
-  It is a technique to link your data to your view layer
###  Data binding can be either one-way data binding or two-way data binding.
-  In one-way databinding, the value of the Model is used in the View (HTML page) but you can't update Model from the View.
-   Angular Interpolation / String Interpolation, Property Binding, and Event Binding are the example of one-way databinding.
-  In two-way databinding, automatic synchronization of data happens between the Model and the View. 
-  Here, change is reflected in both components. 
-  Whenever you make changes in the Model, it will be reflected in the View and when you make changes in View,it will be reflected in Model.
-  This happens immediately and automatically, ensures that the HTML template and the TypeScript code are updated at all times
-  In two way data binding, property binding and event binding are combined together.
-  For two way data binding, we have to enable the ngModel directive. It depends upon FormsModule in angular/forms package, so we have to add FormsModule in imports[] array in the AppModule.
