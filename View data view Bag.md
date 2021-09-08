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
   public class HomeController : Controller{
      public ViewResult Index(){
         ViewData["Countries"] = new List<string>{
            "India",
            "Malaysia",
            "Dubai",
            "USA",
            "UK"
         };
         return View();
      }
   }
}
  
  @{
   ViewBag.Title = "Countries List";
}
<h2>Countries List</h2>
<ul>
@foreach(string country in (List<string>)ViewData["Countries"]){
   <li>@country</li>
}
</ul>
