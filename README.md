# TravelMemoryAssignment
Steps are taken as under for TravelMemory Assignment.
1.	Created EC2 instance named “travelmemoryks” and established connection.
   <img width="1892" height="692" alt="image" src="https://github.com/user-attachments/assets/6fc2b986-8b84-4d9b-b3e6-8c1dbfb760cc" />
2. Run commands for package updates and installation of npm and nodejs
   a. sudo apt update
   b. sudo apt install nodejs
   c. sudo apt install npm
3. Created a database in MongoDB named "TravelMemoryDb"
   <img width="940" height="323" alt="image" src="https://github.com/user-attachments/assets/12668926-18e5-4f20-ac7d-bfe6e83c6e92" />.
4.	Clone repository from github link under EC2 instance with command 
   git clone https://github.com/UnpredictablePrashant/TravelMemory.git
  	<img width="1332" height="870" alt="image" src="https://github.com/user-attachments/assets/106ecd31-8939-450c-a010-e68b8bbe05aa" />
5. Navigated to the "backend" folder under TravelMemory.
6. Created .env file and set connectionstring
   <img width="1902" height="833" alt="image" src="https://github.com/user-attachments/assets/f8d6375e-ce50-4308-b0fb-4e22a9303366" />
7. Next run npm install
   <img width="1792" height="485" alt="image" src="https://github.com/user-attachments/assets/811b1a92-2150-48dd-9d12-0d7908bb1820" />
8. As per the document openning the ports in security group
<img width="1890" height="811" alt="image" src="https://github.com/user-attachments/assets/b0b5565b-92e9-45e9-b9f8-fd6535d0afbc" />
9. Now run command node index.js and keep the server running and check where backend is running or not with public IP along with port 3001.
   <img width="1911" height="575" alt="image" src="https://github.com/user-attachments/assets/27ec1c01-a1c4-4d75-a7ea-6442e798cd69" />
10. Now again go back to EC2 instance and navigate to frontend folder.
11. Create .env file 
<img width="1845" height="825" alt="image" src="https://github.com/user-attachments/assets/21008050-08de-46c2-9912-f9033f909750" />
12. Run npm install
13. Run application with command npm start.
    <img width="1888" height="915" alt="image" src="https://github.com/user-attachments/assets/9e8cca06-2479-4262-9e78-abc1c1f569eb" />
    <img width="1873" height="702" alt="image" src="https://github.com/user-attachments/assets/995eb75d-90ea-4f69-be22-239bb7eb75cb" />

    <img width="1877" height="885" alt="image" src="https://github.com/user-attachments/assets/35cc4b6d-cce0-49fe-a0c0-e00a6982af29" />

    At this stage application is running successfully.
14. In continuation, Install Nginx web server with few commands.
    sudo apt update
    sudo apt install nginx -y
    <img width="1405" height="365" alt="image" src="https://github.com/user-attachments/assets/67996442-3d61-439e-ad65-dd3ce8abf96a" />
15. Start the Nginx Server with two commands:
    sudo systemctl start nginx
    sudo systemctl enable nginx
16. Next need to do configuration for Ngnix, Run command like
    sudo nano etc/nginx/nginx.conf
17. Test connection for nginx
    <img width="1838" height="758" alt="image" src="https://github.com/user-attachments/assets/24da9ad4-e9aa-428a-86ab-a696e3563ff9" />
    <img width="1838" height="758" alt="image" src="https://github.com/user-attachments/assets/d0840446-94a5-46a9-a046-6e936c0bb33d" />

18.The recommended production setup is:
   Nginx serves React static files from build/ backend runs on port 3001
   Nginx proxies /api requests to port 3000
19. Nginx proxies /trip requests to port 3000
  on my computer, not on the EC2 instance, so the page stays on "Loading...".
20. Tried to check current status with command : cat ~/TravelMemory/frontend/src/url.js
21. Change the base url i.e. export const baseUrl = "";
22. Navigated to folder frontend and done a fresh build.
   npm run build
