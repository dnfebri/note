# Create ssh Key Github On Ubuntu

## Generating a new SSH key
1. go to the .ssh directory and register email/unique name
   ```
   cd ~/.ssh
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
2. Enter a unique name or leave it blank
3. At the prompt, type a secure passphrase
4. Start the ssh-agent in the background.
   ```
   eval $(ssh-agent -s)
   ```
   ```
   ssh-add
   ```

## Adding a new ssh key to your github account
1. open file ssh extension .pub
   ```
   cd ~/.ssh/unique_name.pub
   ```
2. Then select and copy the contents of .pub file
3. In the upper-right corner of any page on GitHub, click your profile photo, then click Settings.
4. In the "Access" section of the sidebar, click  SSH and GPG keys.
5. Click New SSH key or Add SSH key.
6. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal laptop, you might call this key "Personal laptop".
7. In the "Key" field, paste your public key.
8. Click Add SSH key.
9. Test connection on terminal
    ```
    ssh -T git@github.com
    ```

## Problem
1. git@github.com: Permission denied (publickey).
   - repeat this command command
   - ```eval "$(ssh-agent -s)"```
   - ```ssh-add namefile```
   - Enter passphrase
   - Test connection ```ssk -T git@github.com```
