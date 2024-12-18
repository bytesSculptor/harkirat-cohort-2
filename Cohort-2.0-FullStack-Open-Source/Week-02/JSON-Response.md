# JSON Response

# How to send JSON response

In an Express.js application, you can send a JSON response using the **`res.json()`** method. This method automatically sets the appropriate Content-Type header to **`application/json`** and sends the JSON-formatted response to the client.

```jsx
const express = require('express');
const app = express();
const port = 3000;

app.get('/get-json', (req, res) => {
  // Create an object to be sent as JSON
  const responseData = {
    message: 'This is a JSON response',
    data: {
      key1: 'value1',
      key2: 'value2',
    },
  };

  // Send the JSON response
  res.json(responseData);
});

app.listen(port, () => {
  console.log(`Server is running on http://localhost:${port}`);
});
```

---

[Postman](./Postman.md)