23. Deploy the application with command
   sudo rm -rf /var/www/travelmemory/*
   sudo cp -r build/* /var/www/travelmemory/
24. Restart nginx with command : sudo systemctl restart nginx
 <img width="1675" height="2213" alt="image" src="https://github.com/user-attachments/assets/ebff2c65-149b-406b-8a33-7f011dabad55" />
25. Test with the both of the EC2 public IP.
   <img width="1880" height="878" alt="image" src="https://github.com/user-attachments/assets/2d4f7f31-4f04-4d37-95d7-27114fe4f5de" />
   <img width="1832" height="891" alt="image" src="https://github.com/user-attachments/assets/dcab4a68-d89e-4349-b15f-3b3605a7f330" />

26. Now in context of addition of these instances to load balancer, it is confirmed that both the instances are i working state.
27. Created a target group named "travelmemory-tg"
<img width="1880" height="980" alt="image" src="https://github.com/user-attachments/assets/9f5f5364-fa26-401a-bca0-df4fba8a151e" />
28. Register EC2 instances
    <img width="1856" height="965" alt="image" src="https://github.com/user-attachments/assets/4edfdabe-0169-46b2-b60f-c1eeee0886e9" />
29. Health check
    <img width="1910" height="920" alt="image" src="https://github.com/user-attachments/assets/5478248a-d528-4e1b-a188-18ea1238df42" />
30. Creating a load balancer and opted Application load balancer.
    <img width="1901" height="961" alt="image" src="https://github.com/user-attachments/assets/4def581c-aeba-4262-b883-70dbfce625c1" />
    Load balancer created
    <img width="1888" height="995" alt="image" src="https://github.com/user-attachments/assets/fa60b148-1879-499d-b992-6346ec4358f9" />
31. Checked health for the target group
<img width="1897" height="977" alt="image" src="https://github.com/user-attachments/assets/c5f40fd5-2d40-4794-9c5b-c0368f562d7f" />
32. Now copied the DNS name from EC2 → Load Balancers → travelmemory-alb and test it in browser.
<img width="1902" height="887" alt="image" src="https://github.com/user-attachments/assets/227e4593-81d3-4b46-8838-b53134445e6e" />
33. Purchase a domain from BigRock
34. Seeting up with cloudflare.
    <img width="1847" height="993" alt="image" src="https://github.com/user-attachments/assets/2bf8cc4a-c7a2-428b-880f-883b2292a3a4" />


36. <img width="1502" height="817" alt="image" src="https://github.com/user-attachments/assets/d42b2a32-d333-46d0-8398-c0558dc80305" />
<img width="1490" height="773" alt="image" src="https://github.com/user-attachments/assets/2c21dbca-7f68-47ae-8cd3-2b5c4790bbac" />

<img width="1857" height="786" alt="image" src="https://github.com/user-attachments/assets/3d9d8ff4-23d3-476b-9cb3-e9dbcb452e33" />

<img width="1891" height="826" alt="image" src="https://github.com/user-attachments/assets/cbc19953-c1f7-4731-a4a5-167213accf59" />

<img width="1913" height="966" alt="image" src="https://github.com/user-attachments/assets/5bd39e3f-ba48-4cb4-95dd-36c6c1e66de2" />


Conclusion:
 There are few deployment concepts that we covered during this exercise.
 a. Started with the archicture for TravelMemory
       User
        |
      React Frontend
        |
      Express API
        |
      MongoDB Atlas
Followed by the deployment concept
**AWS EC2**
Launching EC2 instances
Security Groups
Public vs Private Subnets
**Node.js Application Hosting**
Backend hosted on EC2.
API : GET /trip
      POST /trip
      GET /trip/:id
**MongoDB Atlas**
Cloud database used by all EC2 instances.
   Shared database
   EC2-1 ----\
   EC2-2 ----- MongoDB Atlas
   EC2-3 ----/
  **React Production Build**
  npm run build
  **Nginx Web Server**
  Installed Nginx
     Static File Server
        root /var/www/travelmemory;
      Reverse Proxy
         location /trip {
    proxy_pass http://localhost:3001;
   }
   **Reverse Proxy**
   **DNS Configuration**
      kspractzone.online
      Used:
         BigRock - Domain Registrar
         Cloudflare - DNS Provider
**Migrated DNS management from BigRock to Cloudflare.**
      kami.ns.cloudflare.com
      kobe.ns.cloudflare.com
**Configured A Record and CNAME in DNS records**
**AWS Application Load Balancer**
**Target Groups**
   Registered
      Frontend Instance 1
      Frontend Instance 2
**Horizontal Scaling**
**Security Groups**
   Configured inbound rules:
      HTTP - Port 80
      SSH  - Port 22
      Backend - Port 3001

      **Final Architecture**

                     Users
                        |
                        |
                 Cloudflare DNS
                        |
                        |
                AWS Load Balancer
                        |
         --------------------------------
         |                              |
         |                              |
     EC2 Instance 1                EC2 Instance 2
     React + Node                  React + Node
         |                              |
         -----------MongoDB Atlas--------
         
**AWS Services Used**
EC2
Security Groups
Key Pairs
Application Load Balancer (ALB)
Target Groups
**DevOps Tools Used**
Nginx
Node.js
React Build
Git
**Cloud Services Used**
MongoDB Atlas
Cloudflare
BigRock DNS



















