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
    v<img width="1838" height="758" alt="image" src="https://github.com/user-attachments/assets/24da9ad4-e9aa-428a-86ab-a696e3563ff9" />

    <img width="1838" height="758" alt="image" src="https://github.com/user-attachments/assets/d0840446-94a5-46a9-a046-6e936c0bb33d" />

18.The recommended production setup is:
   Nginx serves React static files from build/ backend runs on port 3001
   Nginx proxies /api requests to port 3000
   <img width="1776" height="790" alt="image" src="https://github.com/user-attachments/assets/908b8c9a-e89f-4842-a5b7-54d826e4d74a" />
   <img width="1906" height="818" alt="image" src="https://github.com/user-attachments/assets/ec3a044a-6703-4462-ad81-083fc79dc429" />
19. Nginx proxies /trip requests to port 3000
   <img width="1675" height="2213" alt="image" src="https://github.com/user-attachments/assets/ebff2c65-149b-406b-8a33-7f011dabad55" />
20. 











