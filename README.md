# Udacity Cloud DevOps Engineer Nanodegree - Capstone Project
Using an **AWS Cloud9** IDE to run the following command that creates an **AWS EKS** (Elastic Kubernetes Service) Cluster.

- **Install eksctl with the following command::**

1.
    ```
        brew install weaveworks/tap/eksctl
    ```
2.
<pre><b>eksctl create cluster</b> \
      --name <b>capstone</b>\
      --version <b>1.18</b>\
      --nodegroup-name <b>workers</b>\
      --node-type <b>t2.medium</b>\
      --nodes <b>2</b>\
      --nodes-min <b>1</b>\
      --nodes-max <b>4</b>\
      --node-ami <b>auto</b>\
      --region <b>us-east-2</b>
</pre>

