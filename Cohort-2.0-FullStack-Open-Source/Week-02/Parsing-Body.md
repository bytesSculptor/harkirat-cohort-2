# Parsing Body

# How to parse body in a POST request

To parse the body of a POST request in Express, you can use middleware to handle different types of data formats such as JSON or form data. Express provides built-in middleware for parsing JSON (**`express.json()`**) and form data (**`express.urlencoded()`**).

```jsx
const express = require('express');
const app = express();
const port = 3000;

// Middleware to parse JSON data
app.use(express.json());

// Middleware to parse form data
app.use(express.urlencoded({ extended: true }));

// POST route to handle form data
app.post('/form', (req, res) => {
  const formData = req.body;
  res.json({ receivedData: formData });
});

// POST route to handle JSON data
app.post('/json', (req, res) => {
  const jsonData = req.body;
  res.json({ receivedData: jsonData });
});

app.listen(port, () => {
  console.log(`Server is running on http://localhost:${port}`);
});
```
---

[Parsing Headers](./Parsing-Headers.md)