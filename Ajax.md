# ASP.NET - Ajax Control
* AJAX stands for Asynchronous JavaScript and XML
* This is a cross platform technology which speeds up response time
* The AJAX server controls add script to the page which is executed and processed by the browser.
*  It is a technique used to create very fast and dynamic web pages.
* The use of AJAX has led to an increase in interactive animation on web pages.
* With AJAX, web applications can retrieve data from the server asynchronously, in the background, without reloading the entire browser page
### The ScriptManager Control
* The ScriptManager control is the most important control and must be present on the page for other controls to work.

* It has the basic syntax:

<asp:ScriptManager ID="ScriptManager1" runat="server">
</asp:ScriptManager>

### The UpdatePanel Control

* The UpdatePanel control is a container control and derives from the Control class.
* For example, if a button control is inside the update panel and it is clicked, only the controls within the update panel will be affected, the controls on the other parts of the page will not be affected. This is called the partial post back or the asynchronous post back.


<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Example.aspx.cs" Inherits="AjaxExample.Example" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
            <asp:ScriptManager ID="ScriptManager1" runat="server"></asp:ScriptManager>
           
            <asp:UpdatePanel ID="UpdatePanel1" runat="server">
                   <ContentTemplate>
                 <asp:Timer ID="Timer2" runat="server" Interval="1000" OnTick="Timer1_Tick"></asp:Timer>
            <asp:Label ID="Label1" runat="server"></asp:Label>
                </ContentTemplate>
            </asp:UpdatePanel>
            
        </div>
    </form>
</body>
</html>

protected void Timer1_Tick(object sender, EventArgs e)
        {
            Label1.Text = DateTime.Now.ToLongTimeString();
        }
### Advantages
* Reduces the traffic travels between the client and the server. 
* Better interactivity and responsiveness.

### Disadvantages

* It is totally built-in JavaScript code. If any user disables JS in the browser, it won't work.
* Security is less in AJAX applications as all the files are downloaded at client side.
