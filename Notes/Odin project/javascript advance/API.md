Servers that are created for serving data for external use (in websites or apps) are often referred to as APIs or Application Programming Interfaces.

There are multiple ways of requesting data from an API, but all of them basically do the same thing. For the most part, APIs are accessed through URLs,

In most cases, you will have to create an account and request an “API key” from the API service before attempting to fetch data from their endpoints. Once obtained, an API key will usually have to be included with every data request, such as _another_ URL query string parameter
```
https://api.weatherapi.com/v1/current.json?key=11111111111111111&q=london
```
issuing API keys allows an API service to better track abuse of their systems and data. On the other hand, it can also be a way for those services to mitigate and recuperate operating costs

Because your API key is **your** key to these services and data, securing them is an important habit, especially if you are using a paid tier. There are plenty of bots that crawl GitHub repositories solely for hardcoded/unsecured API keys, allowing bad agents to then access and utilize the services and data you’ve paid for

## fetching data
A couple of years ago the main way to access API data in your code was using an `XMLHttpRequest`. This function still works in all browsers, but unfortunately, it is not particularly nice to use. The syntax looks something like this:
```javascript
// Just getting XHR is a mess!
if (window.XMLHttpRequest) { // Mozilla, Safari, ...
  request = new XMLHttpRequest();
} else if (window.ActiveXObject) { // IE
  try {
    request = new ActiveXObject('Msxml2.XMLHTTP');
  }
  catch (e) {
    try {
      request = new ActiveXObject('Microsoft.XMLHTTP');
    }
    catch (e) {}
  }
}

// Open, send.
request.open('GET', 'https://url.com/some/url', true);
request.send(null);
```

## CORS(Cross origin resource sharing)

