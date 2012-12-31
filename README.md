What's "JavaScript SOAP Client"?

A lot of talking about AJAX is taking place here and there; AJAX is the acronym of "Asynchronous JavaScript and XML", a technology based on XMLHttpRequest, which is now supported by all main browsers. The basic idea is quite simple - and not actually a breakthrough - but it allows updating a page following a server request, without reloading the entire set of data.

We propose a solution based on AJAX that has a great advantage with respect to those commonly found in Internet: calls are made to the Web Services.

This permits:
On the server side we only have to expose a Web Service with the required methods (instead of generating dynamic pages incorporating data that are based on a custom syntax or on a generic XML)
On the client side we use the WSDL (Web Service Description Language) to automatically generate a JavaScript proxy class so as to allow using the Web Service return types - that is similar to what Visual Studio does when a Web Reference is added to the solution.

The Client invokes the SOAPClient.invoke method using a JavaScript function and specifying the following:
- Web Service URL (pls note that many browsers do not allow cross-domain calls for security reasons)
- Web method name
- Web header parameter values
- Web method parameter values
- Call mode (async = true, sync = false)
- CallBack method invoked upon response reception (optional for sync calls)

The SOAPClient.invoke method executes the following operations (numbers refer to the previous diagram)
1. It gets the WSDL and caches the description for future requests
2. It prepares and sends a SOAP request to the server (invoking method and parameter values)
3. It processes the server reply using the WSDL so as to build the corresponding JavaScript objects to be returned
4. If the call mode is async, the CallBack method is invoked, otherwise it returns the corresponding object

See also
- More info at http://www.guru4.net/articoli/javascript-soap-client/en/
- Demos at http://www.guru4.net/articoli/javascript-soap-client/demo/en.aspx
- Italian version at http://www.guru4.net/articoli/javascript-soap-client/
