# Difference between ASP.NET Core 5 and ASP.NET MVC 5

### Asp.Net Core
ASP.Net core is a much-upgraded version since it combines apart from ASP.NET MVC also ASP.NET, ASP.NET Web API and ASP.NET web pages.
It combines all of them into a single programming model.


1. Single aligned web stack for ASP.NET Core MVC and Web APIs
    - ASP.NET MVC 5 will allow us to choose MVC or Web API or both while creating a web application. It was because the web stack for MVC 5 and Web API are different. ASP.NET Core 5 now has a single-aligned web stack for MVC and Web API.
2. Project (Solution) Structure Changes
    - If you see ASP.NET Core 5 MVC solution explorer on the right-hand side, there is no Web.config, Global.asax.
Then how it deals with configuration settings, authentication and application start specific code execution.    

3. As ASP.NET Core is almost a combination of NET frameworks, app developers can still run the apps on NET Core even with NET Frameworks.



# CROS

 * CORS Stands for Cross-Origin Resource Sharing
* Using CORS, a server can explicitly allow some cross-origin requests while rejecting others.
* Per action
To specify a CORS policy for a specific action add the [EnableCors] attribute to the action. Specify the policy name.

public class HomeController : Controller
{
    [EnableCors("AllowSpecificOrigin")] 
    public IActionResult Index()
    {
        return View();
    }
}
* Per controller
To specify the CORS policy for a specific controller add the [EnableCors] attribute to the controller class. Specify the policy name.

[EnableCors("AllowSpecificOrigin")]
public class HomeController : Controller
{
}

* Globally
You can enable CORS globally for all controllers by adding the CorsAuthorizationFilterFactory filter to the global filter collection:

public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.Configure<MvcOptions>(options =>
    {
        options.Filters.Add(new CorsAuthorizationFilterFactory("AllowSpecificOrigin"));
    });
}
    
* Disable CORS
To disable CORS for a controller or action, use the [DisableCors] attribute.

    [DisableCors]
    public IActionResult About()
    {
        return View();
    }
