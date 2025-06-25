# AWS CloudFormation Templates for Infrastructure Automation

A collection of CloudFormation YAML templates to automate the deployment of AWS infrastructure components, including VPC, EC2, IAM roles, Application Load Balancers (ALB), Auto Scaling Groups (ASG), and Amazon EKS Clusters with Worker Nodes.

---

## 📁 Templates Included

| Template File                          | Description                                  |
|----------------------------------------|----------------------------------------------|
| `VPC-script.yaml`                      | Standalone VPC creation with subnets         |
| `EC2-script.yml`                       | Launch a single EC2 instance                 |
| `EC2+VPC.yaml`                         | Launch EC2 instance inside a custom VPC      |
| `EC2+VPC+IAM.yaml`                     | EC2 + VPC with attached IAM Role             |
| `EC2+VPC+ALB.yaml`                     | EC2 + VPC with Application Load Balancer     |
| `EC2+VPC+ALB+AUTOSCALING.yaml`         | Full Auto Scaling Group with ALB stack       |
| `VPC+EC2+IAM+EKS.yaml`                 | EKS Cluster with IAM and networking          |
| `EC2+VPC+IAM+EKS+WORKER NODES.yaml`    | Full EKS Cluster with Worker Nodes deployment|

---

## 🛠️ Technologies Used

- **AWS CloudFormation (YAML)**
- **Amazon EC2**
- **Amazon VPC**
- **IAM Roles & Policies**
- **Application Load Balancer**
- **Auto Scaling Groups**
- **Amazon EKS**

---

## 📌 Notes

- Ensure IAM roles such as `EKSClusterRole` and `EKSWorkerNodeRole` are unique or not already in use with conflicting policies.
- If using EC2 worker nodes, configure the `aws-auth` ConfigMap after stack creation to enable node communication with the cluster.

---

## 📜 License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## 🤝 Contributing

Contributions are welcome!  
For major changes, please open an issue first to discuss your ideas.

---

## 🚀 Getting Started

### ✅ Prerequisites

- AWS CLI configured (`aws configure`)
- IAM permissions for CloudFormation, EC2, IAM, EKS, and related services

### 🧪 Launch a Template

```bash
aws cloudformation create-stack \
  --stack-name MyStackName \
  --template-body file://templates/EC2+VPC.yaml \
  --capabilities CAPABILITY_NAMED_IAM
