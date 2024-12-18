# Understanding ENV

# How to start PORT on an env variable

### Install dotenv package

Install the **`dotenv`** package using npm. This package allows you to load environment variables from a file.

```bash
npm install dotenv
```

### **Create a `.env` File:**

Create a file named **`.env`** in the root of your project. This file will contain your environment variables. Add a variable for the port, for example:

```bash
PORT=3000
```

### **Load Environment Variables in Your Express App:**

In your main Express application file (e.g., **`app.js`** or **`index.js`**), load the environment variables using **`dotenv`**. Add the following lines at the top of your file:

```jsx
require('dotenv').config();
```

### **Use the PORT Environment Variable:**

```jsx
const express = require('express');
const app = express();
const port = process.env.PORT || 3000;

// Rest of your Express app code...

app.listen(port, () => {
  console.log(`Server is running on http://localhost:${port}`);
});
```

### **Run Your Express App:**

```bash
node app.js
```

---

[Parsing Body](./Parsing-Body.md)