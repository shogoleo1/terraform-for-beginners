# Use minimal Ubuntu-based devcontainer
FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Install Terraform and AWS CLI
ARG TERRAFORM_VERSION=1.3.7

# root user for installation
USER root

# Install dependencies
RUN apt-get update && \
    apt-get install -y wget unzip python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Install Terraform
RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/ && \
    rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip

# Install AWS CLI
RUN pip3 install --upgrade awscli

# Switch back to non-root user
USER codespace
