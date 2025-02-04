These steps are from https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html. I have just listed out the ones that are needed
I hope these steps are more clear to follow.
  - Create a folder Airflow in your computer
  - Create following folders inside Airflow
      - dags
      - logs
      - plugins
      - config
  - Save the file form the link below in the Airflow folder. Name of the file should be docker-compose.yaml
      - file link https://airflow.apache.org/docs/apache-airflow/2.10.4/docker-compose.yaml
  - create a file with name airflow.cfg in the config folder. Save the file with following 3 lines.
[scheduler]
min_file_process_interval = 30
dag_dir_list_interval = 30

  - Open terminal and navigate to the folder Airflow
    - Run the following commands one after another to start the airflow
        - docker compose up airflow-init
        - docker compose up

# Airflow UI
  - Open the browser and type http://localhost:8080/
  - Use the username and password as airflow
  - You can create new dags in the dags folder and refresh the UI to see the new dags
