# Preflight request

A CORS preflight request is a CORS request that checks to see if the CORS protocol is understood and a server is aware using specific methods and headers.

```
client asks server if it allow a `DELETE` request with `OPTIONS` Method
-> server allows
-> respond to preflight request /w Access-Control-Allow-Methods
-> clinet requests actual call
```

`OPTIONS` request

The HTTP OPTIONS method requests permitted communication options for a given URL or server.

The OPTIONS method represents a request for information about the communication options available on the request/response chain identified by the Request-URI. This method allows the client to determine the options and/or requirements associated with a resource, or the capabilities of a server, without implying a resource action or initiating a resource retrieval.

---

### references

https://developer.mozilla.org/en-US/docs/Glossary/Preflight_request
https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS
https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html
https://www.youtube.com/watch?v=tcLW5d0KAYE
