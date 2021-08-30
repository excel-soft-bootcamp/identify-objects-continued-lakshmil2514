# State Management
<p> ASP.NET State management is a preserve state control and object in an application because ASP.NET web applications are stateless.
  * A new instance of the Web page class is created each time the page is posted to the server</P>

<p> ASP.NET offers you a variety of ways to maintain state information on the server,rather than persisting information on the client. 
  * With server-based state management, you can decrease the amount of information sent to the client in order to preserve state, however it can use costly resources on the server.</p>

<p> Techniques are </p>

- Client-Side State Management
  - View State
      1. It is page-level State Management
      2. Used for holding data temporarily
      3. Can store any type of data
      4. Property dependent

public partial class ViwState : System.Web.UI.Page
    {
        int i = 0;
        protected void Page_Load(object sender, EventArgs e)
        {
            if(!IsPostBack)
            {
                ViewState["username"] = i;
            }
        }

        protected void Button1_Click(object sender, EventArgs e)
        {

            i = (int)ViewState["username"];
            Label1.Text = (++i).ToString();
            ViewState["username"] = i; 
        }
    }

  - Hidden field
    1. Contains a small amount of memory
    2. Direct functionality access

public partial class HiddenField : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {

        }
        protected void Button1_Click(object sender, EventArgs e)
        {
            HiddenField1.Value = TextBox1.Text;
        }
        protected void Button2_Click(object sender, EventArgs e)
        {
            Label1.Text = HiddenField1.Value;
        }
    }


  - Cookies
     - Persistent Cookie
     - Non-Persistent Cookie
     1. Store information temporarily
    2. It's just a simple small sized text file
    3. Can be changed depending on requirements
    4. User Preferred
    5. Requires only a few bytes or KBs of space for creating cookies


        protected void Button1_Click(object sender, EventArgs e)
        {
            HttpCookie cookie = new HttpCookie("MyCookie");
            cookie.Value = TextBox1.Text;
            cookie.Expires = DateTime.Now.AddSeconds(15);
            Response.Cookies.Add(cookie);

            Response.Redirect("Home.aspx");

        }
  - Control State
    1. Used for enabling the View State Property
    2. Defines a custom view
    3. View State property declaration
    4. Can't be modified
    5. Accessed directly or disabled
  - Query Strings
    1. It is generally used for holding values
    2.  Works temporarily
    3.  Switches info from one to another page
    4. Increase performance
    5. Uses real and virtual path values for URL routing

protected void Page_Load(object sender, EventArgs e)
        {
            string id = Request.QueryString["id"];
            string name = Request.QueryString["name"];
            Label1.Text = id;
            Label2.Text = name;
        }
- Server-Side 
  - Session State
      1. Maintains the state of user information by using a session ID. 
      2. When users makes a request without a session ID, ASP.NET creates a session ID and sends it with every request and response to the same user.
      3. session_start and session_end special file called Global.asax in the root directory

protected void Button1_Click(object sender, EventArgs e)
        {
            Session["Data"] = TextBox1.Text;
            Response.Redirect("SessionRedirect.aspx");
        }
      
  - Application State
    1. Data stored in the application should be of small size. 
    2. The date stored in application state is common for all users
    3. Application_Error it is raised when an unhandled exception occurs

 protected void Button1_Click(object sender, EventArgs e)
        {
            Application["Data"]=TextBox1.Text;
            Response.Redirect("ApplicationRedirect.aspx");
        }
        
        

###  Client-Side State Management

<p> Whenever we use Client-Side State Management, the state related information will directly get stored on the client-side. 
  * That specific information will travel back and communicate with every request generated by the user then afterwards provides responses after server-side communication.</p>

### Server-side State Management

<p> Server-Side State Management is different from Client-Side State Management but the operations and working is somewhat the same in functionality.
  * In Server-Side State Management all the information is stored in the user memory. 
  * Due to this functionality there is more secure domains at the server side in comparison to Client-Side State Management.</p>