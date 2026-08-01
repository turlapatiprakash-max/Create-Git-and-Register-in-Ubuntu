# Create-Git-and-Register-in-Ubuntu
Great! The easiest and most secure way is to connect your Ubuntu terminal to GitHub using **SSH**. Follow these steps.
### Step 1: Check if Git is installed
Open Terminal and run:
bash
git --version
If Git is not installed, install it:
sudo apt update
sudo apt install git -y
Verify again:
git --version
### Step 2: Configure Git
Replace the values with your own GitHub name and email:
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
Check your configuration:
git config --list
### Step 3: Generate an SSH Key
Run:
ssh-keygen -t ed25519 -C "your_email@example.com"
Press **Enter** for the default location.
When prompted for a passphrase:
Press **Enter** to skip it, or
Enter a passphrase for extra security.
### Step 4: Start the SSH Agent
eval "$(ssh-agent -s)"
Add your key:
ssh-add ~/.ssh/id_ed25519
### Step 5: Copy the Public Key
Display your public key:
cat ~/.ssh/id_ed25519.pub
Copy the entire output beginning with:
ssh-ed25519 AAAA...
### Step 6: Add the Key to GitHub
1. Log in to your GitHub account.
2. Click your profile picture → **Settings**.
3. Go to **SSH and GPG keys**.
4. Click **New SSH key**.
5. Give it a title (for example, "Dell Inspiron Ubuntu").
6. Paste the copied key.
7. Click **Add SSH key**.
### Step 7: Test the Connection
Run:
ssh -T git@github.com
The first time you'll see:
Are you sure you want to continue connecting (yes/no)?
Type: yes
If everything is correct, you'll see something similar to:
Hi yourusername! You've successfully authenticated, but GitHub does not provide shell access.
### Step 8: Clone a Repository
git clone git@github.com:username/repository.git
## If you already have a local project
Go to your project folder:
cd myproject
Initialize Git:
git init
Add files:
git add .
Commit:
git commit -m "Initial commit"
Connect to GitHub:
git remote add origin git@github.com:username/repository.git
git branch -M main
git push -u origin main
<img width="846" height="473" alt="image" src="https://github.com/user-attachments/assets/8e54cb9c-0004-40e8-8c93-b9813abebd0a" />
