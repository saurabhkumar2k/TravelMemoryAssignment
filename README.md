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




