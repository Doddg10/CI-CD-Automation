# CI-CD-Automation-
CI/CD Automation with Jenkins, Terraform, Ansible, and Docker

## 1. Integrate Slack with Jenkins
- **Install Slack Notification Plugin**: I installed the slack notification plugin to enable Slack notifications.
![unnamed](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/7db992eb-77c2-4da7-9433-b236c916d961)

- **System Configuration**: Then I configure Jenkins with Slack from the Slack portion.
  ![unnamed (1)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/f10f1d0f-8b98-42c8-8d9d-a33d71001125)

- **Workspace Setup in Slack App**: Then I went to my workspace in the Slack app (Tools & Settings -> Manage Apps).
![unnamed (2)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/5c9efda6-63d8-41ac-932a-24ce21d2e53e)

- **Add Jenkins CI.**
![unnamed (3)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/19943280-e642-4302-8115-c11476368b17)

- **Choose the channel.**

- **I followed the step instructions provided.**
![unnamed (4)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/83f6620e-525c-401b-9752-37c1c943f809)

- **Test Connection**: Clicked test connection to ensure the connection between Jenkins and Slack is successful.
![unnamed (5)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/23d8ded2-6ee1-428b-aa73-267746007542)

![unnamed (6)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/5e6bdef4-a149-44f8-add3-3449e68bb09d)

## 2. Send Slack Message When Stage in Pipeline is Successful
![unnamed (7)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/93ae9959-7928-4411-9192-47bf31df4524)

![unnamed (8)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/629283b1-aaca-4ffd-9f88-129c313ae4e9)


## 3. Install Audit Logs Plugin and Test It
![unnamed (9)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/61e71850-f3b6-46a2-b356-2138e39c065d)

![unnamed (10)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/e72ee817-1b2b-493a-a5da-db03f39448e7)

## 4. Fork the following repo https://github.com/mahmoud254/Booster_CI_CD_Project and add dockerfile to run this django app and use github actions to build the docker image and push it to your dockerhub

- **Fokred repo and added Dockerfile**: I created a Dockerfile in the forked repository: [Dockerfile](https://github.com/Doddg10/Booster_CI_CD_Project).
![unnamed (11)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/9897d2ff-51cb-445e-9d33-41a3431c9924)

- **Add DockerHub Credentials**: Add DockerHub credentials as secrets in the repository.
![unnamed (12)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/06afcfa3-35f4-4c52-9675-aa1a216245ad)

- **Push Files to Git Repo**: Push Dockerfile and `.github/workflows/build.yaml` to the Git repository.
![unnamed (13)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/7aaf3bea-bf52-461d-bf50-ec7bc135edc8)
![unnamed (14)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/e862b73b-ecfb-4603-9f17-dfa769663f6e)
![unnamed (15)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/b342001d-95b5-4775-8fec-84a750e0fcf1)
![unnamed (16)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/cbbeae90-a78e-4fcc-97cc-ddfa27337d2a)

## 5. Create Infrastructure Pipeline to Run Terraform with Jenkins
- **First**: 
  - Install Terraform plugin.
  ![unnamed (17)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/aa5d0550-8c4c-4db1-bd48-e2f2ff7a60ec)

  - Add AWS access key credentials.
  ![unnamed (18)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/834e5097-c627-4c11-b2b0-1bdcd974af68)

  - Create pipeline.
  ![unnamed (19)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/9249a97b-b399-47e7-8e34-8e272aee234a)

- **Steps I did for pipeline Execution**:
  - Create an EC2 public instance and install Jenkins and Terraform on it.
  - Configure a public EC2 instance to be a Jenkins slave.
  - Add node to act as a slave in the master.
  - Create pipeline and add script to run on slave agent.
- **Pipeline Script**: Jenkinsfile in infrastructure repository: [Jenkinsfile](https://github.com/Doddg10/Infrastructure-Terraform).
![unnamed (20)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/5c1be23b-c822-488d-9577-ce27cf81fb38)

## 6. Configure Ansible for Application EC2 (Private)
- **Configure Ansible**:
  - Set up ansible to run over private IPs through a bastion (`~/.ssh/config`).
  - I connected to the public EC2 master node.
  - ``` cd ~/.ssh ```
  - ``` vim tf-key-pair.pem ```
  - After pasting the private key I ran the ansible command.
  - Run ansible command:

    ```
    ansible-playbook -i inventory -vvv --private-key tf-key-pair.pem myplaybookjenkins.yaml

    ```
![unnamed (21)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/02f48288-389b-4dc0-aac4-f9fd54358312)

## 7. Ansible Script to Configure EC2 as Jenkins Slaves
- **Ansible Script**: 
  - The ansible script is in `myplaybookjenkins.yaml` uploaded to this repository.

## 8. Configure Slave in Jenkins Dashboard (with Private IP)
- **Agent Node**: It's the **agentt** node.
![unnamed (22)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/691191ca-6094-46d8-ade3-ab9389039bfb)
![unnamed (23)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/1e4f8d47-a54e-47a7-ab86-9426b60dd327)
![unnamed (24)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/c9f9d368-482d-4689-ab74-266f4025bd43)

- **Commands**:
  - I ran these two commands on the private EC2 instance after SSH connection to it through Bastion:
    ```
    curl -sO http://52.91.173.120:8080/jnlpJars/agent.jar
    java -jar agent.jar -url http://52.91.173.120:8080/ -secret fc99c1d801a87749f033c8d3155e5fa1701fed5ec16481b8631cd88be0e9168c -name agent1 -workDir "/home/ubuntu"
    ```

## 9. Create Pipeline to Deploy Node.js Example for Branch (rds_redis)
![unnamed (25)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/dbad3b38-5389-4e0b-9a32-a6d45195588e)
![unnamed (26)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/0ffceb9c-3de3-404f-9eef-02f05ae667cc)

- **Forked Repository**: My forked repository with Jenkinsfile in `rds_redis` branch: [jenkins_nodejs_example](https://github.com/Doddg10/jenkins_nodejs_example).

## 10. Add application load balancer to your terraform code to expose your nodejs app on port 80 on the load balancer
- Added it in Terraform infrastructure code in my repository: [Infrastructure-Terraform](https://github.com/Doddg10/Infrastructure-Terraform).
![unnamed (27)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/f244e150-b484-450b-98f9-a21260f4d496)

## 11. Test Application
- **Test URLs**:
  - Test your application by calling `loadbalancer_url/db` and `/redis`.
![unnamed (1)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/1d7c6eac-f011-4cd8-9a91-f5cde6d82978)
![unnamed](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/d4eb92cf-75c6-4c9c-9ea6-7ff2af4aadd2)


**The intances I used and my pipelines**: 
![unnamed (29)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/99de02d4-60c7-4d1a-a360-c4d1cebf6de7)
![unnamed (28)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/85a4f025-b194-4f2f-bb68-3fc76a94694a)
