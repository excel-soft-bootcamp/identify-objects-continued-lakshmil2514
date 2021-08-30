# ASP.NET Page Life Cycle

* When a page is requested, it is loaded into the server memory, processed, and sent to the browser. 
* Then it is unloaded from the memory. At each of these steps, methods and events are available, which could be overridden according to the need of the application.
* Understanding the page cycle helps in writing codes for making some specific thing happen at any stage of the page life cycle.
* It also helps in writing custom controls and initializing them at right time, populate their properties with view-state data and run control behavior code.

### The page life cycle phases are:

1. Initialization
2. Instantiation of the controls on the page
3. Restoration and maintenance of the state
4. Execution of the event handler codes
5. Page rendering

#### ASP.NET Page Life Cycle Events

**PreInit** - PreInit is the first event in page life cycle. 
* It checks the IsPostBack property and determines whether the page is a postback. 
* It sets the themes and master pages, creates dynamic controls, and gets and sets profile property values.


**Init** - Init event initializes the control property and the control tree is built.
* During page initialization, controls on the page are available and each control's UniqueID property is set

**InitComplete** - InitComplete event allows tracking of view state. 
* All the controls turn on view-state tracking.

**LoadViewState** - LoadViewState event allows loading view state information into the controls.

**LoadPostData** - During this phase, the contents of all the input fields are defined with the <form> tag are processed.

**PreLoad** - PreLoad occurs before the post back data is loaded in the controls.
 * This event can be handled by overloading the OnPreLoad method 

**Load** - The Load event is raised for the page first and then recursively for all child controls. 
 * The controls in the control tree are created. This event can be handled by overloading the OnLoad method.
 * We can call the validate method and verify that IsValid.
  
**LoadComplete** - The loading process is completed, control event handlers are run, and page validation takes place.
 * This event can be handled by overloading the OnLoadComplete method

**PreRender** - The PreRender event occurs just before the output is rendered. 
 * By handling this event, pages and controls can perform any updates before the output is rendered.

**PreRenderComplete** - As the PreRender event is recursively fired for all child controls, this event ensures the completion of the pre-rendering phase.

**SaveStateComplete** - State of control on the page is saved. Personalization, control state and view state information is saved.
 * The HTML markup is generated. This stage can be handled by overriding the Render method or creating a Page_Render handler.

**UnLoad** - The UnLoad phase is the last phase of the page life cycle. 
 * It raises the UnLoad event for all controls recursively and lastly for the page itself.
 * Final cleanup is done and all resources and references, such as database connections,Instances of classes,in other words objects.
 * This event can be handled by modifying the OnUnLoad method or creating a Page_UnLoad handler.
  
  ## Conculsion 
  
  Therefore we can conclude that whenever a page is requested from the browser by the user, the request would go through a series of steps, 
  and various things would happen in the background so as to produce the output and send the response back to the client.
  The duration between this request and the response of a page is known as the “Page Life Cycle”.



