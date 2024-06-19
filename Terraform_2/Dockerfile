# Using the official Ubuntu image as a base
FROM ubuntu:latest

# Image maintainer
LABEL maintainer="panData"

# Updating system packages and installing necessary dependencies
RUN apt-get update && \
    apt-get install -y wget unzip curl

# Setting the Terraform version
ENV TERRAFORM_VERSION=1.6.4

# Download and install Terraform
RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/ && \
    rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip

# Create the /lab1 directory inside the container
RUN mkdir /lab1

# Copy main.tf to the /lab1 directory in the container
COPY main.tf /lab1/

# Create the Downloads directory and install AWS CLI (for accessing AWS)
RUN mkdir Downloads && \
    cd Downloads && \
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    ./aws/install

# Set the default command to execute when the container starts
CMD ["/bin/bash"]