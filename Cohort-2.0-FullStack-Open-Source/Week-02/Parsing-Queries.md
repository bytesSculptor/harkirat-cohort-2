# Parsing Queries

# How to parse query parameters

In an Express.js application, query parameters can be parsed from the URL using the **`req.query`** object. Query parameters are usually included in the URL after the "?" character and separated by "&" ([https://www.google.com/searchq=what+is+query+parameter+in+node+js&sca_esv=589601647](https://www.google.com/search?q=what+is+query+parameter+in+node+js&sca_esv=589601647&sxsrf=AM9HkKl-6hyjsI1zuB3KR3gyWxgy_50Fnw%3A1702233948173&ei=XAd2ZeWNCsCPseMPtLKFyA8&ved=0ahUKEwjlq7jOw4WDAxXAR2wGHTRZAfkQ4dUDCBA&uact=5&oq=what+is+query+parameter+in+node+js&gs_lp=Egxnd3Mtd2l6LXNlcnAiIndoYXQgaXMgcXVlcnkgcGFyYW1ldGVyIGluIG5vZGUganMyBhAAGBYYHjILEAAYgAQYigUYhgMyCxAAGIAEGIoFGIYDMgsQABiABBiKBRiGAzILEAAYgAQYigUYhgNIyw5QvwRYrwxwAXgBkAEBmAG2AaABtQuqAQMwLjm4AQPIAQD4AQHCAgoQABhHGNYEGLADwgIEECMYJ8ICCxAAGIAEGIoFGJECwgIFEAAYgATiAwQYACBBiAYBkAYI&sclient=gws-wiz-serp)).

 Here's a simple example:

```jsx
const express = require('express');
const app = express();
const port = 3000;

app.get('/api/user', (req, res) => {
  // Access query parameters from req.query
  const userId = req.query.id;
  const name = req.query.name;

  // Process the parameters as needed
  const user = {
    id: userId,
    name: name,
  };

  // Send a JSON response with the parsed parameters
  res.json({ user });
});

app.listen(port, () => {
  console.log(`Server is running on http://localhost:${port}`);
});
```


---
[JSON Response](./JSON-Response.md)