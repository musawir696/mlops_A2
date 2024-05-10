
                                   Roll No:                         i200840
                                   Name:                             Abdul Musawir
                                   Subject:                         Mlops
                                   Assignment:                      ![i200840](https://github.com/musawir696/mlops_A2/assets/112896428/1a4e1e7c-233c-4940-a471-4736d5b65162)
 2
                                   Section:                          CS-B

                                    Pipeline using Airflow

ETL Pipeline Components:
Extraction:
•	The fetch_Dawn _did_you_know() function utilizes the requests library to fetch the HTML content Dawn page.
•	BeautifulSoup is then used to parse the HTML and extract the "Did You Know" section.
•	The function extracts relevant text and cleans it by removing unwanted items and prefixes.
Transformation:
•	The extracted data is then passed to the convert_list_to_json() function, which converts the list of sentences into JSON format.
•	This transformation ensures that the data is structured and ready for storage.
Loading:
•	The transformed JSON data is saved to a file using the save_json_data() function.
Versioning and Pushing Data:
•	The version_and_push_data() function utilizes DVC to version the data and Git to commit and push the changes.
•	This ensures that the data pipeline's output is versioned and accessible for future reference.
3. Airflow DAG Configuration:
•	A DAG (Directed Acyclic Graph) named musawir_etl_dag is defined with specific configurations:
•	Owner: airflow
•	Start date: December 5, 2023
•	Email notification settings: Disabled
•	Retries: 1 retry with a delay of 5 minutes
•	Schedule interval: Daily
•	Catchup: Disabled
4. Task Dependencies:
•	Task dependencies are established to ensure the sequential execution of tasks:
•	Extraction task (extract) depends on no prior task.
•	Transformation task (transform) depends on the extraction task.
•	Load task (load) depends on the transformation task.
•	Versioning task (version_data) depends on the load task.
Airflow Setup and Working 
1. Airflow Installation:
•	Apache Airflow can be installed using pip In Ubuntu.
•	Installation involves setting up dependencies and configuring the Airflow environment.
2. Airflow Components:
•	Airflow consists of several components, including the scheduler, web server, metadata database (usually PostgreSQL), executor, and workers.
•	These components work together to execute and monitor workflows defined as DAGs.
3. DAG Definition:
•	DAGs are defined using Python scripts, specifying tasks and their dependencies.
•	Task definitions include Python functions or external commands to be executed.
4. Airflow Web Interface:
•	Airflow provides a web-based user interface for monitoring and managing DAGs, tasks, and executions.
•	Users can visualize DAG execution status, view task logs, and trigger manual runs through the interface.
Commands and steps:
Steps: 
Step 1: Control Panel | Programs and Features | Turn Windows Features on or off Enable: Windows Subsystems for Linux. 
Step 2: Install Ubuntu from windows store and restart system 
Step 3: Install and update PIP Sudo apt-get install software-properties-common
Sudo apt-add-repository universe 
Sudo apt-get update
Sudo apt-get install python-pip 
Step 4: Install Airflow
Export SLUGIFY_USES_TEXT_UNIDECODE=yes 
pip install apache-airflow 
Step 5: Initialize DB Airflow Initdb 
Step 6: Start airflow server airflow webserver -p 8080 
Step 7: URL is ready: http://localhost:8080/ 
Step 8: step up folder for DAG Create folder DAG in C: drive(C:\DAG) 
Step 9: Add New DAG Run airflow initdb Create A Admin users: airflow users create \ --username admin \ --password xxxx \ --firstname admin \ --lastname admin \ --role Admin \ --email xxx@email.com


 
# mlops_A2
