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

## Documentation

### Extending the applications

- Extending the Server Code
  - Adding a model
  - Implementing the APIs
    - Adding controllers
    - Adding routes
- Extending the client Code
  - Adding the API fetch models
  - Adding Components
  - Loading new Components

## Tech Stack

**Client:** React

**Server:** Node, Express

## Acknowledgements

- [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
- [Awesome README](https://github.com/matiassingers/awesome-readme)
- [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)
