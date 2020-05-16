# Setup
### First-time Setup
This will setup and configure git and GitHub in your CentOS 7 environment. Run everything as your local user, unless indicated otherwise.

1. Install git (as root):
```bash
su -
yum install git
exit
```
2. Configure git with your full name and Seneca e-mail address:
```bash
git config --global user.name "Firstname Lastname"
git config --global user.email "yoursenecaid@myseneca.ca"
```
3. Generate an SSH key-pair to add to your GitHub account:
```bash
ssh-keygen  # Follow defaults (hit enter)
cat ~/.ssh/id_rsa.pub
```
4. Copy/paste your public key from above (starting from 'ssh-rsa') to your GitHub account:
> https://github.com/settings/ssh/new

5. Rename your exisiting ops435 directory:
```bash
mv ~/ops435 ~/old_ops435
```
6. Recreate the directory structure:
```bash
for x in {1..8}; do mkdir -p ~/ops435/lab$x; done
```


### Per-Lab Setup
This will download Lab 1 locally, allowing you to work on your scripts and upload (push) them back up to GitHub.

1. Clone your lab repository into your ~/ops435/lab1 directory using SSH:
```bash
git clone git@github.com:ops435/lab1-yourgithubusername.git ~/ops435/lab1/
```
2. Copy your backed-up work into your new GitHub-linked directory:
```bash
cp ~/old_ops435/lab1/* ~/ops435/lab1/
```

# Submission
1. Run the checking script. Make sure you identify and correct any and all errors in your scripts:
```bash
cd ~/ops435/lab1/
pwd #confirm that you are in the right directory
python3 ./CheckLab1.py -f -v
```
2. Paste the checking script output into *laboutput.txt*:
```bash
vi ~/ops435/lab1/laboutput.txt
```

3. Commit and push (upload) your lab work:
```bash
git add lab*
git add gitlog.txt repo_tree.txt
git commit -m "Individual message or note."
git push
```

You can make changes to your scripts and reupload as many times as you like. Make sure you commit+push to do so.

**Note:** Your lab is automatically submitted at the due date and time using the last published code. Any changes you publish after the due date won't be marked or seen by your professor.
