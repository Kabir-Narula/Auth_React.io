# Web Authentication Mechanisms Overview

## Cookie

A **cookie** is a name-value pair stored in a web browser, which carries information such as user sessions, preferences, and other data used by websites. It has an expiry date and is associated with a specific domain.

### Storing Cookies:

Cookies can be stored in a web browser either through JavaScript or via an HTTP Response header:

- JavaScript:
  ```javascript
  document.cookie = 'my_cookie_name=my_cookie_value';
