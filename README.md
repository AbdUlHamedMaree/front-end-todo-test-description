# **Scandinavia Front-End Test**

At first, I hope you are doing well.

This test is to preview the clean code and how useful you will be to our team.

The test will be about a simple **crud operations** on a **todos list**, the application contains home page that contains the main todos list we want and another page to show a single todo.

[the design](https://www.figma.com/file/mtltCozpNqhL7x3lBv5uGq/%E2%9C%85--To-Do-List-(Community)?node-id=2%3A490)

## **_The Rules_**

- Create this application using `ReactJs` and `NextJs`.
- Link the application to a public repository on github.
- Organize your repository commits, pushes and branches because it all maters, so organize your work on the git.
- `Axios`, `React Query` and `Material UI` is required libraries to use and any other libraries is optional.
- Every page should have at least `title` and `description` meta tags for better SEO.
- Build the same UI showed in the design link by following the same design system.
- Any action performed in the application (create todo, update todo, ...) need to be synced with the backend.

---

## **_The API_**

Here we describe the **_API_** that you should communicate with to achieve the goal of the test.

**IMPORTANT**: for each request, you should send a query param `key` and you'll receive its value in your test email.

**IMPORTANT**: The base url for the backend is <https://front-end-todo-test.herokuapp.com>, so list todos link will be like <https://front-end-todo-test.herokuapp.com/todos> and so on.

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

1. Every break rule will reduce you test points
2. The application contains two pages:
   1. `/`: The homepage.
   2. `/todos/[id]`: Task details.
3. Every change in application design not matching the base design will cost you test points.
4. Every change in application design that make the page better will grant you extra test points.
