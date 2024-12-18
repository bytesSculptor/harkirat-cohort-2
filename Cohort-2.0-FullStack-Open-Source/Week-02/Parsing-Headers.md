# Parsing Headers

# How to parse headers in a GET request

In an Express.js application, you can access headers in a GET request through the **`req.headers`** object in the route handler. The **`req.headers`** object contains all the headers sent with the request, and you can extract and use specific headers as needed.

```jsx
const express = require('express');
const app = express();
const port = 3000;

app.get('/get-info', (req, res) => {
  // Access headers from req.headers
  const userAgent = req.headers['user-agent'];
  const acceptLanguage = req.headers['accept-language'];

  res.json({
    userAgent,
    acceptLanguage,
  });
});

app.listen(port, () => {
  console.log(`Server is running on http://localhost:${port}`);
});
```

----

[Parsing Queries](./Parsing-Queries.md)