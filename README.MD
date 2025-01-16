# Installing Python on MacOS

## Install `pyenv`

Before installing Python, we first need to install `pyenv`, a version manager
for Python. We will likely only use Python version 3.8.13 in the Software
Engineering curriculum, but installing pyenv will make it simple to install
newer versions later on.

Enter the following command in the Terminal:

```console
$ brew install pyenv
```

Open your `.zshrc`file in VSCode:

```console
$ code ~/.zshrc
```

Add the following to the end of the file:

```text
if which pyenv > /dev/null; then
  eval "$(pyenv init -)";
fi
```

We want to load `pyenv` every time we open a new terminal window; this will make
sure that it does!

Enter the following command to load your new settings:

```console
$ source ~/.zshrc
```

---

## Install Python

Run the following command to install Python (you'll notice pyenv makes us put in
the exact version instead of being able to just say 3.8 or 3):

```console
$ pyenv install 3.8.13
```

After some time this should complete without any errors. It could take a while
since you are compiling Python from source code.

Once this is finished we also need to tell pyenv this is our default version of
Python using this command:

```console
$ pyenv global 3.8.13
```

Ensure that these changes take effect by closing your terminal and opening a new
one.

### Check Your Work

You can verify that you have the correct version of Python installed by typing:

```console
$ python3 --version
```

This command should show 3.8.13.

---

## Install Pipenv

Another piece of software we will use in class is Pipenv. We will learn more
about what Pipenv is later; for now, go ahead and install it:

```console
$ pip install pipenv
```

After you have installed pipenv, modify your `.zshrc` file to add an export line
inside the `if` statement we added earlier, after the `eval` line:

```text
 if which pyenv > /dev/null; then
     eval "$(pyenv init - )";
     export PIPENV_VENV_IN_PROJECT=1
 fi
```

Save and close your shell startup file, then enter the following command once
again to finish configuring your environment:

```console
$ source ~/.zshrc
```

Congratulations! If you've completed all these steps you are ready to code in
Python!
