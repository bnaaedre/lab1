# Setup
### First-time Setup
This will setup and configure git and GitHub on Matrix. Run everything as your local user, unless indicated otherwise.

1. Configure git with your full name and Seneca e-mail address:
```bash
git config --global user.name "Firstname Lastname"
git config --global user.email "yoursenecaid@myseneca.ca"
```
(optional) You may want to add a key to Github to reduce password prompts. Generate an SSH key-pair to add to your GitHub account:
```bash
ssh-keygen  # Follow defaults (hit enter)
cat ~/.ssh/id_rsa.pub
```
Copy/paste your public key from above (starting from 'ssh-rsa') to your GitHub account:
> https://github.com/settings/ssh/new

5. If you have an exisiting ops435 directory, rename it:
```bash
mv ~/ops435 ~/old_ops435
```
### Per-Lab Setup
This will download Lab 1 locally, allowing you to work on your scripts and upload (push) them back up to GitHub.

1. Clone your lab repository into your ~/ops435/lab1 directory using SSH:
```bash
git clone git@github.com:ops435/lab-1-yourgithubusername.git ~/ops435/lab1/
```
You may continue to **Investigation 2** in the Lab 1 instructions posted on the [Wiki](https://wiki.cdot.senecacollege.ca/wiki/OPS435_Online_Lab1#Investigation_2_-_Python_on_Matrix).

# Submission
When you have completed all sections of the lab, no submission to Blackboard is necessary. Complete the following steps:

1. Run the checking script. Make sure you identify and correct any and all errors in your scripts:
```bash
cd ~/ops435/lab1/
pwd #confirm that you are in the right directory
python3 ./CheckLab1.py -f -v 
```
2. Create laboutput.txt by redirecting the output from CheckLab1.py:
```bash
python3 ./CheckLab1.py -f -v &> laboutput.txt
```

3. Commit and push (upload) your lab work:
```bash
git add lab*
git commit -m "Individual message or note."
git push
```

You can make changes to your scripts and reupload as many times as you like. Make sure you commit+push to do so.

**Note:** Your lab is automatically submitted at the due date and time using the last published code. Any changes you publish after the due date won't be marked or seen by your professor.
