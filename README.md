# This is Sample Code for Marketing Cloud SSJS POST API Called

This topic I want to share the way to post api from the Server-Sode JavaScript in Marketing Cloud

This script will work under the Automation Studio / Script Activity 

I wrote this one becuase when I try to search this kind of information in the Google or Official Document from Salesforce Marketing Cloud

Most of the Code that I got or found it is not usable at all then I woul like to share this thing to

Marketing Cloud Developer and Developer who is interesting to be a Marketing Cloud Developer

The Script below you can copy and past in the Cloud Page too 


```html
<script runat="server">
    Platform.Load("Core", "1.1.1");

    try {
        // url or endpoint is required 
        var url = "https://sampleApi.com";

        // contentType this parameter is depend on how you want to send data to API
        var contentType = "application/json";

        // payload  is a data you want to send to API
        var requestBody = {
            paramerter: "parameterValue"
        }

        // convert payload from object to string 
        // this process is required becuase Marketiong Cloud Syntaxt is required 
        // the pay load as a string type
        var requestBody = Stringify(requestBody)

        // these are the set of parameter if you want to send header to an API
        var requestHeaderData = ["Header 1","Header 2"];
        var requestHeaderValue = ["Header 1 Value","Header 1 Value"];
        

        // HTTP POST call with parameters
        var response = HTTP.Post(
            url,
            contentType,
            requestBody,
            requestHeaderData,
            requestHeaderValue
        ); 
        
        // Log response from the API
        Write(Stringify(response));
        
    } catch (ex) {
        Write("error message: " + Stringify(ex));
    }
</script>
```
This is Official Document from Salesforce : [Salesforce Document](https://developer.salesforce.com/docs/atlas.en-us.noversion.mc-programmatic-content.meta/mc-programmatic-content/httppost.htm)
