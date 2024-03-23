# Web Authentication Mechanisms Overview

## Cookie

A **cookie** is a name-value pair stored in a web browser, which carries information such as user sessions, preferences, and other data used by websites. It has an expiry date and is associated with a specific domain.

### Storing Cookies:

Cookies can be stored in a web browser either through JavaScript or via an HTTP Response header:

- JavaScript:
  ```javascript
  document.cookie = 'my_cookie_name=my_cookie_value';



# JWT and Token-Based Authentication

JWT (JSON Web Tokens) and other token-based authentication methods, such as OpenID or OAuth, provide a secure way to authenticate and authorize users.

## Handling Tokens:
When using token-based authentication, you typically receive an `access_token` and possibly an `id_token` from a trusted authority.

### Option 1: Storing Tokens in Cookies
- **Advantages**: Automatic handling by the browser, including sending with each request and secure storage.
- **How to use**: Store the token(s) in cookies. This can be done as shown in the Cookies section above.

### Option 2: Storing Tokens in Local/Session Storage
- **Store the token** in the browser's local or session storage.
- **Manually set the Authorization header** in each HTTP request.
- **Advantages**: Provides more control to the client application but requires more code to manage.
- **Usage**:
  ```javascript
  // Storing the token in local storage:
  localStorage.setItem('token', 'my_token_value');
  
  // Adding the token to the Authorization header in requests:
  const token = localStorage.getItem('token');
  fetch('http://example.com/api/resource', {
    headers: {
      'Authorization': `Bearer ${token}`
    }
  });

  # Bearer Token

A **bearer token** is a token that is sent in the Authorization header of HTTP requests. Unlike cookies, bearer tokens are not automatically stored or sent by the browser; they must be manually handled by the client application.

## Sending Bearer Tokens:

To send a bearer token with an HTTP request, include it in the Authorization header:

```http
GET http://www.bigfont.ca
Authorization: Bearer my_bearer_token_value

