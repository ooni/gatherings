# Pipeline knowledge sharing

## Overview of how the new pipeline works

It's a set of scripts managed by Airflow. You need an ssh tunnel to work with it.

DAG -- a graph of tasks. Airflow doesn't manage data, it manages tasks via DAG. 

The pipeline has some ticks. The unit of Airflow needs to do a significant amount of computation. The task is a unit computation. Right now, for example, there is a task to check if the data was ingested by Chameloen, since we currently have 2 pipelines running together.

Sanitization procedure -- > Raw data is stored forever, but we sanitize it before exposing it to the user. In a way, it replicates the old pipeline.

There are some sanitization checks that don't pass due to formatting reasons.

Eventually the data ends up in postgress database. This is not the best database, but it's good enough. As the raw data storage increases, we will need to consider an alternative.

How to run this:

The code is basically stored in a docker image, so you can use whatever software you like. Airflow is a bunch of python libraries with their own version and you don't want to have conflicts and resolve them. So you have to build a docker image to run the software.

How do you add the docker image to a chain (like described below)? You upload the docker image to docker hub, and then make the pipeline run this image through operations with elevated privileges (Airflow does this through a wraper script, run with sudo). At the end of these basic checks and setups, docker runs something and that's it. 

You update the version in the file, and then you deploy airflow. You can look at the source. DAG itself is maintained in sysadmin repo, because you need to maintain it somewhere. 

```

$ ./play deploy-pipeline.yml -t airflow-dags

```

DAG tasks:

reports_raw_sensor ==> canning ==> reports_raw_cleanup ===> autoclaving ===> meta_pg ===> sanitized_check ===> sanitized_cleanup

Canning = takes all the raw reports and puts them into larger tar files (more effective from compresion prospective)

Auto-claving == normalization and sanitization

Sanitization check == checks if the sanitization is correct by comparing it to that done by the other/older pipeline (Chameleon)

Santization cleanup == cleanup based on the sanitized check

Meta_pg = centrifugation 

How to do this via UI:

1. Go through Airflow UI and use scheduler (but it's imperfect and it has its own issues and it wastes some CPU)

2. Using something like old GNU make (you can make files that will do it a bit more efficiently)

You access the Airflow DAG UI, click on "Tree View", and then click on one of the squares. 

## How to add fingerprints for known block pages?

The fingerprints are part of the schema. The reason for why it's part of schema updates is because we need a way to update that and you need some reference number for each fingerprint, and you want that to be preserved, etc. Eventually we will have some UI (when/if we have dozens of fingerprints per day). The way of storing fingerprints doesn't matter --- what matters is that they will need to be re-processed. 

Fingerprints currently cannot be reprocessed for a single country -- that's quite good, because it allows you to detect them across countries, and censorship keaks are happening often. So enforcing whole data re-processing is actually good.

compat_code_ver and change where needed

Be sure to change a cert fingerprint table. 

Airflow also sends alerts when something fails.

