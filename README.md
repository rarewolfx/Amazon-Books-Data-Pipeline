
# Amazon Books Data Pipeline 
-----------

## About the Project:
The following techstacks were used in this project:

- **Apache Airflow**: For workflow orchestration and scheduling
- **Python**: For data manipulation and scripting within ETL processes
- **PostgreSQL**: For data storage and querying
- **Docker**: For environment setup and containerized deployment
- **SQL**: For data transformation and storage management
## Screenshots
![Screenshot 2024-11-13 004449](https://github.com/user-attachments/assets/8da5aa2f-7c7f-4193-aaef-e04e24649444)

## Create a virtual environment and activate it (optional)

    python -m venv venv
    source venv/bin/activate


# 🔗Important links and Code
-----

## Install Airflow 
-----

Follow steps in the link - https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html

## Install PGAdmin 
-----
Code to add in yaml file

    postgres:
        image: postgres:13
        environment:
          POSTGRES_USER: airflow
          POSTGRES_PASSWORD: airflow
          POSTGRES_DB: airflow
        volumes:
          - postgres-db-volume:/var/lib/postgresql/data
        healthcheck:
          test: ["CMD", "pg_isready", "-U", "airflow"]
          interval: 10s
          retries: 5
          start_period: 5s
        restart: always
        ports:
          - "5432:5432"
    
    pgadmin:

        container_name: pgadmin4_container2
        
        image: dpage/pgadmin4
        
        restart: always
        
        environment:
        
          PGADMIN_DEFAULT_EMAIL: admin@admin.com
          PGADMIN_DEFAULT_PASSWORD: root
          
        ports:
          - "5050:80"
