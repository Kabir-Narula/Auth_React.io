Cookie
A cookie is a name-value pair, that is stored in a web browser, and that has an expiry date and associated domain.

We store cookies in a web browser either with JavaScript or with an HTTP Response header.

document.cookie = 'my_cookie_name=my_cookie_value'   // JavaScript
Set-Cookie: my_cookie_name=my_cookie_value           // HTTP Response Header
The web browser automatically sends cookies with every request to the cookie's domain.

GET http://www.bigfont.ca
Cookie: my_cookie_name=my_cookie_value               // HTTP Request Header
Bearer Token
A bearer token is a value that goes into the Authorization header of any HTTP Request. It is not automatically stored anywhere, it has no expiry date, and no associated domain. It's just a value. We manually store that value in our clients and manually add that value to the HTTP Authorization header.

GET http://www.bigfont.ca
Authorization: Bearer my_bearer_token_value          // HTTP Request Header
JWT and Token Based Authentication
When we do token-based authentication, such as OpenID, OAuth, or OpenID Connect, we receive an access_token (and sometimes id_token) from a trusted authority. Usually we want to store it and send it along with HTTP Requests for protected resources. How do we do that?

Option 1 is to store the token(s) in a cookie. This handles storage and also automatically sends the token(s) to the server in the Cookie header of each request. The server then parses the cookie, checks the token(s), and responds accordingly.

Option 2 is to store the token in local/session storage, and then manually set the Authorization header of each request. In this case, the server reads the header and proceeds just like with a cookie
