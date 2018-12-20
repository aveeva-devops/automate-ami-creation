FROM jenkinsslave/aws_cli_docker
MAINTAINER aveevadevops v0.2

RUN apt-get update && \
    apt-get install -y \
        unzip \
        && \
    rm -rf /var/lib/apt/lists/*

RUN wget https://releases.hashicorp.com/packer/0.12.2/packer_0.12.2_linux_amd64.zip && \
    unzip packer_0.12.2_linux_amd64.zip && \
    mv packer /bin/ && \
    rm packer_0.12.2_linux_amd64.zip
RUN wget --quiet https://releases.hashicorp.com/terraform/0.11.11/terraform_0.11.11_linux_amd64.zip \
  && unzip terraform_0.11.11_linux_amd64.zip \
  && mv terraform /usr/bin \
  && rm terraform_0.11.11_linux_amd64.zip
