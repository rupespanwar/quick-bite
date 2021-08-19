- https://www.terraform.io/downloads.html
         $ brew install terraform
         $ brew upgrade terraform

 - download the binary :

          wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip

then :

          unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip

then :

          mv terraform /usr/local/bin/

make sure to change ${TERRAFORM_VERSION} by the version you want to install


