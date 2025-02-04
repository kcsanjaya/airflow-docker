# Airflow docker setup
These steps are copied from [airflow documentation](https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html). I have just listed out the ones that are needed to quickly setup the Airflow in docker.
I hope these steps are more clear to follow.
  1. Create a folder named `Airflow` in your computer
  2. Create following folders inside Airflow
      - dags
      - logs
      - plugins
      - config
  3. Save the file form the link below in the Airflow folder. Name of the file should be `docker-compose.yaml`
      - file link [docker-compose.yaml](https://airflow.apache.org/docs/apache-airflow/2.10.4/docker-compose.yaml)
  4. Create a file with name `airflow.cfg` in the config folder and copy the following 3 lines to the file. This config is to reduce the time taken to refresh the dags in the UI and can be adjusted as needed.

 ``` 
[scheduler]
min_file_process_interval = 30
dag_dir_list_interval = 30
```

  5. Open terminal and navigate to the folder Airflow
      - Run the following commands one after another to start the airflow
        > docker compose up airflow-init

        > docker compose up -d

# Airflow UI
  - Open the browser and type http://localhost:8080/ (The port can be changed in the `docker-compose.yaml` file if 8080 is already in use)
  - Use the username and password as `airflow` to login
  - You can create new dags in the `dags` folder and refresh the UI to see the new dags