# gleam-dev-container

## About
This repo provides the setup for a dev container using the Remote - Containers plugin on VSCode. For more info on dev containers you can check out this [link](https://code.visualstudio.com/docs/remote/containers)

This dev container sets up a full Gleam development environment that has all necessary project dependencies, starts any extra services (postgres) and runs migrations, etc. Once it's created you'll be able to directly interact with the container from a shell prompt within VSCode.

## Using the Dev Container
Feel free to fork or copy this code and just add it to the root of your Gleam project directory.

Once this code is in your project root, (with the VSCode `Remote - Containers` plugin installed) you should be able to click on the Containers plugin in the bottom left-hand portion of the editor and choose the option "Open in Container" - if you receive a prompt to choose which directory to open, just make sure that it's in the root of the project.

To get this running there is a Dockerfile to define the ubuntu VM (in .devcontainer), a docker-compose.yml to add a postgres service for ecto / the dev environment, a devcontainer.json which outlines which plugins to use, container startup logic, etc. and an (optional) setup.sh file which will execute once the container is created to run Gleam boilerplate for us.

## Notes
* The setup.sh currently isn't in use, but you can add any startup commands here (migrations, etc.) and then you just have to uncomment the line in `devcontainer.json` that has the `"postCreateCommand"` key.
* You can add extra services to the docker compose file - a sample postgres service is already there, it just needs to be uncommented
