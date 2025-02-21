Steps to create a connection between EC2 instance and GIT bash.

1. Create EC2 instance in AWS EC2.
2. Copy Key.pem to your working folder.
   
   Ex: streamlit-app.pem
3. Open git bash in your local Desktop or Vs Code Terminal. And connect your EC2 instance with git bash using EC2 instance SSH client Id. It's look like -- "ssh -i /path/to/your/key.pem ec2-user@your-ec2-ip"

		e.g., ssh -i "streamlit-app.pem" ubuntu@ec2-18-207-222-33.compute-1.amazonaws.com
4. If the file is in a GitHub repository, you can SSH into your EC2 instance and clone the repo directly:

		e.g., git clone https://github.com/yourusername/your-repo.git
5. Once check all files/ folder colned or not using this command:

		ls
6. Now you can see all files/ Folders. Change directory to your required Repository folder. Using this command

		e.g., cd streamlit-app
7. Update once your Instance

		sudo apt update
8. Now check once python version. if python already existing upgrade it otherwise install python :

		sudo apt install python3.12-venv -y
9. Check once again python version. It's show downloaded python version.

		python3 --version
10. Creating a virtual environment helps keep dependencies isolated:

		python3 -m venv myenv
11. Now activate a virtual environment using this command.

		source myenv/bin/activate
13. Check pip installed or not

		pip --version
14. If pip not installed use this command for installing pip.

		sudo apt install -y python3-pip
	already installed update it

		pip install --upgrade pip
15. Now install all required dependencies:

		pip install -r requirements.txt
	If in case above command not working, Install dependencies one by one.

 		pip install streamlit
16. To delete a file (e.g., app.py or requirments.txt), use:

		rm app.py requirments.txt
17. If you want to delete the myenv or python-app directory use:

		rm -rf myenv python-app
18. Update the Repository

	A. If the Folder is Already a Git Repository use:

		git pull origin main
	B.If the Folder is NOT a Git Repository

		rm -rf python-app  # Be careful! This deletes everything in the folder
		git clone https://github.com/yourusername/your-repo.git
19. Now run code in the command inside the activated SSH Session.

		streamlit run app.py
	or The nohup command allows the app to keep running even after you close the SSH session.

		nohup streamlit run app.py
20. To stop the Streamlit app

	A.  first find the process ID (PID):

		ps aux | grep streamlit
	B. Then kill it:

		kill -9 <PID>
    
