## Coffee Shop
 
This project "Coffee Shop" is a new digitally enabled cafe for students to order drinks, socialize, and study hard. But they need help setting up their menu experience.
It shows my knowledge about building APIs in Flask, I used  in implementing Authentication, Authorization and Permissions. There are three main users
of this web application which are the public, the Barista and Manager. 

This application will:
1. Display graphics representing the ratios of ingredients in each drink.
2. Allow public users to view drink names and graphics.
3. Allow the shop baristas to see the recipe information.
4. Allow the shop managers to create new drinks and edit existing drinks and delete drinks.

The authentication system used for this project is [AUTH0](https://auth0.com/). There is a logic to direct a user to the Auth0 login page, managing the JWT token upon successful callback, and handle setting and retrieving the token from the local store. This token is then consumed by the DrinkService and passed as an Authorization header when making requests to our backend. The Auth0 JWT includes claims for permissions based on the user's role within the Auth0 system. This project makes use of these claims using the auth.can(permission) method which checks if particular permissions exist within the JWT permissions claim of the currently logged in user. This 
determines whether a button will be enabled or disabled on the frontend. 

## Coffee Shop Backend

### Installing Dependencies

#### Python 3.7

Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)

#### Virtual Environment

We recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organized. Instructions for setting up a virtual environment for your platform can be found in the [python docs](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)

#### PIP Dependencies

Once you have your virtual environment setup and running, install dependencies by naviging to the `/backend` directory and running:

```bash
pip install -r requirements.txt
```

This will install all of the required packages we selected within the `requirements.txt` file.

##### Key Dependencies

- [Flask](http://flask.pocoo.org/) is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) and [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/2.x/) are libraries to handle the lightweight sqlite database. Since we want you to focus on auth, we handle the heavy lift for you in `./src/database/models.py`. We recommend skimming this code first so you know how to interface with the Drink model.

- [jose](https://python-jose.readthedocs.io/en/latest/) JavaScript Object Signing and Encryption for JWTs. Useful for encoding, decoding, and verifying JWTS.

## Running the server

From within the `./src` directory first ensure you are working using your created virtual environment.

Each time you open a new terminal session, run:

```bash
export FLASK_APP=api.py;
```

To run the server, execute:

```bash
flask run --reload
```

The `--reload` flag will detect file changes and restart the server automatically.


### Documentation 
> View the [Trivia API Documentation](./backend/README.md)


### Coffee Shop Frontend

### Frontend

The `./frontend` directory contains a complete Ionic frontend to consume the data from the Flask server. You will only need to update the environment variables found within (./frontend/src/environment/environment.ts) to reflect the Auth0 configuration details set up for the backend app.

[View the README.md within ./frontend for more details.](./frontend/README.md)
