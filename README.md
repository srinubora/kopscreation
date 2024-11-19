# kopscreation
sudo su -

apt update -y

apt install curl wget apt-transport-https -y

curl -fsSL http://get.docker.com -o get-docker.sh

ll

systemctl start docker 

systemctl status docker

sh get-docker.sh
![Screenshot 2024-11-19 170559](https://github.com/user-attachments/assets/464aba65-843f-4b4b-905c-3be0256bbf96)

sudo curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

ll

chmod +x kubectl

aws configure

snap info aws-cli

snap install aws-cli --channel=v1/stable --classic

curl -LO https://github.com/kubernets/kops/releases/download/v1.25.0/kops-linux-amd64
![Screenshot 2024-11-19 174511](https://github.com/user-attachments/assets/d3b65c67-630b-4815-b77f-8e6a65ef00b3)

chmod +x kops-linux-amd64

ll

mv kops-linux-amd64 /usr/local/bin/kops

mv kubectl /usr/local/bin/kubectl

ll
![Screenshot 2024-11-19 175819](https://github.com/user-attachments/assets/00741c2c-cd50-4ced-9c17-be4353eafac9)
![Screenshot 2024-11-19 212807](https://github.com/user-attachments/assets/c957aafa-a9f7-49ef-bd58-3bd11741f453)

vi  .bashrc

source .bashrc
![Screenshot 2024-11-19 213335](https://github.com/user-attachments/assets/a38a491e-e3e1-4707-8b1d-66de5fb81095)



kubectl version --client --output=yaml

kops version
![Screenshot 2024-11-19 220614](https://github.com/user-attachments/assets/99580087-9d3a-465c-b885-eb0188367975)

aws s3api create-bucket --bucket srinu2025.local --region us-east-1
![Screenshot 2024-11-19 221323](https://github.com/user-attachments/assets/76f5021d-fbc7-4acc-8114-1c23f43a63ea)

aws s3api put-bucket-versionning --bucket srinu2025.local --region us-east-1 --versioning-configuration Status=Enabled
![Screenshot 2024-11-19 221515](https://github.com/user-attachments/assets/52fc781f-09d7-4cb3-ab45-275e13448b6e)


export kpos_state_store=s3://srinu2025.local
![Screenshot 2024-11-19 223142](https://github.com/user-attachments/assets/907b3740-67d1-41b8-b3f9-0c8d320f33b7)
shh-keygen

ll

kops create cluster --name example.k8s.local --state://srinu2025.local--zones us-east-1a --master-size t2.medium --node=size t2.micro

kops update cluster --name example.k8s.local --yes --admin --state=s3://srinu2025.local

kubectl get nodes

	Amazon wed services Aws installed. After see the aws configure and create the IAM user give access keys ,secret keys,region,ouputformat.
