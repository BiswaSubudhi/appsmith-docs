# JS Objects

Writing extensive code without a full-fledge editor could be challenging. The JavaScript Editor(beta) in Appsmith allows you to create a reusable set of JavaScript functions that you can call within JavaScript bindings across a Page’s component to write complex code with ease. In Appsmith, it’s referred to as `JS Objects`.

{% embed url="https://www.youtube.com/watch?v=tpbY5Jti9d4" %}

### JS Object

A JS Object is an entity comprised of multiple functions and variables. It is a reusable component you can refer to in other JS Objects, allowing you to create a neatly organized set of hierarchies.

**How to Create a JS Object?**

You can create new JS Objects from the Entity Explorer.

Navigate to **Entity Explorer** >> Click (+) next to **Queries/JS** >> Select **New JS Object**.

{% embed url="https://youtu.be/8kzyYaHnwPw" %}
How to add a JS Object?
{% endembed %}

The screen below shows a JS Object added to the page. The default code template that supports [export default](https://developer.mozilla.org/en-US/docs/web/javascript/reference/statements/export).

![When you add a new JS Object](<../../../.gitbook/assets/JavaScript Editor  New JS Object.png>)

1. Give a meaningful name to the JSObject
2. Code editor where you can write JavaScript Code
3. Settings are available for [Async functions](./#asynchronous) only.
4. Define variables
5. Define functions
6. Use the editor to do several jobs, to name a few:
   1. Write your code
   2. Call in-built or user-defined functions
   3. API calls
   4. Database query execution
7. Add multiple functions to the JS Object
8. Access JS Objects from Explorer available under JS Objects Group

{% hint style="info" %}
The support for the named [exports](https://developer.mozilla.org/en-US/docs/web/javascript/reference/statements/export) is not available for exporting functions. However, you can expose functions that are part of the JS Object using **default** export.
{% endhint %}

## Calling a JS Object Function

You can call the functions defined in a JS Object by using the notation `{{ JS_OBJECT_NAME.Function_Name }}` embedded in a mustache sign as shown in the figure below:

![How to call a function defined in a JS Object?](<../../../.gitbook/assets/call\_JS\_object (1) (1) (1) (1) (1) (2) (1) (1) (1) (1) (1) (3) (3) (3) (1) (1).png>)

{% hint style="info" %}
The JS Objects defined are available across APIs, Queries, or other JS Objects defined for **a particular page,** i.e., the JS Objects have **page-level access** and are **not** accessible **across pages**.
{% endhint %}

## Types of JS Functions

You can write different types of functions in a JS Object that can be **Synchronous** or **Asynchronous**.

### Synchronous

As the name suggests, synchronous means to be in a sequence, i.e., every statement of the code gets executed one by one. So, a statement must wait for the earlier statement to complete its execution.

For example, the below code snippet shows a data filter:

```
Api.data.filter(() => {}); // filtering data 
```

Here data filtering is the process of selecting a subset of data you want to choose for viewing or analysis. To filter the data, you must traverse the whole dataset one after the other and segregate it if it matches the filter criteria. Thus, you need synchronous execution.

### Asynchronous

The word asynchronous means not occurring at the same time. You may sometimes need to fetch data from the server or execute a function with a delay, something you do not anticipate occurring at the current time.

For example, `Promises`, `Api.run()`, `Query.Run()`, Appsmith platform functions(eg. `showModal`). It basically lets you delay the execution of code embedded in an async function and is executed when needed.

You can [configure additional settings for the asynchronous function](asynchronous-javascript-function-settings.md) and enhance the user experience.

## Working with JavaScript Editor

JavaScript Editor is an extensive editor that provides additional functionalities while writing code. You can do a lot with it, like:

{% embed url="https://youtu.be/agyvQNFGGIY" %}
A quick walkthrough of JavaScript Editor
{% endembed %}

| **What do you get?**    | **Description**                                                                          |
| ----------------------- | ---------------------------------------------------------------------------------------- |
| **Response Tab**        | Execute each function at the time of development and view the output in the Response tab |
| **Linting Errors**      | Get the linting errors caught right in the editor                                        |
| **Errors Tab**          | Check for the syntax errors in the Errors tab                                            |
| **Logs Tab**            | Check the function execution log in the Logs tab                                         |
| **Snippets**            | Insert ready-to-use snippets                                                             |
| **Debugger Statements** | Use debugger statements to pause the execution                                           |

To understand how JavaScript Editor works, let’s create a **Hello World JS Object**.

* Navigate to **Explorer** >> Click **(+)** for **Queries/JS** >> Select **New JS Object.**
* You’ll see the default code template. Add the below code snippet:

```
export default {
   hello: () => {
      return “Hello World”;
   }
}
```

### Response Tab

The response tab displays the **output** generated by the functions defined in a JS Object.

#### Execute Function

You can click **Run** available on the top right corner to execute the JS function. If your JS object has only one function defined, the editor defaults the function name. But if your JS Object has more than one function defined, you can select the function you want to execute and then click **Run**.

![Response Tab](<../../../.gitbook/assets/JavaScript Editor  Response Tab.png>)

{% hint style="info" %}
If your code has syntax errors, the **Run** button is disabled and blocks the execution. You can resolve the errors and then execute the function using **Run**.
{% endhint %}

You can verify the response generated by the `hello()` in the Response tab, as shown in the screenshot above.

{% hint style="info" %}
You can execute the function by clicking the **RUN** button or by using a shortcut key (**CMD+ENTER** or **CTRL + ENTER**)
{% endhint %}

### Linting Errors

The Javascript Editor automatically checks your source code for programmatic errors. If the code is not programmatically correct, it will highlight the error using a red-colored lint below the erroneous code. For example, the syntax error where the `return` is misspelled as `retu` is also captured by linting.

![Linting also captures the Syntax error and highlights it with a red line below it.](<../../../.gitbook/assets/JavaScript Editor  Linting Errors.png>)

{% hint style="info" %}
You can inspect the `error` in detail from the **Errors** tab.
{% endhint %}

### Errors Tab <a href="#errors-tab" id="errors-tab"></a>

The errors tab displays all types of errors generated by the code execution. The errors could be comprised of **Syntax Errors**, **Run time errors** like **Parsing Errors**, and more.

![Errors Tab](<../../../.gitbook/assets/JavaScript Editor  Error Tab.png>)

### Logs Tab

The Logs tab shows the execution of functions with a timestamp. You can also open the Logs Tab by clicking a debug icon at the right bottom of the console (as shown in the screenshot below).

![Logs Tab](<../../../.gitbook/assets/JavaScript Editor  Logs Tab.png>)

The logs tab gives you the flexibility to filter logs either by writing keywords in the **Filter box** or selecting the **type of log** from the **dropdown**.

### Snippets

You’ll see a Snippets button available on the right top side of the editor. Click on it to open the Appsmith Snippet Library.

![Snippets Button](<../../../.gitbook/assets/JavaScript Editor  Snippets.png>)

#### Appsmith Snippet Library

You can search and copy the Snippets from the Appsmith Snippet Library and use them in the JavaScript Editor. You can then build on the code snippet to add your code or use it as is.

![Appsmith Snippet Library](<../../../.gitbook/assets/JavaScript Editor  Snippets  Appsmith Snippet Library.png>)

{% hint style="info" %}
Appsmith is actively working on expanding the **Snippets Library**. Please reach out to us on[ Discord](https://discord.com/invite/rBTTVJp) or[ Community Forms](https://community.appsmith.com/) if you wish to contribute to the library.
{% endhint %}

### Debugger Statements

The debugger statement in JavaScript will help you pause the code execution during the development phase. The debugger lets you visualize the data and operations when executed on runtime.

You’ll have to use the `debugger` keyword in the code snippet to pause the execution.

{% hint style="info" %}
You must have the **browser’s developer console** **open** to see the debugger in action.
{% endhint %}

{% embed url="https://youtu.be/ZjleR7iM-xo" %}
How to use Debugger statements in JavaScript Editor?
{% endembed %}

For example, you are returning user information fetched from the userDetailsAPI in the JS function, and you want to see the value returned by the API during execution. To get this working, you can use a debugger statement as below:

```
export default {
    getUserDetails: async () => {
        const userInfo = await userDetailsAPI.run();
        debugger; // the execution will be paused at this point 
        // and you can check the value of the userInfo variable
        console.log(“user information: “+userInfo); // the logs will be 
        // printed in the browser 
        // console.
        return userInfo;
    }
}
```

## Writing Complex Code

When you build applications, it’s often more than just a CRUD operation from a single datasource. You might integrate with multiple APIs or want to have the dataset created by querying multiple tables, which leads to traversing data, filtering, or manipulating the response by calling different APIs. You can write complex logic with ease using JavaScript Editor.

To understand it further, let’s look at a use case and build different workflows.

### Use case

You want to create a developer task tracker dashboard, update developer information, and add some permissions like making sure only admins can access the dashboard.

#### Code Workflow

Let’s create a task tracker dashboard that gives you an overview of progress on tasks. You have a query called “_developers_,” which fetches the developers’ information like name, email, etc. You have an API `getAllDeveloperTaskStatus` that gives you a task list with the status for each developer.

**Task Tracker**

You want to display the developer details in a tabular format so that you can choose a table widget. You would want to show a total number of tasks like total tasks, no of completed tasks, no of to-do tasks, and no of in-progress tasks. You can achieve this by adding a JS Object and creating one function in it, “_getTaskList_.” Let’s write the code for this function using the JavaScript Editor.

* In the **Explorer** tab, >> click **(+)** next to `JS Objects` >> Select `New JS Object`.
* It’ll open a JS Editor. Rename the JS Object to `Utils`
* Add the below code snippet in the **Code** tab.

```
export default {
    getAllDeveloperTaskStatus: () => {
    return developers.data.map((developer) => {
     const developerId = developer.id;
     const taskList = developerTaskStatus.data.filter((alltask) => alltask.userId === String(developerId)); // fetch all the tasks for the given developer
     const completedTaskList = taskList.filter((task) => task.status === "Completed"); // fetch tasks that are completed by the developer
     const todoTaskList = taskList.filter((task) => task.status === "To-Do"); // fetch tasks that are not yet started by the developer
     const inProgressTaskList = taskList.filter((task) => task.completed === "In-Progress"); // fetch tasks that are in progress by the developer
     return {
       "Id": developer.id,
       "Name": developer.name,
       "Email": developer.email,
       "Total Tasks": taskList.length,
       "To-Do Tasks": todoTaskList.length,
       "In Progress Tasks": inProgressTaskList.length,
       "Completed Tasks": completedTaskList.length
     };
    })
 }
}
```

The `getAllDeveloperTaskStatus` function does the following:

* Reads all the developers’ data
* Iterates for each developer record
  * Scans the tasklist to fetch the developer-related tasks
    * Based on task status (TO-DO, In-Progress, and Completed)
  * Generate a response that gives a cumulative task breakup for each task status for each developer

To display the response generated by`getAllDeveloperTaskStatus` we'll bind it to a widget.

* Navigate to `Page` >> Select [`Table`](../../../reference/widgets/table/) widget in Widgets Tab >> Drag it onto the canvas.
* Select the `Table` Widget on the canvas
* In the `Property Pane` on right side add the code `{{Utils.getAllDeveloperTaskStatus()}}` in `Table Data` property.

{% embed url="https://youtu.be/HJGOf5ez4eY" %}
Add a Table Widget to display data
{% endembed %}

The [table widget](../../../reference/widgets/table/) will show the data as shown in the below screenshot.

![Display data in a table widget](<../../../.gitbook/assets/JavaScript Editor  Write Complex Code  Bind JS Function Response to Table Widget.png>)

**Update Developer Information**

Let’s add another function where you’ll be able to select a developer record and update the information.

To achieve this, add a new column to the [table widget](../../../reference/widgets/table/) and select the `Column Type` as an `icon button` type that will open a modal window.

{% embed url="https://youtu.be/H85pm7Ae_U8" %}
How to add an edit column to the table widget?
{% endembed %}

Now that the `Edit` column is added to the table let’s add a modal to fetch the `developer` information like `Name` and `Email`.

{% embed url="https://youtu.be/lqC0MzK4s5g" %}
How to add a modal to edit a developer's details?
{% endembed %}

Navigate to Explorer >> Select Utils >> Add the code snippet for `updateUserData()` after `getAllDeveloperTaskStatus()`.

```
export default {
    getAllDeveloperTaskStatus: () => {
        ...// code block for getAllDeveloperTaskStatus
    }, 
    updateUserData: () => {
        // Construct new user's data
        const newUserData = {
            ...Table1.selectedRow,
            name: devName.text,
            email: devEmail.text,
        }
        // Run updateDeveloperDetails query		
        updateDeveloperDetails.run(
            // on successful execution of updateDeveloperDetails run developers to fetch updated data 
            async () => {
                    await developers.run();
                    closeModal("editModal");
                    showAlert("Developer Details are updated successfully!");
                },
                // On Error, close the modal and show an error toast			
                (e) => {
                    closeModal("editModal")
                    showAlert("An error occurred while updating the developer details!");
                    if (e.statusCode === 401) {
                        navigateTo("Page1");
                    }
                },
                // Params Object	
                newUserData)
    }
}
```

The `updateUserData` function does the following:

* Create the dynamic data that is updated by the user in `editModal` in `newUserData` JSON
* Executes query `updateDeveloperDetails`
  * On successful execution of the query:
    * Calls `developers` query to fetch the updated developer details
    * Shows a success toast to the user
    * Closes the `editModal`
  * On error or failed execution of the query
    * Shows an error toast to the user
    * Closes the `editModal`

Rename the `Confirm` button to `Update` and bind the function `updateUserData` to its `onClick()` event. You can bind the function call by using `{{Utils.updateUserData()}}`.

![How to bind function call to an onClick event?](<../../../.gitbook/assets/JavaScript Editor  Edit Modal  Bind UpdateUser Function Call on Update Button (1).png>)

When you'll hit the `Update` button, the `updateUserData` function gets executed that updates the developer information and refreshes the developer table to fetch the updated information.

**Add Permissions**

As you want only the admins to access the Dashboard, let’s create another function for access control. The function will contain a list of users’ emails who will have access to update data in the table. Let’s call this function `isAdmin`.

Add the code snippet for `isAdmin()` and `adminsList` to the `Utils` JS Object.

```
export default {
    adminsList: ["admin1@yourdomain.com", "admin2@yourdomain.com", "admin3@yourdomain.com"],
    getAllDeveloperTaskStatus() => {
        ... // code block for getAllDeveloperTaskStatus
    },
    updateUsersData() => {
        ... // code block for updateUserData
    },
    isAdmin: (email) => {
        if (this.adminList.indexOf(appsmith.user.email) > -1) { // check if the logged in user is an admin
            return true;
        }
        return false;
    }
}
```

The final function will look as below:

```
export default {
    //the allowed list of admin's email
    adminsList: ["admin1@yourdomain.com", "admin2@yourdomain.com", "admin3@yourdomain.com"],
    getAllDeveloperTaskStatus: () => {
        return developers.data.map((developer) => {
            const developerId = developer.id;
            const taskList = developerTaskStatus.data.filter((alltask) => alltask.userId === String(developerId)); // fetch all the tasks for the given developer
            const completedTaskList = taskList.filter((task) => task.status === "Completed"); // fetch tasks that are completed by the developer
            const todoTaskList = taskList.filter((task) => task.status === "To-Do"); // fetch tasks that are not yet started by the developer
            const inProgressTaskList = taskList.filter((task) => task.completed === "In-Progress"); // fetch tasks that are in progress by the developer
            return {
                "Id": developer.id,
                "Name": developer.name,
                "Email": developer.email,
                "Total Tasks": taskList.length,
                "To-Do Tasks": todoTaskList.length,
                "In Progress Tasks": inProgressTaskList.length,
                "Completed Tasks": completedTaskList.length
            };
        })
    },
    updateUserData: () => {
        // Construct new user's data
        const newUserData = {
            ...Table1.selectedRow,
            name: devName.text,
            email: devEmail.text,
        }
        // Run updateDeveloperDetails query		
        updateDeveloperDetails.run(
            // on successful execution of updateDeveloperDetails run developers to fetch updated data  
            async () => {
                    await developers.run();
                    closeModal("editModal");
                    showAlert("Developer Details are updated successfully!");
                },
                // On Error, close the modal and show an error toast		
                (e) => {
                    closeModal("editModal")
                    showAlert("An error occurred while updating the developer details!");
                    if (e.statusCode === 401) {
                        navigateTo("Page1");
                    }
                },
                // Params Object	
                newUserData)

    },
    isAdmin: async () => {
        if (this.adminsList.indexOf(appsmith.user.email) > -1) {
            return true;
        }
        navigateTo("Page2");
        return false;
    }
}
```

{% embed url="https://youtu.be/cuoUVqzhCMo" %}
A user who is not an admin is taken to a no permissions page
{% endembed %}

Only the users with email added to the `adminList` will be able to access the dashboard and do the updates.

With the [Async function settings](asynchronous-javascript-function-settings.md), you can bind the `isAdmin` function to `RUN ON PAGE LOAD`. The execution of `IsAdmin` on Page load ensures the validation of the user’s email against the `adminList` for the logged-in user should happen on the page load. If the logged-in user's email is present in the `adminsList`, the user can access the Dashboard. If not, the user navigates to the access denied page that shows a message:

{% hint style="info" %}
You do not have permission to access the Dashboard.
{% endhint %}

## Current Limitations

As the JavaScript Editor is in its BETA, there are a few limitations:

* At the moment, you cannot use `JS Objects` across pages. We are working to enable this functionality in the future. You can subscribe to[ the issue](https://github.com/appsmithorg/appsmith/issues/1751) and follow the progress.
* You cannot define variables and functions outside of export default { }. In future iterations, we will allow you to write and export only selected variables/functions from a `JS Object`.

![Async Function](<../../../.gitbook/assets/JS\_editor\_async\_function (1).png>)

If a function is async, i.e., if it returns a promise, it cannot be called on the fields incompatible with the return type, such as the default text property of the [text](../../../reference/widgets/text.md) widget. For example, in the above screenshot `executeQuery` returns `Api1.run()` promise and hence is an [async function](./#asynchronous). You can call `executeQuery` or similar functions only from `trigger` or `event` properties such as `OnClick`.
