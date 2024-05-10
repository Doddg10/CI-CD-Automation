# CI/CD-Automation-
CI/CD Automation with Jenkins, Terraform, Ansible, and Docker

## 1. Integrate Slack with Jenkins
- **Install Slack Notification Plugin**: I installed the slack notification plugin to enable Slack notifications.
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/7db992eb-77c2-4da7-9433-b236c916d961)
</div>

- **System Configuration**: Then I configure Jenkins with Slack from the Slack portion.
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (1)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/f10f1d0f-8b98-42c8-8d9d-a33d71001125)
</div>

- **Workspace Setup in Slack App**: Then I went to my workspace in the Slack app (Tools & Settings -> Manage Apps).
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (2)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/5c9efda6-63d8-41ac-932a-24ce21d2e53e)
</div>

- **Add Jenkins CI.**
- **Choose the channel.**
- **I followed the step instructions provided.**
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (4)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/83f6620e-525c-401b-9752-37c1c943f809)
</div>

- **Test Connection**: Clicked test connection to ensure the connection between Jenkins and Slack is successful.
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (5)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/23d8ded2-6ee1-428b-aa73-267746007542)
    ![unnamed (6)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/5e6bdef4-a149-44f8-add3-3449e68bb09d)
</div>

## 2. Send Slack Message When Stage in Pipeline is Successful
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (7)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/93ae9959-7928-4411-9192-47bf31df4524)
    ![unnamed (8)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/629283b1-aaca-4ffd-9f88-129c313ae4e9)
</div>

## 3. Install Audit Logs Plugin and Test It
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (9)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/61e71850-f3b6-46a2-b356-2138e39c065d)
    ![unnamed (10)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/e72ee817-1b2b-493a-a5da-db03f39448e7)
</div>

## 4. Fork the following repo https://github.com/mahmoud254/Booster_CI_CD_Project and add dockerfile to run this django app and use github actions to build the docker image and push it to your dockerhub
- **Forked repo and added Dockerfile**: I created a Dockerfile in the forked repository: [Dockerfile](https://github.com/Doddg10/Booster_CI_CD_Project).
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (11)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/9897d2ff-51cb-445e-9d33-41a3431c9924)
</div>

- **Add DockerHub Credentials**: Add DockerHub credentials as secrets in the repository.
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (12)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/06afcfa3-35f4-4c52-9675-aa1a216245ad)
</div>

- **Push Files to Git Repo**: Push Dockerfile and `.github/workflows/build.yaml` to the Git repository.
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (13)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/7aaf3bea-bf52-461d-bf50-ec7bc135edc8)
    ![unnamed (14)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/e862b73b-ecfb-4603-9f17-dfa769663f6e)
    ![unnamed (15)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/b342001d-95b5-4775-8fec-84a750e0fcf1)
    ![unnamed (16)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/cbbeae90-a78e-4fcc-97cc-ddfa27337d2a)
</div>

## 5. Create Infrastructure Pipeline to Run Terraform with Jenkins
- **First**: 
  - Install Terraform plugin.
<div style="border: 1px solid #ccc; padding: 10px;">
    ![unnamed (17)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/aa5d0550-8c4c-4db1-bd48-e2f2ff7a60ec)
    ![unnamed (18)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/834e5097-c627-4c11-b2b0-1bdcd974af68)
    ![unnamed (19)](https://github.com/Doddg10/CI-CD-Automation/assets/94852102/9249a97b-b399-47e7-8e34-8e272aee234a
