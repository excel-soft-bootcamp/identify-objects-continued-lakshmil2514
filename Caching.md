# Caching
* Technique of storing frequently used data/information in memory
* Caching is extremely important for performance boosting in ASP.NET
* It is especially important for data related transactions, as these are expensive in terms of response time.
* The data will not be available in the following cases:

1. If its lifetime expires,
2. If the application releases its memory,
3. If caching does not take place for some reason.
* ASP.NET provides the following different types of caching:
 
1. Output Caching
2. Data Caching
3. Object Caching


### Output Chaching 

<%@ OutputCache Duration="15" VaryByParam="None" %>

protected void Page_Load(object sender, EventArgs e)
{
    Label1.Text = DateTime.Now.ToLongTimeString();
   
}

