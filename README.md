# mlflow_example

>>> cd code/mlflow_example
>>> python -m venv mlflow_env
>>> source mlflow_env/bin/activate
>>> pip install mlflow
>>> pip install scikit-learn
>>> cd examples
>>> python sklearn_elasticnet_wine/train.py
>>> python sklearn_elasticnet_wine/train.py 0.6 0.7

>>> mlflow ui
and view it at http://localhost:5000.