# GitHub-setup-with-SSH-keys


Enter ls -al ~/.ssh to see if existing SSH keys are present:

ls -al ~/.ssh

Check the directory listing to see if you already have a public SSH key. By default, the filenames of the public keys are one of the following:

id_dsa.pub
id_ecdsa.pub
id_ed25519.pub
id_rsa.pub

If you don't have an existing public and private key pair, or don't wish to use any that are available to connect to GitHub, then generate a new SSH key.

ssh-keygen -t rsa -C "email@example.com" This creates a new ssh key, using the provided email as a label.

Copy the contents of the file ~/.ssh/id_rsa.pub to your SSH keys in your GitHub account settings. Test SSH key: pbcopy < ~/.ssh/id_rsa.pub

ssh -T git@github.com clone the repo: git clone git://github.com/username/your-repository

Now cd to your git clone folder and do:

git remote set-url origin git@github.com:username/your-repository.git

Now try editing a file (try the README) and then do:

git add -A git commit -am "my update msg" git push
