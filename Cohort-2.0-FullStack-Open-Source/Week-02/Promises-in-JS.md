# Promises in JS

Promises are a JavaScript feature that provides a more structured and readable way to work with asynchronous code. They represent the eventual completion or failure of an asynchronous operation, allowing you to handle the result or error in a more organized and manageable manner.

### **Key Characteristics of Promises:**

1. **Asynchronous Operations:**
    - Promises are commonly used to handle asynchronous operations, such as fetching data from a server, reading a file, or executing a timer.
2. **States:**
    - A promise can be in one of three states:
        - **Pending:** The initial state, before the promise is resolved or rejected.
        - **Fulfilled (Resolved):** The operation completed successfully, and the promise has a resulting value.
        - **Rejected:** There was an error during the operation, and the promise has a reason for the failure.
3. **Chaining:**
    - Promises support chaining through the **`then`** method, allowing you to sequence asynchronous operations in a readable manner.
4. **Error Handling:**
    - Promises have built-in error handling through the **`catch`** method, making it easier to manage and propagate errors in asynchronous code.

### **Why Do We Need Promises?**

1. **Avoiding Callback Hell (Callback Pyramids):**
    - Promises help to mitigate the problem of callback hell, where nesting callbacks leads to unreadable and hard-to-maintain code.
    
    ```jsx
    
    // Without Promises
    asyncOperation1((result1) => {
      asyncOperation2(result1, (result2) => {
        asyncOperation3(result2, (result3) => {
          // ...
        });
      });
    });
    
    // With Promises
    asyncOperation1()
      .then((result1) => asyncOperation2(result1))
      .then((result2) => asyncOperation3(result2))
      .then((result3) => {
        // ...
      });
    
    ```
    
2. **Sequential Execution of Asynchronous Code:**
    - Promises provide a clean way to execute asynchronous operations sequentially, improving code readability.
    
    ```jsx
    
    // Without Promises
    asyncOperation1((result1) => {
      asyncOperation2(result1, (result2) => {
        asyncOperation3(result2, (result3) => {
          // ...
        });
      });
    });
    
    // With Promises
    asyncOperation1()
      .then((result1) => asyncOperation2(result1))
      .then((result2) => asyncOperation3(result2))
      .then((result3) => {
        // ...
      });
    
    ```
    
3. **Error Handling:**
    - Promises simplify error handling by providing a centralized **`catch`** block to handle errors for a sequence of asynchronous operations.
    
    ```jsx
    
    asyncOperation1()
      .then((result1) => asyncOperation2(result1))
      .then((result2) => asyncOperation3(result2))
      .catch((error) => {
        console.error('An error occurred:', error);
      });
    
    ```
    
4. **Promise.all for Parallel Execution:**
    - Promises offer the **`Promise.all`** method, allowing parallel execution of multiple asynchronous operations and waiting for all of them to complete.
    
    ```jsx
    
    const promise1 = asyncOperation1();
    const promise2 = asyncOperation2();
    
    Promise.all([promise1, promise2])
      .then((results) => {
        const result1 = results[0];
        const result2 = results[1];
        // ...
      })
      .catch((error) => {
        console.error('An error occurred:', error);
      });
    
    ```
    

In summary, promises provide a cleaner and more organized way to work with asynchronous code, making it easier to read, write, and maintain. They address common challenges associated with callback-based code and promote better error handling and sequential execution of asynchronous operations.

### **Promises Basics:**

1. **Creating a Promise:**
    - A promise represents the eventual completion or failure of an asynchronous operation.
    - The **`Promise`** constructor takes a function with two parameters: **`resolve`** and **`reject`**.
    
    ```jsx
    
    const myPromise = new Promise((resolve, reject) => {
      // Asynchronous operation goes here
      // If successful, call resolve with the result
      // If there's an error, call reject with the error
    });
    
    ```
    
2. **Resolving a Promise:**
    - Use the **`resolve`** function when the asynchronous operation is successful.
    
    ```jsx
    
    const successfulPromise = new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve('Operation succeeded!');
      }, 1000);
    });
    
    ```
    
3. **Rejecting a Promise:**
    - Use the **`reject`** function when there's an error during the asynchronous operation.
    
    ```jsx
    
    const failedPromise = new Promise((resolve, reject) => {
      setTimeout(() => {
        reject('Operation failed!');
      }, 1000);
    });
    
    ```
    

### **Consuming Promises:**

1. **Using `then` and `catch`:**
    - The **`then`** method is used to handle the resolved value.
    - The **`catch`** method is used to handle errors.
    
    ```jsx
    
    successfulPromise
      .then((result) => {
        console.log(result); // Output: Operation succeeded!
      })
      .catch((error) => {
        console.error(error); // This won't be called in this example
      });
    
    ```
    
2. **Chaining Promises:**
    - Promises can be chained using **`then`**. Each **`then`** returns a new promise.
    
    ```jsx
    
    successfulPromise
      .then((result) => {
        console.log(result); // Output: Operation succeeded!
        return 'New value';
      })
      .then((newValue) => {
        console.log(newValue); // Output: New value
      })
      .catch((error) => {
        console.error(error);
      });
    
    ```
    
3. **Promise All:**
    - **`Promise.all`** is used to wait for multiple promises to complete.
    
    ```jsx
    
    const promise1 = Promise.resolve('One');
    const promise2 = Promise.resolve('Two');
    
    Promise.all([promise1, promise2])
      .then((values) => {
        console.log(values); // Output: ['One', 'Two']
      })
      .catch((error) => {
        console.error(error);
      });
    
    ```
    

 Promises are essential for handling asynchronous code in a clean and readable way, especially when working with features like fetching data from a server, handling events, or working with timers.

---

[Express-Server](./Express-Server.md)
