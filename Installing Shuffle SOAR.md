# Installing Shuffle SOAR 

Step1: Make sure you have Docker and docker-compose installed, and that you have a minimum of 2Gb of RAM available.
Step2: Download Shuffle
```
git clone https://github.com/Shuffle/Shuffle
cd Shuffle
```

Step:3 Fix prerequisites for the Opensearch database (Elasticsearch):
```
mkdir shuffle-database                    # Create a database folder
sudo chown -R 1000:1000 shuffle-database  # IF you get an error using 'chown', add the user first with 'sudo useradd opensearch'

sudo swapoff -a                           # Disable swap
```
Step:4 Run docker-compose.
```
docker-compose up -d
```
Step:5 Recommended for Opensearch to work well
```
sudo sysctl -w vm.max_map_count=262144     
```
