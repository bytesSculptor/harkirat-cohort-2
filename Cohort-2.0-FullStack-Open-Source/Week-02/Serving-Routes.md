# Serving Routes

# How to serve different routes

Use the **`app`** object to define routes for different URLs. Routes are defined using HTTP methods (such as **`GET`**, **`POST`**, **`PUT`**, **`DELETE`**, etc.) and specify a callback function that gets executed when a request matches the specified URL and method.

```jsx
const express = require('express');
const app = express();
const port = 3000;

// get route
app.get('/', (req, res) => {
  res.send('Hello from GET route!');
});

// post route
app.post('/add', (req, res) => {
  res.send('Hello from POST route!');
});

// PUT route - updation
app.put('/put/:id', (req, res) => {
  res.send('Hello from PUT route!');
});

//DELETE route 
app.delete('/delete/:id', (req, res) => {
  res.send('Hello from DELETE route!');
});

app.listen(port, () => {
  console.log(`Server is running on http://localhost:${port}`);
});
```


---

[Understanding ENV](./Understanding-ENV.md)