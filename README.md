# django-react-webpack

This is Labcodes' boilerplate for django apps with frontend SPAs. We're currently using React and Webpack to manage the frontend.

The boilerplate is PWA, HMR and code splitting ready (and a couple of other acronyms as well).

It's still on beta, so expect little bugs to happen. They shouldn't, but if they pop up, add an issue and we'll get right to it!

## Setup

First of all, we require wget, make, python>=3.6 and nodejs>=8.10 to install our dependencies. On Ubuntu 18.04, you need libpq-dev and python3-dev too.

The easiest way to get started with this boilerplate is to run:

`wget -O - https://raw.githubusercontent.com/labcodes/django-react-webpack/feature\/update/create_project.sh | bash`

It downloads the current code, unpacks it, then sets up nvm and dependencies. You may check the code and run it manually as well, it's inside `create_project.sh' :]

If everything went right, you should have a server running at `localhost:8000`. Visit that on your browser to make sure everything is working <3

## Running it

After installing, when you want to run the project locally, be sure to have your virtualenv active (running `source bin/activate` from the project folder) and nvm set to the correct node version (by running `nvm use` on the project folder). If nvm is not found, try restarting your terminal or running `make node_setup` manually.

Then, to run django and webpack in parallel for development, just run:

`make run`

Since nvm can be a little fiddly, if you have any issues with it, [try reading their documentation](https://github.com/nvm-sh/nvm#installing-and-updating) on how to use it.

## Postinstall

There are a couple of things we suggest you do after installing the boilerplate.

You may want to:

- rename the folder to match your project name;
- move the folder to your preferred folder;
- start a new git repository;
- check `project/settings.py` for variables that need to be customized (PWA related, for example).
