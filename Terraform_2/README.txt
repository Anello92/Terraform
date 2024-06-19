# Instructions

1. Open the terminal or command prompt and navigate to the folder where you placed the files (do not use spaces or accents in folder names).

2. Run the command below to create the Docker image:

docker build -t pandata-terraform-image:lab .


3. Run the command below to create the Docker container:

docker run -dit --name pandata-lab1 pandata-terraform-image:lab /bin/bash

4. Check the versions of Terraform and AWS CLI with the commands below:

terraform version
aws --version
```