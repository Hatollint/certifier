# Certifier Project
This project generates a certificate. It runs on Vert.x, and is built on the Gradle build system.
* [Features](#feat)
* [Setting up the project](#setup)
* [Running the app](#run)
* [Making contributions](#contr)
* [Help/Reference](#help)

## <a id="feat"></a>Features
* Students can generate certificates of completion for a variety of courses.
* Mentors can generate certificates for students from data in CSV files.

## <a id="setup"></a>Setting up the project
First you need to install [Git](https://git-scm.com/) (if it is not installed). This command will install Git into the system.
```bash
sudo apt-ger install -y git
```
*Fork* this git repository and *clone* the fork to a local directory.
```bash
git clone https://github.com/jboss-outreach/certifier.git
```
If you prefer using an IDE, install [Intellij IDEA](https://www.jetbrains.com/idea) or another preferred IDE

## <a id="run"></a>Running the app
* [Run in terminal](#run_term)
* [Run at IDE like Intellij IDEA](#run_intellij)

### <a id="term"></a>Run in terminal
```bash
./gradlew run         # pwd should be project home dir
```

#### If using on terminal at windows,
```bash
gradlew run           # pwd should be project home dir
```

### <a id="run_intellij"></a>Run at IDE like Intellij IDEA,
1. Download Java development kit (JDK 8, as 9 won't work)
2. Configure intellij project defaults, project structure, to set the project SDK to java version 1.8
3. Import the cloned repository into your IDE
4. after importing there should be a notification in the bottom right, asking you to link the project to gradle. Click on it and it will occur automatically.
5. Right click the **App** class
6. Right click on the vertx at the top of the code and use the suggested help from intellij to link it to the project
7. Click **Run App.main()**

## <a id="contr"></a>Making contributions
* [Fork](#fork)
* [Configuring Git](#git_conf)
* [Coding](#code)
* [Sending a pull request](#pull)
* [Amending your pull request](#pull_amend)
* [Cleaning up](#clean_up)

### Contents
The first thing to do is create an account on GitHub (if you do not have one yet). Then you should read the rules of participation in the development for the project you selected. These rules are usually found in a file CONTRIBUTING.md in the root of the repository. This repository doesn't have it.

Usually, there are several ways to participate in the development of a project, the main ones are sending a message about some error or desired improvement (Submitting Issue) or directly creating a Pull Request with your correction or improvement (Code Contributing). You can also participate in the improvement of documentation, answers to questions that have arisen from other developers, and much more.

### <a id="fork"></a>Forking the project
We go to the project page and click the button "Fork". This command will create your own copy of the project's repository.

![fork](https://habrastorage.org/files/22d/147/828/22d147828b834ba3b3995df947d6cc3d.png)

Next, you need to bend your copy of the repository.
```bash
cd ~/work/git #folder in which there will be a code
git clone https://github.com/jboss-outreach/wiki-explorer.git #clone repository
```

### <a id="git_conf"></a>Configuring Git
Next, you need to make a small adjustment of your Git, so that when you send commits, your correct name will be displayed.
For this it is enough to execute these commands:
```bash
git config --global user.name "Your name"
git config --global user.email you@example.com
```


### <a id="code"></a>Coding

Starting to work on your fix, you must first create the corresponding Git branch, based on the current code from the base repository.

Choose a clear and concise name for the branch, which would reflect the essence of the changes.
It is considered a good practice to include the number of the GitHub issue in the branch name.
```bash
git fetch upstream
git checkout -b <your-name-branch> upstream/master #exemple
```

Now you can easily start working on the code.
While working, remember the following rules:
* Follow the coding standards (usually PSR standards);
* Write unit tests to prove that the bug is fixed, or that the new function actually works;
* Try not to violate backward compatibility without extreme necessity;
* Use simple and logical whole commits;
* Write clear, clear, complete messages when you commit changes.


### <a id="pull"></a>Sending a pull request

While you were working on the code, other changes could be made to the main branch of the project. Therefore, before submitting your changes, you need to rebase your branch.
This is done like this:
```bash
git checkout <your-name-branch>
git fetch upstream
git rebase upstream/master
```
#### Deploy on Windows (with minimal use of CMD):

Download Google App Engine from [here](https://storage.googleapis.com/appengine-sdks/featured/google_appengine_1.9.63.zip), if you haven't already.
Unzip it and add the directory to PATH in environment variables. More help can be found [here](http://www.itprotoday.com/management-mobility/how-can-i-add-new-folder-my-system-path)

After that, we go to your project clone repository, in which you participate and click the button "New Pull Request".
And we see the following form:

![New Pull Request](https://habrastorage.org/files/191/d14/269/191d14269eae48e29d2179e32cf4fb2c.png)
On the left, you must select the branch in which you want to kill the changes (this is usually the master, well, in general, this is the branch you rebase to).
On the right is a branch with your changes.
Next, you will see a message from GitHub about whether it is possible to automatically change the changes or not.
In most cases, you will see Able to merge.
If there are conflicts, you will most likely need to review your changes.
Then click the button - Create Pull Request.
When filling out the name and description of your Pull Request it is considered good practice to specify the Issue number for which your Pull Request is created.
After creating the Pull Request, it will run the tests, perhaps some tools for metrics and so on. The results of his work you will see in your Pull Request as shown below:

![results](https://habrastorage.org/files/46c/e42/a41/46ce42a41ef24141a5c74d76cdb71f13.png)

In case the tests are not passed or the build is not compiled, you will see a red error message and by clicking the Details link you will see what is wrong. In most cases, you will need to fix your Pull Request so that all checks are successful.


## Contributing to the project
1. Fork and clone this repository.
2. Make changes to your local copy of this repository.
3. Commit and push your local changes to your fork on GitHub.
4. Review the changes on your fork.
5. Create a pull request to merge your changes into this repository.

### <a id="pull_amend"></a>Amending your pull request

If everything is good with your pull request, then soon it will be merged by a project collaborator.
However, it is more likely that a reviewer asks for some changes to be made to your pull request.
To do so, simply return to step 6 and after making the changes and commit we perform the following commands:
```bash
git checkout <your-name-branch>
git fetch upstream
git rebase upstream/master
git push origin <your-name-branch>
```
### <a id="clean_up"></a>Cleaning up

After your pull request has been accepted or rejected, you need to delete the branch with your changes.
This is simply done with:
```bash
git checkout master
git branch -D <your-name-branch>
git push origin --delete <your-name-branch>
```
Instead of the last command, you can also run
```bash
git push origin :<your-name-branch>
```

## <a id="help"></a>Help/Reference

If you are stuck anywhere or need any help, you can refer the following:

1. [Git Handbook](https://guides.github.com/introduction/git-handbook)
2. [Introduction](https://guides.github.com/introduction/flow)
3. [Chat](https://gitter.im/jboss-outreach/gci)
