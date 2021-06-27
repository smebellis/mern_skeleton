# MERN Skeleton Code

Establishes skeleton code for quick and easy use in establishing a new MERN WebApp

## Folder and File Structure

- ```
    | mern-simplesetup/
        | -- config/
            | --- config.js
        | -- server/
            | --- controllers/
                | ---- auth.controller.js
                | ---- user.controller.js
            | --- helpers/
                | ---- dbErrorHandler.js
            | --- models/
                | ---- user.model.js
            | --- routes/
                | ---- auth.routes.js
                | ---- user.routes.js
            | --- express.js
            | --- server.js
        | -- client/
            | --- assets/
                | ---- images/
            | --- auth/
                | ---- api-auth.js
                | ---- auth-helper.js
                | ---- PrivateRoute.js
                | ---- Signin.js
            | --- core/
                | ---- Home.js
                | ---- Menu.js
            | --- user/
                | ---- api-user.js
                | ---- DeleteUser.js
                | ---- EditProfile.js
                | ---- Profile.js
                | ---- Signup.js
                | ---- Users.js
            | --- App.js
            | --- main.js
            | --- MainRouter.js
            | --- theme.js
        | -- .gitignore
        | -- .bablerc
        | -- nodemon.json
        | -- package.json
        | -- template.js
        | -- webpack.config.server.js
        | -- webpack.config.client.js
        | -- webpack.config.client.production.js









  ```

## Server-side code

- `models` - This folder is meant to contain all of the Mongoose schema model definitions in separate files, whith each file representing a single model.
- `routes` - This folder contains all routes that allows the client to interact with the server, with routes placed in separate files that may be associates with a model in the `models` folder.
- `controllers` - This folder contains all of the controller functions that define logic to respond to incoming requests at the defined routes. These controllers are divided into separate files corresponding to the relevant model and route files.

## Client-side code

- `auth` - all auth-related components and helper code
- `core` - Common and basic components, such as `Home` and `Menu`
- `post` `user` - all the post-releated or user-releated components

## API Reference

#### User Model

| Field Name | Type     | Description                                                                                                                            |
| :--------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| `name`     | `string` | **Required** field to store the user's name                                                                                            |
| `email`    | `string` | **Required** unique field to store the user's email and identity each account (only one account allowed per unique email)              |
| `password` | `string` | **Required** field for authentication. The database will store the encrpyted password and not the actual string for security purposes. |
| `created`  | `Date`   | Automatically generated timestamp when a new user account is created.                                                                  |
| `updated`  | `Date`   | Automatically generated timestamp when exisiting user details are updated                                                              |

#### API endpoints for user CRUD

| Operation        | route                | HTTP method |
| :--------------- | :------------------- | :---------- |
| `Create a user`  | `/api/users`         | POST        |
| `List all users` | `/api/users`         | GET         |
| `Fetch a user`   | `/api/users/:userId` | GET         |
| `Update a user`  | `/api/users/:userId` | PUT         |
| `Delete a user`  | `/api/users/:userId` | DELETE      |
| `User sign-in`   | `/auth/signin`       | POST        |
| `User signout`   | `/auth/signout`      | GET         |

## Extending the application

- **Extending the Server Code**
  - For a specific feature that will require data persistence and APIs to allow the views to manipulate the data, we can start by extending the server code and adding the necessary models, routes and controller functions.
    - **Adding a model**
      - For the data persistence aspect of the feature, design the data model considering the fields and values that need to be stored. Then, define and export a Mongoose schema for this data model in a separate file, and place it in the `server/models` folder. WItht the data structure defined and ready for the dataase, you can move on to adding the API endpoints for manipulating this data.
    - **Implementing the APIs**
      - In order to manipulate and access the data that will be stored in the database based on the model, you need to design the APIs relevant for the desired feature. To start implementing the APIs, you have to add the corresoonding controller methods and route declarations.
    - **Adding controllers**
      - With the APIs decided, add the corresonding controller functions that will respond to the requests to these APIs in a separate file in the `server/controllers` folder. The controller functions in this file should access and manipulate the data for the model defined for this feature.
    - **Adding routes**
      - To complete the implementation od the backend APIs, corresonding routes need to be declared and mounted on the Express app. In a separate file in the `server/routes` folder, first, declare and export the routes for these APIs, assigning the relevant controller functions that should be executed when a specific route is requested. Then, load these new routes on the Express app in the `server/express.js` file.
- **Extending the client Code**
  - On the client side, first, design the views required for the feature, and determine how these views will incorporate user interaction with the data relevant to the feature. Then, add the fetch API code to integrate with the new backend APIs, define the new components that represent these new views, and update the existing code to include these new components in the frontend of the application.
    - **Adding the API fetch models**
      - Before adding the fetch methods that will make calls to the backend APIS, you will determine a location for placing the new frontend code. In the client folder, create a new folder to house the components and helper code relevant to the feature module being developed. Then, to integrate the new backend APIs with the frontend of the application, define and export the coressponding fetch methods in a separate file in this new components folder. Finally, you can populate this folder with the React components that will be the frontend of this feature.
    - **Adding Components**
      - To start adding the UI for the feature, you can create and export new React components that represents views for the desired feature in separate files in the new folder. If authentication is required, you can integrate it into these new components using the exiting auth-helper methods. Once the React components are implemented, they need to be loaded into the main application view.
    - **Loading new Components**
      - In order to incorporate these new components into the frontend, the components either need to be added into exisitng components or rendered at their own client-side routes.
      - If these new componentsneed to be rendered at individual routes, update the `MainRouter.js` code to add new routes that load these comonents at given URL paths. Then, these URLs can be used as links to load the components from other views in the application, or directly by visiting the URL from the browser address bar.
      - However, if the new components need to becompe part of exisitng views, then import the components into the exisitng components to add them to the view as desired.
      - The new components can also be linked with exisitng components, such as in the `Menu` component, by linking to new components that were added with individual routes.

## Tech Stack

**Client:** React

**Server:** Node, Express

## Acknowledgements

- [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
- [Awesome README](https://github.com/matiassingers/awesome-readme)
- [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)
