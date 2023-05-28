## Deploy-a-Java-Web-Application-to-Tomcat-Server-Using-Jenkins-with-Slack-Notification.
### **DevOps Pipeline Diagram:-**
![java web-app](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Application-To-Tomcat-Server-Using-Jenkins/assets/119833411/3371a8cd-bd08-41c8-983f-38fbffcd3bf9)

### Prerequisites:-
* **Tomcat Server up and running.**
* **Jenkins Server up and running.**
* **Jenkins Integration with Slack Notification.**
* **A Java Project.**

### Reference:-

* **Tomcat Setup** https://github.com/sampathshivakumar/Installations/blob/main/Tomcat%20Installation%20on%20Amazon-Linux-2.md
* **Jenkins Setup** https://github.com/sampathshivakumar/Installations/blob/main/Jenkins%20Installation%20on%20Amazon-Linux-2.md
* **Jenkins Integration with Slack Notification** https://github.com/sampathshivakumar/Integrating-Jenkins-with-Slack-Notifications
* **Java Project** https://github.com/sampathshivakumar/Java-Web-Apps.git

### Install Git in Jenkins Server.
```
# Become a root 
sudo su -

# Install git.
yum install git -y

# Check Version of git.
git version
```
### Open Jenkins in web-browser, click on manage jenkins then select Global Tool Configuration.
![1](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/ac8acf4e-b67f-46e7-bf2d-8a839c5b3e6b)

![2](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/618437d3-626b-474c-be98-e4cff76c279f)

### In Git installations click Add git then select git.
![3](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/94be1c33-0053-4037-82c1-72654464ccce)

![4](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/19a6eb8a-307f-47d7-b0b3-598905f69314)

### Enter Name and Path to Git executable as below then click apply and save.
![5](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/b90410d7-cbce-4276-ad8a-91bbcd433313)

**We have Successfully integrated Git with Jenkins.**

### Now go to Jenkins Dashboard select Manage Jenkins then click on Global Tool Configuration.
![2](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/f6814485-97df-4bc4-af85-6b745de8530d)

### In Maven installations click Add Maven and give name and select Install automatically then Appy and Save.
![6](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/58e362f8-c56f-4315-adc2-cfdb44665b95)

**Maven is also Successfully integrated with Jenkins.**

### Install Deploy to container Plugin.
![10](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/b12f4f5b-b8f3-41db-b7a2-cdb5415746eb)

![11](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/201e6b55-e0b3-43e5-ae12-3ea21324e296)

### Add Tomcat user credentials in Jenkins Secrets.

**You can check it in tomcat-user.xml**
![12](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/4d435b55-1d7f-4f32-b0d6-44df49614e72)

### Go to Manage Jenkins and Click on Credentials.
![13](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/7a3ab980-19c8-4b2b-8c0d-9dfd2d976165)

### Select System.
![14](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/179a4c80-c014-4e06-91dd-43305e38704e)

### Select Global credentials (unrestricted).
![15](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/abc55345-6568-4bdf-8474-527cae6b6a0e)

### Select Add Credentials.
![16](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/497be0a4-58bf-4138-8bdb-b80a2ff6e502)

### Enter username and password.
![17](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/f19feb71-8c5b-4395-a38d-a7f191805c7f)

### Once done you should see like this.
![18](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/858b99b0-1085-4c65-8eb6-3df528a485bd)

### Now lets create a Jenkins job.
![7](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/07583236-a989-426c-9419-ee3d5336ff83)

![9](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/9f558aa6-ec08-4ba2-821a-fc4d83508e0d)

![19](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/b3e17831-6b82-4c25-a499-d931b7c753fc)

![20](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/424f2eed-6422-4b4e-aa8f-13a7fa782f99)

### Provide Build details.
![21](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/124f6c30-4063-43be-b528-1f9bfbb4401a)

### In Post-build Actions click Add Post-build Actions and Select Slack Notification and select following and click apply and save.
![22](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/05432385-9ba9-4cc5-8202-cafafc99765a)

### In Post-build Actions click Add Post-build Actions and Select Deploy war/ear to container.
![image](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/ce3d293d-ec04-462f-be5a-e29cc71aa363)

### Enter the details as following then click on apply and save.
![27](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/71cc91b3-9dcf-463c-bd9e-0310e64d9606)

### Now Click Build Now.
![23](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/afe967a4-85e0-4829-8f43-1c41b7640f87)

### Build Successfull.
![24](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/1ec16222-d77b-4a06-9e85-14384173e046)

### Slack Notifications.
![25](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/c2cb487d-88b7-4c3b-a485-8842208dfcce)

### Output.
![28](https://github.com/sampathshivakumar/Deploy-A-Java-Web-Apps-To-Tomcat-Server-Using-Jenkins-with-Slack-Notification./assets/119833411/ef21efd8-7ba0-473b-ac24-e3aca35ffb7e)

## Project is Successfully Completed.

**Thank you for reading this post! I hope you found it helpful. If you have any feedback or questions,Please connect with me on LinkedIn at https://www.linkedin.com/in/sampathsivakumar-boddeti-1666b810b/. Your feedback is valuable to me. Thank you!
