# MLflow Sandbox project

## General
The [MLflow](https://mlflow.org/docs/latest/index.html) environment serves as a tracking server for managing the machine learning lifecycle. The repo contains several infrastructure services that start in a Docker stack. 

## Infrastructure services
The Docker stack uses four infrastructure services. These services can be started manually so that you get an MLflow working environment in Docker.
* JupyterLab (docker-container: jupyter)
* MLflow Tracking Server (docker-container: mlflow)
* Artifact Store as SFTP Server (docker-container: sftp)
* Backend Storage as postgres db (docker-container: postgres)

### Start and stop the MLflow workspace
1. Start MLflow workspace: `sh start_docker_stack.sh`
2. Visit [http://127.0.0.1:5001](http://127.0.0.1:5001) for MLflow UI
3. Visit [http://127.0.0.1:8888](http://127.0.0.1:8888) for JupyterLab UI (enter the password `mlflow`)
4. Stop MLflow workspace: `sh stop_docker_stack.sh`

### Test your MLflow workspace setup
* Visit the JupyterLab ([http://127.0.0.1:8888](http://127.0.0.1:8888)) and execute the notebook [mlflow_example.ipynb](notebooks/mlflow_example.ipynb). If no error appears, then your MLflow workspace is set up correctly.

### Adding new dependencies for JupyterLab
* Add new dependencies to file [docker/jupyter/requirements.txt](docker/jupyter/requirements.txt)

## Troubleshooting
* On Linux systems there may be permission problems with the Artifact Store. The current workaround is to set the permissions manually (sudo chmod -R 777). 

## Useful Tools
* SFTP-Server: [Cyberduck](https://cyberduck.io)

## References
* [How to setup an MLflow 2.0 Workspace with Docker?](https://medium.com/dev-genius/how-to-setup-an-mlflow-2-0-workspace-with-docker-7e4938b695e5) / Dec 4, 2022
* [MLFlow-Workspace by Tinztwins](https://github.com/tinztwins/mlflow-workspace)
* [MLFlow official tutorial](https://mlflow.org/docs/latest/tutorials-and-examples/tutorial.html)
