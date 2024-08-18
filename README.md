# NoSql-MongoDB
NOSL (NoSQL Language) refers to the various query languages used with NoSQL databases. Unlike traditional SQL, NOSL supports diverse data models like document, key-value, and graph formats, allowing flexible and scalable data management. Each NoSQL database has its own query language tailored to its specific model.
       
       Project Overview: Introduction to NoSQL Databases
       Check the lab environment:
    You need the ‘couchimport’ and ‘couchexport’ tools to move data in and out of the Cloudant database.
    https://github.com/user-attachments/assets/39531fa7-0c7e-466b-bfd8-b962683ed1ad
        https://github.com/user-attachments/assets/51f421d6-ceb8-4e4d-a4fa-6a48d8935682

    You need to obtain the content of the json file and copy the entire content: movies.json

    Create a new file named movie.json under the project directory and paste the entire content copied earlier into the newly created json file.

    Go to your Cloudant Service created on IBM Cloud and then click on Launch Dashboard to launch the cloudant databases. Then, click on New database on the top-right corner and create a Non-patitioned database named movies.
    1. Log in to IBM Cloud
    You need an IBM Cloud account to work with IBM Cloudant.
     If you do not have an account, you can sign up for one using the 
    instructions here.
    Step 1: Navigate to cloud.ibm.com.
    Step 2: Login using your IBM cloud credentials.
    You will land on the the Cloud Dashboard page.
    
    2.Create an IBM Cloudant instance
    Step 1: Click on cloud.ibm.com/catalog/services/cloudant to create a 
    Cloudant instance.
    Or you can alternatively click on Create Resource, search for Cloudant 
    on the Dashboard page.
    You will be taken to the Cloudant instance creation page.
      https://github.com/user-attachments/assets/bbcc0fa2-fc4a-437f-926c-db2e6233b7ef

    Step 2: Select the region under the “Available regions”.
    It is OK to go with the default option, if you cannot figure out which 
    region to choose.
    Step 3: Scroll down to configure Cloudant instance.
    https://github.com/user-attachments/assets/36347ed7-bb3a-46d7-a6da-607dd0985c23

    
    Step 4: Set your instance name to mycloudant or anything else that you prefer.
    Step 5: Authentication Method is a critical setting. Select “IAM and legacy Credentials” as your Authentication Method. If you choose any other Authentication Method, some labs will not work. Step 6: Select the Lite plan.
    Step 7: Click on Create
              https://github.com/user-attachments/assets/40aff0cf-9249-4a5d-9707-76024de97f57

    
    You should see a screen like this
    Your Cloudant service will be created and you will be redirected to the Resource list page.
    Step 8: If you are not redirected, you can click on this link cloud.ibm.com/resources?groups=resource-instance
    You may see a screen like this, indicating the Provision in progress.
      https://github.com/user-attachments/assets/d2460f4a-1104-463b-ad3b-17f1a4e2968f

    
    Step 9: Wait till the status turns ‘Active’ and click on mycloudant or your custom instance name.
    https://github.com/user-attachments/assets/a82b5ce8-2a3f-4375-90ec-aa907ca550fe

    
    3.Create Cloudant Service credentials
         Step 1: On the Cloudant instance page, click on Service Credentials
     https://github.com/user-attachments/assets/a144ee4b-8ded-4db3-8b08-9375f6d41dfa

        Step 2: Click on New Credential.
        https://github.com/user-attachments/assets/d286e55c-16a6-4e44-9701-6c7a81c532e0
  
          Step 3: Create credential pop up appears. Accept the default 
         values for Name and Role and click on Add
     https://github.com/user-attachments/assets/c8f4e545-36ff-4086-833d-441866fb2b9f

         
          Step 4: Your Cloudant Service credentials will be created. Click 
          on the chevron to view the credentials.
     DO NOT attempt to use the credentials shown here. These are expired 
       credentials.
       https://github.com/user-attachments/assets/fd3972fd-9459-4d67-82d3-63f25b495807


       Step 5: You will be using the username, password and url in the next labs.
        https://github.com/user-attachments/assets/885e302e-cc0a-4532-905c-6f9723f03dc3

       You have successfully created a Cloudant instance and Service 
        credentials for your instance.

    Note: If you do not see the password field in your credentials, it is because you have not selected “IAM and legacy credentials”. You can fix it by deleting your current Cloudant instance and following this lab from the beginning to create a new instance of Cloudant.


    #Export the json into your Cloudant Database:
    Go to your Cloudant Service created on IBM Cloud and then click on Launch Dashboard to launch the cloudant databases. Then, click on New database on the top-right corner and create a Non-patitioned database named movies.
    https://github.com/user-attachments/assets/ef23c98b-6afc-4242-9e20-b932212fa321

     Export the data of the “movie.json” file into your Cloudant database “movies”:
      https://github.com/user-attachments/assets/44540d06-f20f-4222-914c-b3f56c45e879

    
     for example : curl -XPOST $CLOUDANTURL/movies/_bulk_docs -Hcontent-type:application/json -d @movie.json
    
    https://github.com/user-attachments/assets/5775589b-b355-496f-836b-46f4df50ee51

    TASK 1 -  import 100 documents into the "movies" collection within the "entertainment" database on a MongoDB instance?
       https://github.com/user-attachments/assets/e641c1bd-988c-4ab9-9a77-a6a5554c52fa

    TASK 2 - What does the MongoDB aggregation pipeline in the image calculate and how does it arrive at the final output of [{ "_id": 2016, "movieCount": 73 }]?

       https://github.com/user-attachments/assets/fdbf2e09-aaf4-4d55-a954-08c7e807346e


       TASK 3 -  What does the MongoDB command db.movies.countDocuments({ year: { $gt: 1999 } }) do, and what is the result of executing it?

       https://github.com/user-attachments/assets/eaa6d6cf-d7c7-4910-81c1-3baf9545f3b0

       TASK 4 - Explain what this MongoDB aggregation pipeline does. Why is the averageVotes field null in the output?
       
       https://github.com/user-attachments/assets/d70d53dc-3799-497f-8b52-d0f7b865276e

       TASK 5 - what command was used to import 100 records from the CSV file "partial_data.csv" into the "movies" collection within the "entertainment" database on a MongoDB instance?
       
       https://github.com/user-attachments/assets/f1936eba-08b0-4f67-bbb9-bd13275d3dbf


       TASK 6 - what command was used to create a new keyspace called "keyspace_name" with a replication factor of 3 using the SimpleStrategy?

               https://github.com/user-attachments/assets/a5f77796-7c53-4fab-8bb8-370c4076d55d

       TASK 7 - what command was used to import 100 records from the CSV file "partial_data.csv" into the "movies" table within the "entertainment" keyspace?
       https://github.com/user-attachments/assets/6f06d3ee-bcfc-4359-bdd0-79e655babf16
       
       TASK 8 - what is the total count of rows in the "movies" table within the "entertainment" keyspace?

     https://github.com/user-attachments/assets/95ef3a70-3f83-4083-a790-543d91c9a7f0

     TASK 9 - What is the purpose of the CREATE TABLE statement in the image and what are the key characteristics of the "movies" table being created?
 
              https://github.com/user-attachments/assets/2ba5b355-f2de-4448-b989-b35dae4dc6bc

       TASK 10 - what is the count of rows in the "movies" table with a "rating" of 'G'?

       https://github.com/user-attachments/assets/df939123-69e2-4747-bdeb-69d13b48b927

       
       
