# Cloud Computing Android Application

A location based discussion or micro forum to help people find best answers to any questions they have, suggestions they need, to group up on local social issues. It is an android application that requires a cloud platform. Here there could be scenarios where the application can expect a high amount of traffic on irregular basis. For instance, there can be a discussion on an upcoming concert in New York, or a new iPhone being launched etc. The users currently participating in the discussion would considerably increase depending on the topic of discussion. Using virtual machines to cover such periods would be beneficial. Splitting cloud attributes into broad categories can simplify the mapping process. The categories used here are cloud infrastructure, cloud storage, cloud platform and cloud applications.


<h3> AWS Architecture </h3>

<table>
  <tr>
      <td>Scenario</td>
      <td>Use Case</td>
      <td>Desired Features</td>
      <td>Services Used</td>
  </tr>
  
   <tr>
      <td>Location based Forum</td>
      <td>Mobile Application</td>
      <td>Scalability + Elasticity</td>
      <td>EC2, RDS, Auto Scaling, ELB, EBS, SNS, SQS, CloudSearch, CloudWatch</td>
  </tr>
</table>

<img src="https://github.com/JanhaviBNYU/Cloud_Computing-Android_Application/blob/master/Pictures/AWS_Architecture.png"/>


<h4>Cloud Infrastructure (IaaS)</h4></br>
<B>Amazon EC2</B> – We are using Amazon Elastic Compute Cloud (Amazon EC2) as IaaS. The simple web service interface allows to display forums, events, trending discussions.</br>
<B>Amazon S3</B> – Storing large write once, read many type of objects. To store forum archives, image files, any media file uploaded by subscriber Amazon S3 is used.</br>
<B>Elastic LoadBalancing</B> - It will automatically distributes incoming application traffic across multiple EC2 instances. This will handle the scenario discussed in the beginning about increasing traffic at irregular intervals. In addition to that, it will also detect unhealthy EC2 instances and automatically re-routes traffic to the healthy ones.</br>
<B>Auto Scaling</B> - Since we are using Amazon Cloud Watch, it enables Auto Scaling of EC2 instances depending on the capacity or conditions we define.</br>
 
<h4>Cloud Storage</h4></br>
Includes the services that provide database like functionality, unstructured data services, data synchronization and Network Attached Storage (NAS) services</br>
<B>Amazon Relational Database Service (Amazon RDS)</B> – For database like functionality, we are using Amazon RDS that provides features of a familiar MySQL database. Information such as User details, Forum description, Posts by the users, Replies to the posts, Subscriber to the forum etc. are well formulated into schemas in RDS. The major benefit is the flexibility to scale and compute resources or storage capacity by using a single API call.</br>
<B>Amazon Elastic Block Storage(EBS)</B> – It provides block level storage volumes for all EC2  instances. We need to store the data beyond the lifetime of the instance and to store them with high durability multiple in time snapshots are taken so that new volumes can be created. This is applicable to forums which are not currently active or closed long time back.
 
<h4>Cloud Platform (PaaS)</h4>
Cloud platform required to build, test, deploy, run and manage our application in Cloud
AWS Elastic Beanstalk.  Fastest and the simplest way to deploy application on cloud.  By simply using the IDE such as Eclipse we can deploy our application. It gives full control over the AWS resources and can access the underlying resources at any time. Since, Elastic Beanstalk is built using web servers such as Apache HTTP Server, Apache Tomcat it is convenient to port the application.
 
<h4>Cloud Application (SaaS)</h4></br>
<B>Amazon CloudSearch</B> – It’s a managed search solution for the application. When the user wants to search an old post he initiated or currently active forums, this service allows easy integration into application. It will create a search domain where the data related to posts and forum will be uploaded and the search service deploys a highly tuned search index. Search parameters and settings can be changed without re uploading the data.</br>

<B>Amazon Simple Notification Service (SNS)</B> – It is a push messaging service. This service is used to send notifications to the subscribers of the post. Any reply or likes to a post is notified to all the subscribers of that particular post. Besides pushing cloud notifications directly to mobile devices, it will also deliver notifications by SMS text message or email, to Simple Queue Service (SQS) queues, or to any HTTP endpoint.</br>

<B>AWS CloudWatch</B> – To monitor the status of cloud resources, we are using Cloud Watch. It will help to collect and track metrics such as the most trending topic of discussion on a particular day or at particular location. This will help in enabling features like trending topics etc. It will also give system wide visibility into resource utilization and application performance.</br>

<B>Amazon Simple Email Service (Amazon SES)</B> - Although this doesn’t qualify in the current scope of the project, but it shall be used for bulk email sending for marketing or promotional offers, forum suggestions to subscribers depending on their interests or referring friends to join an ongoing discussion which is one of the future roadmaps.</br>

<B>Identity and Access Management (IAM)</B>  This is also one of the future roadmaps of the project where users will be given access to AWS resources after permissions. Roles will be created in IAM and manage permissions to control which operation can be performed by the entity, or AWS service, that assumes the role.
 


