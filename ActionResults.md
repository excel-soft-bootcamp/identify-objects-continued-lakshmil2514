# Action Result

* Action Result is actually a data type. When it is used with action method, it is called return type
* As the name depicts these results are used for returning the content to the browser. There are 7 types of content returning results:

1. ViewResult 
2. PartialViewResult 
3. ContentResult 
4. EmptyResult 
5. FileResult 
6. JsonResult 
7. JavaScriptResult

### View result 
    public ViewResult Index()  
    {  
        return View();  
    }  
    
### PartialViewResult
    public PartialViewResult Index()  
    {  
        return PartialView("Second View");  
    }  
    
   ### ContentResult 
   
         public ContentResult content()
        {
            return Content(
            "<script> alert('Hi! I am from Mysore') </script>"
                );
        }
        
   ### RedirectionResult
   
   public RedirectResult content()
        {
            return Redirect("https://www.google.com");
        }


    
