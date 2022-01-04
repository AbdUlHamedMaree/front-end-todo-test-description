# **Scandinavia Front-End Test**

At first, I hope you are doing well.

This test is to preview the clean code and how useful you will be to our team.

The test will be about a simple **crud operations** on a **todos list**, the application contains home page that contains the main todos list we want and another page to show a single todo.

## **_The Rules_**

- Create this application using `ReactJs` and `NextJs`.
- Link the application to a public repository on github.
- Organize your repository commits, pushes and branches because it all maters, so organize your work on the git.
- `Axios`, `React Query` and `Material UI` is required libraries to use and any other libraries is optional.
- every page should have at least `title` and `description` meta tags for better SEO.
- Build the same UI showed in the design link by following the same design system.
- Any action performed in the application (create todo, update todo, ...) need to be synced with the backend.

---

## **_The API_**

Here we describe the **_API_** that you should communicate with to archive the goal of the test.

**IMPORTANT**: for each request you should send a query param named with `key` and the value will send to you in the email.

- list the todos

  ```
  GET: /todo
  ```

  the result:

  ```ts
  type ListTodoResponse = {
    _id: string;
    title: string;
    subject: string;
    status: 'todo' | 'doing' | 'done' | 'archive';
  }[];
  ```

  ---
- create a todo

  ```
  POST: /todo
  ```

  you should send the new todo in the request body:

  ```ts
  type CreateTodoDto = {
    title: string;
    subject: string;
  };
  ```

  the result is the new todo:

  ```ts
  type CreateTodoResponse = {
    _id: string;
    title: string;
    subject: string;
    status: 'todo' | 'doing' | 'done' | 'archive';
  };
  ```

  ---
- get a todo

  ```
  GET: /todo/:id
  ```

  you should pass the id of the todo that you want to get in the request query params.

  the result is the requested todo:

  ```ts
  type GetTodoResponse = {
    _id: string;
    title: string;
    subject: string;
    status: 'todo' | 'doing' | 'done' | 'archive';
  };
  ```

  ---
- update a todo

  ```
  PATCH: /todo/:id
  ```

  you should pass the id of the todo that you want to update in the request query params.

  and you should send the updated todo in the request body:

  ```ts
  type UpdateTodoDto = {
    title?: string;
    subject?: string;
    status?: 'todo' | 'doing' | 'done' | 'archive';
  };
  ```

  the result is the updated todo:

  ```ts
  type UpdateTodoResponse = {
    _id: string;
    title: string;
    subject: string;
    status: 'todo' | 'doing' | 'done' | 'archive';
  };
  ```

  ---
- delete a todo

  ```
  DELETE: /todo:id
  ```

  you should pass the id of the todo that you want to delete in the request query params.

  the result is the deleted todo:

  ```ts
  type DeleteTodoResponse = {
    _id: string;
    title: string;
    subject: string;
    status: 'todo' | 'doing' | 'done' | 'archive';
  };
  ```

---

## **_The Point System_**

1. every break rule will reduce you test points
2. the application contains two pages:
   1. `/`: The home.
   2. `/todos/[id]`: Task details.
3. every change in application design not matching the base design will reduce you test points.
4. every change in application design that make the page better will increase your test points.
