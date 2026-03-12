FROM mcr.microsoft.com/devcontainers/base:ubuntu

ARG TERRAFORM_VERSION=1.3.7

USER root

RUN apt-get update && \
    apt-get install -y wget unzip docker.io && \
    rm -rf /var/lib/apt/lists/*

# Add vscode user to docker group
RUN groupadd -f docker && usermod -aG docker vscode

# Install Terraform
RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/ && \
    rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip