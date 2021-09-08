# Routing 
* ASP.NET MVC routing is a pattern matching system that is responsible for mapping incoming browser requests to specified MVC controller actions.
## Properties of Route
### Route Name:
*  A route is a URL pattern that is mapped to a handler.
*   A handler can be a controller in the MVC application that processes the request.
*  A route name may be used as a specific reference to a given route.
###  URL Pattern:
* A URL pattern can contain literal values and variable placeholders (referred to as URL parameters).
* The literals and placeholders are located in segments of the URL that are delimited by the slash (/) character.
### Defaults:
*  When you define a route, you can assign a default value for a parameter. The defaults is an object that contains default route values.
### Constraints: 
* A set of constraints to apply against the URL pattern to more narrowly define the URL that it matches.

## The Default Route
* The default ASP.NET MVC project templates add a generic route that uses the following URL convention to break the URL for a given request into three named segments
* url: "{controller}/{action}/{id}"
 
This route pattern is registered via call to the MapRoute() extension method of RouteCollection.

// default Route  
routes.MapRoute(  
      name: "Default",  
      url: "{controller}/{action}/{id}",  
      defaults: new { controller = "Home", action = "Index", id = UrlParameter.Optional }  
      
      // Custom Route  
routes.MapRoute(  
  name: "about",  
  url: "Home/About-WDI",  
  defaults: new { controller = "Home", action = "About", id = UrlParameter.Optional }  
);  

## Route Constraints in Asp.Net MVC

routes.MapRoute(
 "Default", // Route name
 "{controller}/{action}/{id}", // Route Pattern
 new { controller = "Home", action = "Index", id = UrlParameter.Optional } // Default values for parameters
);

Restrict to numeric id only

routes.MapRoute(
 "Default", // Route name
 "{controller}/{action}/{id}", // Route Pattern
 new { controller = "Home", action = "Index", id = UrlParameter.Optional }, // Default values for parameters
 new { id = @"\d+" } //Restriction for id
);

http://example.com/Home/Index/1
