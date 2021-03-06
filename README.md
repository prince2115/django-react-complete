# django-react-boilerplate

This is Labcodes' boilerplate for django apps with frontend SPAs. We're currently using React and Vite to manage the frontend.

The boilerplate is PWA, HMR and code splitting ready (and a couple of other acronyms as well).

It's still on beta, so expect little bugs to happen. They shouldn't, but if they pop up, add an issue, and we'll get right to it!

## Setup

First, to install our dependencies, we require:
- wget
- make
- python>=3.6
- [poetry](https://python-poetry.org)
- nodejs>=8.10


On Ubuntu>=18.04, you also need:
- libpq-dev
- python3-dev

The easiest way to get started with this boilerplate is to run:

```sh
wget https://raw.githubusercontent.com/labcodes/django-react-boilerplate/master/create_project.sh --no-cache -P /tmp/ && bash /tmp/create_project.sh
```

It downloads the current code, unpacks it, then sets up nvm and dependencies. You may check the code and run it manually as well, it's inside `create_project.sh` :]

If everything went right, you should have a server running at `localhost:8000`. Visit that on your browser to make sure everything is working <3

### Installing it manually

If the script isn't working or you want to install everything manually, first [download the zip with the boilerplate from github](https://github.com/labcodes/django-react-boilerplate/archive/feature/update.zip), run `poetry shell` to activate the virtualenv, then run `make install_dependencies` to install all dependencies.

With that done, the app is almost ready to be run! You just need to copy the `env.example` file to `.env`, so that the django app has access to evironment variables via python-decouple, then run `python manage.py migrate` to create a dev database, and finally `make run`, so that both vite and django run in parallel.

## Running it

After installing, when you want to run the project locally, be sure to have your virtualenv active (running `poetry shell` from the project folder) and nvm set to the correct node version (by running `nvm use` on the project folder). If nvm is not found, try restarting your terminal or running `make setup_node_environment` manually.

Then, to run django and vite in parallel for development, just run:

```sh
make run
```

Since nvm can be a little fiddly, if you have any issues with it, [try reading their documentation](https://github.com/nvm-sh/nvm#installing-and-updating) on how to use it.

## Testing it

Run the command `pytest` in the main directory, or run the script `make test`.

For coverage report, run the script `make cov`. Your default browser will open with the report for the tests, if all tests pass.

## Adding new dependencies

If you wish to add new dependencies, just note that:

- for python dependencies, use `poetry add name_of_the_dependency` to install and add it to the requirements (`pyproject.toml`);
- to update python dependencies, run `poetry update`;
- for js dependencies, we're using nvm and npm, so be sure to run `nvm use` before running `npm install name_of_the_dependency` or, if it's a development-only dependency, `npm install name_of_the_dependency -D`.

## Postinstall

There are a couple of things we suggest you do after installing the boilerplate.

You may want to:

- rename or move the project folder to your preferred folder (though you [may need to remake your virtualenv to do so](https://stackoverflow.com/questions/32407365/can-i-move-a-virtualenv#answer-58772116));
- start a new git repository;
- add `nvm use` to the end of your `bin/activate` script, so that you're always using nvm whenever the virtualenv is active;
- deactivate the pre-push scripts, if you want ESLint or Black to **not** be run before pushing (just remove the "husky" key inside package.json);
- check `project/settings.py` for variables that need to be customized (PWA related, for example).
