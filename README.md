
## Git Installation !

First thing first...you have to install git through Homebrew package manager.

```
brew install git
```

Then, check if Git is installed with this command:

```
git --version
```
_If everything worked, you should see a message with the Git version installed._
![Ein is ready](Ein_is_ready.png)
## Time for some configuration steps !

```
git config --global user.name "your.username"
```
_It tells Git your name. Every commit will have both your name and your email attached._

```
git config --global user.email "your@email"
```
_It tells Git what your email is. This should be the same email of your GitHub account and it will be attached to every commit you make._

```
git config --global color.ui true
```
_This turns on colored output in Git messages. Good for readability!_

```
git config --global --list
```
_This shows all your Git settings so far. It's a quick way to check if everything was configured correctly._

## Generate a SSH key to connect your Mac to GitHub !

Run this commad.
```
ssh -T git@github.com
```

You  might get a message that ends with something like:
```
git@github.com: Permission denied (public key).
```

Then run the following command and if you don't see anything you have to generate a new key.
```
cat ~/.ssh/id_rsa.pub
```
 
### Create a new key !

```
 ssh-keygen -t rsa -b 4096 -C "your.github@email.com"
```
_This will generate a new key._

 ***!! You will get a few prompts. You can confirm the default file location.***
***If you don't want to enter your credentials every time you push to GitHub, just hit enter twice more to leave the passphrase. !!***
...Once the key has been generated, can copy it to the clipboard with the following command:
 
```
 cat ~/.ssh/id_rsa.pub | pbcopy
```

### Login to GitHub

Go to **GitHub > Settings > SSH and GPG keys > New SSH key**

![Screen](Screen.png)
 
 In the **"Title"** you can add a label for the new key. For example: "My MacBook Air".
 Then, paste in your SSH key and click the **"Add SSH key"** button. After that you may be asked to confirm your password.

Finally, run this command to test the SSH connection to GitHub:

```
ssh -T git@github.com
```

And if everything is well, you will see this message:

![Message](Message.png)
![Ein is happy](Ein_is_happy.png)
