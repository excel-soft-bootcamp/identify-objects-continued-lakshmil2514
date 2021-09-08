# View Data
* ViewData is a dictionary of objects that are stored and retrieved using strings as keys.
* It is used to transfer data from Controller to View
* ViewData is of Dictionary type, whereas ViewBag is of dynamic type. However, both store data in the same dictionary internally.
* ViewData is a dictionary, so it contains key-value pairs where each key must be a string.
* ViewData only transfers data from controller to view, not vice-versa. It is valid only during the current request
* Storing data in ViewData −

ViewData["countries"] = countriesList;

* Retrieving data from ViewData −

string country = ViewData["MyCountry"].ToString();

using System.Collections.Generic;
using System.Web.Mvc;
namespace DemoMvcApplication.Controllers{
   public class HomeController : Controller
   {
      public ActionResult Index()  
        {  
            List<string> Courses = new List<string>();  
            Courses.Add("J2SE");  
            Courses.Add("J2EE");  
            Courses.Add("Spring");  
            Courses.Add("Hibernates");  
            ViewData["Courses"] = Courses;  
            return View();  
        }  
   }
}
  <h2>List of Courses</h2>  
    <ul>  
        @{  
            foreach (var Courses in ViewData["Courses"] as List<string>)  
            {  
                <li> @Courses</li>  
            }  
        }  
    </ul>  
       
# View Bag
   
* The ViewBag in ASP.NET MVC is used to transfer temporary data (which is not included in the model) from the controller to the view.
* You can assign any number of properties and values to ViewBag
* If you assign the same property name multiple times to ViewBag, then it will only consider last value assigned to the property.
* ViewBag only transfers data from controller to view, not visa-versa. ViewBag values will be null if redirection occurs.
       
        public ActionResult Index()  
        {  
            List<string> Courses = new List<string>();  
            Courses.Add("J2SE");  
            Courses.Add("J2EE");  
            Courses.Add("Spring");  
            Courses.Add("Hibernates");  
            ViewBag.Courses = Courses;  
            return View();  
        }  
       
       <h2>List of Courses</h2>  
    <ul>  
        @{  
            foreach (var Courses in ViewBag.Courses)  
            {  
                <li> @Courses</li>  
            }  
        }  
    </ul>  
   
   ### Limitations
   
 * ViewBag doesn't require typecasting while retrieving values from it. This can throw a run-time exception if the wrong method is used on the value.
 * ViewBag is a dynamic type and skips compile-time checking. So, ViewBag property names must match in controller and view while writing it manually
   
